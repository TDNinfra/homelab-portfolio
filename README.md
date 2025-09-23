# IT & Homelab Portfolio (TDNinfra)

This repository powers my public portfolio site (GitHub Pages) and showcases practical DevOps/sysadmin work:
Dockerized services, secure access with Cloudflare Zero Trust, reverse proxies with TLS, media automation, and self-hosted apps.

- **Live site:** https://tdninfra.github.io/homelab-portfolio/
- **Highlights:** Docker, Compose, Reverse Proxy, Cloudflare, Backups (B2), Plex/Arr stack, Immich, Vaultwarden

## Structure
```
/index.md                   # homepage (Jekyll)
/services/                  # all projects
  <service>/
    README.md               # what/why/integration/security/usage
    docker-compose.yml
    .env.example
    [extra configs]
_includes/
  header.html               # top nav
  footer.html               # footer (repo link + last updated)
```

> All configs are **sanitized**; no personal names, domains, IPs, or secrets are published.

## Local preview (optional)
If you want to preview the site locally with Jekyll:
```bash
gem install bundler jekyll
bundle init
bundle add jekyll
bundle exec jekyll serve
```
(Or just push to GitHub and let Pages build it.)
