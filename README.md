# merrowa-site

The static company site for https://merrowa.com/ (three pages, no build step, no dependencies).

## Publish (GitHub Pages)

1. Push this folder to a public GitHub repo and enable Pages for the default branch, root folder.
2. The `CNAME` file sets the custom domain to `merrowa.com`.
3. At IONOS, turn off the forwarding on `merrowa.com` and set these DNS records. Leave MX, SPF/TXT, and every subdomain record (`haya`, `wx`, mail) as they are.

   | Host | Type | Value |
   |---|---|---|
   | `@` | A | `185.199.108.153` |
   | `@` | A | `185.199.109.153` |
   | `@` | A | `185.199.110.153` |
   | `@` | A | `185.199.111.153` |
   | `@` | AAAA | `2606:50c0:8000::153` |
   | `@` | AAAA | `2606:50c0:8001::153` |
   | `@` | AAAA | `2606:50c0:8002::153` |
   | `@` | AAAA | `2606:50c0:8003::153` |
   | `www` | CNAME | `thundersnow9.github.io` |

4. In the repo's Pages settings, wait for the certificate, then tick "Enforce HTTPS". GitHub redirects `www` to the bare domain on its own.

## Preview locally

    python3 -m http.server 8766 --bind 127.0.0.1
