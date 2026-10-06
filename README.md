# site/ - the public face of ProcureFlow

Source of truth for the public static site. Lives in this (private) repo and is mirrored to
a public GitHub Pages repo by the deploy step, so one folder serves both.

Plain HTML, no generator, no CMS: the landing page is also the design-gate artifact, and the
only generated pages are the per-org forms, written by a small Python step in
`scripts/deploy-home.sh`. Revisit a generator only if the site grows past a handful of pages
or someone non-technical needs to edit copy regularly.

```
site/
  index.html            the landing page: the pitch story, outcomes not machinery
  demo/                 (later) the artifacts as real pages: control-tower demo, engine lab
  app/order/<token>/    (generated per org) the Telegram Mini App order form; unlisted path,
                        SKU list baked at deploy time, result sent to the bot via sendData
```

Rules that apply here as everywhere: steel-first examples, sell outcomes never "AI", no em
dashes, nothing on these pages is data or a secret (orders go straight to Telegram; the form
pages carry only field layout and SKU names).
