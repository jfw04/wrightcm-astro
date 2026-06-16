# Wright Construction Management — Website (Astro)

Static, fast, SEO-friendly site built with [Astro](https://astro.build).

## Edit content
**Everything lives in one file:** `src/data/content.json`
- Stats, services, process steps, client logos, projects, white papers, and testimonials.
- Add a project: add an object to `projects` and drop its photos in `public/assets/img/projects/`.
- Turn testimonials on: set `testimonials.enabled` to `true`.

Page copy (Services / About / Careers / Contact) lives in the matching file in `src/pages/`.

## Run locally
```bash
npm install      # first time only
npm run dev      # preview at http://localhost:4321
npm run build    # outputs the deployable site to dist/
```

## Structure
- `src/pages/` — one file per page (clean URLs, no .html)
- `src/components/` — Header, Footer, ProjectCard, ResourceCard, FinalCta
- `src/layouts/Base.astro` — shared page shell
- `src/styles/global.css` — all styles
- `public/assets/img/` — images
