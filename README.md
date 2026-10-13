# teaadvisory site: editing and deployment

Everything lives in `index.html`. Open it in any code editor and find `const SITE = {` near the top of the `<script>` block. All copy, skills, projects and links sit in that one object. You never need to touch the layout code below it.

## Swap in real projects

Each project in `SITE.projects` looks like this:

```js
{ id: "telecom-launch",          // unique, lowercase, no spaces
  segment: "media",              // media | product | visual | branding | video
  title: "Launch messaging for digital products",
  client: "",                    // client name; leave empty for confidential work
  sector: "Digital telecommunications",
  confidential: true,            // true adds the badge, hides the client, shows "Request details"
  role: "Product and Brand Designer",
  year: "2025",
  did: "One or two sentences on what you did. Shown on the card.",
  scope: ["Bullet one", "Bullet two"],  // shown in the modal
  outcome: "What changed because of the work.",
  metric: "Engagement up 20 to 35 percent",  // optional; use ranges for NDA work
  tools: ["Figma", "Premiere Pro"],
  ai: ["Claude"]                 // shown as tinted tags
}
```

1. Replace every value in square brackets, such as `[Client name]`, `[Year]` and `[Start year]`.
2. Delete seed projects you do not need, or add more. Each segment can hold any number.
3. To add a segment, add an entry to `SITE.segments` and use its `id` in projects.
4. Wrap one word in `*asterisks*` inside any heading to colour it.
5. Proficiencies live in `SITE.proficiencies.skills` (outer ring) and `SITE.proficiencies.tools` (inner ring). Each needs an `icon` name from the `ICONS` list under the data. Both rings space their icons evenly however many you add.
6. Sectors in the scrolling banner live in `SITE.sectors.items`.

## Before going live

- **Your photo**: save a portrait (at least 900 x 1200, JPG) as `photo/ezra.jpg`. Until it exists, the hero shows an EA monogram behind the floating text.
- **Tracka in Figma**: in Figma, click Share, copy the link to the file or prototype, and paste it into the `figma` field of the `tracka` project. The project window then shows an "Open in Figma" button and an embedded prototype visitors can click through. Set the Figma link to "Anyone with the link can view".
- **Calendly**: paste your booking link into `SITE.calendly`. Every "Book a strategy session" button uses it.
- **CV**: the PDF is already at `cv/Ezra-Anya-CV.pdf`. Replace the file to update it.
- **Contact details**: email, WhatsApp and LinkedIn come from the CV. Add the Instagram handle in `SITE.contact.instagram`.
- **Contact form**: create a free form at formspree.io, copy the endpoint and paste it into `SITE.contact.formEndpoint`. Until then the form tells visitors to use email or WhatsApp.
- **Domain and sharing image**: replace `https://www.teaadvisory.com/` in the `<head>` with the real domain. Add a 1200 x 630 PNG named `og-image.png` next to `index.html` for link previews on WhatsApp, LinkedIn and X.

## Deploy

**Netlify (simplest).** Go to app.netlify.com/drop and drag this whole folder onto the page. The site is live in seconds. Add the custom domain under Domain settings.

**Vercel.** Install the CLI with `npm i -g vercel`, then run `vercel` inside this folder and follow the prompts.

**GitHub Pages.** Push the folder to a repository, then open Settings, Pages, and set the source to the main branch.

There is no build step. Any host that serves static files will work.
