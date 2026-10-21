# PRD — bash-365-apex

> Product requirements for [`bash-365/bash-365-apex`](https://github.com/bash-365/bash-365-apex).
> Derived from the README, agent docs, config and code in this repo. Anything not
> stated in those sources is marked **TBD**; success metrics are proposals.

## 1. Overview / problem

Redirects the bare domain `bash-365.com` to `https://www.bash-365.com`, preserving the path. DNS is hosted in Microsoft 365, which lacks ALIAS/ANAME records, so the apex points at GitHub Pages and this repo answers with client-side redirects.

## 2. Target users

- Visitors typing the apex domain
- BASH Consulting (site owner)

## 3. Goals and non-goals

**Goals**

- Every apex URL lands on the same path on `www`

**Non-goals**

- Serving any content
- Existing once the apex moves to a DNS host supporting ALIAS records (retire then)

## 4. Core features (current)

- `index.html` redirect for `/`
- `404.html` path-preserving redirect for every other path
- `CNAME` binding the apex
- `.nojekyll` (files served as-is)

## 5. Requirements

**Functional**

- Redirect preserves path (and query: TBD)

**Non-functional**

- No build step; GitHub Pages hosting
- Note: with `.nojekyll`, repo files such as this PRD are publicly reachable on the apex

## 6. Success metrics (proposed — not defined in sources)

- Redirect success (no apex 404s)

## 7. Roadmap / open questions

- SEO impact of client-side vs server redirect: TBD

## 8. Links

- [README.md](README.md) · [AGENTS.md](AGENTS.md) · [CHANGELOG.md](CHANGELOG.md)
