Apex Treasure — apextreasure.com

GitHub source package for Cloudflare Workers

Put the contents of this folder at the root of the separate landing-page repository:
  wrangler.jsonc
  public/ (HTML, CSS, JavaScript, images, robots.txt and sitemap.xml)
  .gitignore
  README.txt

Cloudflare GitHub deployment
1. Workers & Pages > Create application > Import a repository.
2. Connect the landing-page GitHub repository and select the production branch.
3. Worker name: apextreasure-landing (must match wrangler.jsonc).
4. Root directory: repository root.
5. Build command: leave blank; this is a static site with no build step.
6. Deploy command: npx wrangler deploy
7. Save and Deploy. Cloudflare can then deploy new pushes automatically.

Only public/ is uploaded as website assets. Git metadata, configuration and
credentials stay outside that directory. No packages or build output are needed.

If deploying from a terminal, run npx wrangler deploy from this directory after
authenticating to the intended Cloudflare account.

Domain and SEO
Primary canonical domain: https://apextreasure.com/
After verifying the workers.dev preview, add apextreasure.com under the Worker's
Settings > Domains & Routes > Custom Domain. Set www.apextreasure.com to redirect
to the canonical host if www is also connected. Domain routing is a separate step.
Preserve existing email MX/TXT records when configuring the domain.
Submit https://apextreasure.com/sitemap.xml in Google Search Console once live.
Search indexing and rankings are determined by search engines.

Site behavior
Navigation menus scroll to sections on the same page. Detail buttons open the
relevant apextreasuresoftware.com page. Contact opens WhatsApp directly.
Unknown URLs use 404.html rather than returning the homepage.

Reference:
https://developers.cloudflare.com/workers/ci-cd/builds/
