# ADRA Humanitarian SitRep Generator — Website

A standalone, no-login website for drafting condensed, three-page ADRA-style humanitarian situation reports.

## Features
- Emergency metadata and key indicators
- Narrative fields for situation, needs, achievements, risks, priorities, coordination, projects and sources
- Ten humanitarian sectors, each with needs, activities, progress and multiple captioned photos
- Built-in ADRA logo on each PDF and Word report page
- Fixed three-page PDF export and three-page structured Word export
- Live three-page editorial preview, autosaved local drafts, JSON backup/import
- No database, no server, no login, no API key

## Local development

Requires Node.js 20.19+ (or 22+).

```bash
npm install
npm run dev
```

Visit the local URL shown in the terminal.

## Deploy to Vercel

1. Create a new GitHub repository (private is fine) and upload the contents of this folder **at the repository root**.
2. At https://vercel.com/new, import the repository and authorize Vercel to access it.
3. Framework: Vite; Build command: `npm run build`; Output directory: `dist`.
4. Deploy. The resulting website is accessible to anyone with its URL; a private GitHub repository does **not** make the deployed website private.

You can also run `npm run build` and upload `dist/` to any static hosting provider.

## Important limitations

- This is **not** an AI-connected app. It offers structured narrative editing and length-limited report drafting, not generative AI. Adding AI requires a secure backend and API credentials; do not put an API key in client-side code.
- Reports and images are saved in browser localStorage, which can be cleared and has size limits. Use **Save draft (.json)** for reliable backups. There is no cross-device synchronization.
- The PDF has exactly three pages by design. Long content is shortened for the export, and some sectors may be omitted (PDF shows up to seven; Word up to six). Verify all content before distribution.
- The Word document uses explicit page breaks and compact content, but pagination can vary across Word versions and fonts. Check the exported Word file and PDF before publishing.
- The report preview is an approximation, not a pixel-perfect PDF or Word rendering.
- This public site does not have authentication. Do not enter sensitive or personally identifiable beneficiary information on a shared device. Images stay local unless a user exports or shares a report.
- The ADRA logo is bundled from the supplied image; verify organizational approval before external publication.

## Repository layout

- `src.js`: application UI, state, photos, exports
- `style.css`: responsive layout and print-style preview
- `public/adra-logo.png`: supplied official ADRA logo
- `vercel.json`: Vercel build configuration
- `package.json`: dependencies and scripts

## Privacy

No analytics, tracking, network uploads, or AI service calls are included. The only network requests on the hosted site are for the static website assets. The site uses the browser's local storage for draft persistence.
