# AasPass Platform Decision Tree (DT)

A searchable, self-contained support decision tree for AasPass — covering the **Customer**, **Vendor**, and **Delivery Partner** platforms in one tool, plus a home screen and a built-in keyword search assistant.

## ⚠️ If you're seeing this README instead of the tool
The actual live site is served from `index.html` at a **different URL**:
## How to enable GitHub Pages

1. Push this folder's contents to a GitHub repository (root of the repo — `index.html` should sit at the top level, not inside a subfolder, unless you configure Pages to use that subfolder).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, choose `main` (or `master`) and folder `/ (root)` — then **Save**.
5. Wait ~30–60 seconds. GitHub will show a green banner with your live URL:
   `https://<your-username>.github.io/<repo-name>/`
6. Visit that URL — not the repo's main `github.com/...` page — to see the actual tool.

No build step, no dependencies, no server. It's a single static HTML file with embedded CSS and JavaScript.

---

## What's in this repo

```
/
├── index.html   ← the entire tool (this is what GitHub Pages serves)
└── README.md    ← this file (repo documentation only, not part of the live site)
```

## What the tool does

- **Home screen** — what AasPass is, what it does, leadership, how to use the DT, and links to the companion documents (PRD, Unit Economics, SOP Manual, etc.)
- **Three platform tabs** — Customer (15 topics), Vendor (14 topics), Delivery Partner (18 topics)
- **Search** — press `/` anywhere to jump into the search bar, `Esc` to clear it or close the chat panel
- **Cross-platform related topics** — many entries link to the matching topic on another platform
- **Chat assistant** (bottom-right bubble) — a keyword-matching assistant that searches this same DT content and returns what to check, what to ask, what to tell the customer, and where to escalate. It is **not** a live AI model — there's no backend, so it can't safely call one — it's a scored keyword search over the data already in this file.

## Updating the content

Everything is in `index.html`, inside the `<script>` tag, in three arrays near the top:

- `CUSTOMER_DATA`
- `VENDOR_DATA`
- `DELIVERY_DATA`

Each entry is a plain JavaScript object. To add a new topic, copy an existing entry in the relevant array, change its fields, and give it a unique `code`. To edit an existing topic, just edit its fields directly. Save the file and push — GitHub Pages redeploys automatically within a minute or so of a push to the branch configured above.

No build tools, no `npm install`, no compilation — edit the file, commit, push.

## Source

Built from the AasPass PDR (corrected), the AasPass Unit Economics / Financial Model (corrected), and the Business Operations, Sales & SOP Master Manual. Every factual claim in the tool is tagged LOCKED/CONFIRMED, PROPOSED, OPTIONAL, TBD, or LEGAL/FINANCE REVIEW — see the legend in the tool's footer.
