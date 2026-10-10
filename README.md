# bash-365-apex

Redirects the bare domain `bash-365.com` to `https://www.bash-365.com`, keeping the path.

DNS for `bash-365.com` is hosted in Microsoft 365, which has no ALIAS/ANAME records, so the
apex cannot point at the Azure Static Web App that serves `www`. The apex A/AAAA records point
at GitHub Pages instead, and this repo answers there with a client-side redirect (`index.html`
for `/`, `404.html` for every other path).

Retire this repo if the apex ever moves to a DNS host that supports ALIAS records.
