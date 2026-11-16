SURYA ASSOCIATES — CLOUDFLARE PAGES PACKAGE (FIXED V2)

PACKAGE CONTENTS
- index.html
- data/products.json
- functions/api/chat.js
- wrangler.toml
- README_MALAYALAM_ENGLISH.txt

IMPORTANT DEPLOYMENT FIX
The previous build log shows that Cloudflare ran:
    npx wrangler deploy

That is the Workers deploy command. This project is a Cloudflare Pages project
(the wrangler.toml file contains pages_build_output_dir = ".").
Use the Pages deploy command instead:

    npx wrangler pages deploy . --project-name=surya-associates-shop-assistant

Cloudflare dashboard values for the connected Git build:
- Build command: leave blank
- Deploy command: npx wrangler pages deploy . --project-name=surya-associates-shop-assistant
- Root directory: /
- Do not use: npx wrangler deploy

If the dashboard rejects a blank Build command or shows "Invalid request body",
do not repeatedly save random values. Keep the Build command as the dashboard's
default/empty value and set the Deploy command exactly as shown above.

GITHUB FILE STRUCTURE
index.html
wrangler.toml
data/
  products.json
functions/
  api/
    chat.js

AI SECRET
In Cloudflare, add OPENAI_API_KEY as a SECRET for the Production environment.
Optionally add OPENAI_MODEL as a variable (default: gpt-4.1-mini).
Do not put the API key in index.html, products.json, or chat.js.
After changing secrets, redeploy.

LOCAL PREVIEW
1. Extract this ZIP.
2. Open index.html in Chrome.
3. The product catalogue and website UI can be previewed locally.
4. The secure AI chat endpoint requires Cloudflare Pages deployment and OPENAI_API_KEY.

CATALOGUE NOTICE
The catalogue contains 176 product records. Verify model names, prices, stock,
warranty, and specifications with the shop before publishing. These are not live
inventory values.

This package is a website project, not Raspberry Pi GPIO/servo hardware code.
