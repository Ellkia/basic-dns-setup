# Basic DNS Setup

Project: https://roadmap.sh/projects/basic-dns

## Description
Setting up a custom domain name and configuring DNS records for both 
a static site server and GitHub Pages.

## Domain
`elka-lab.xyz` purchased on Porkbun

## Task 1 - Custom Domain for GitHub Pages

### DNS Records added on Porkbun
| Type | Host | Answer | TTL |
|---|---|---|---|
| A | pages | 185.199.108.153 | 600 |
| A | pages | 185.199.109.153 | 600 |
| A | pages | 185.199.110.153 | 600 |
| A | pages | 185.199.111.153 | 600 |

### GitHub Pages Configuration
- Go to repo Settings → Pages → Custom domain
- Set custom domain to `pages.elka-lab.xyz`

### Result
GitHub Pages site accessible at: https://pages.elka-lab.xyz/gh-deployment-workflow/

## Task 2 - Custom Domain for GCP VM (Nginx)

### Reserved Static IP on GCP
Promoted ephemeral IP to static to avoid IP changes on VM restart.

### DNS Records added on Porkbun
| Type | Host | Answer | TTL |
|---|---|---|---|
| A | (blank) | <SERVER_IP> | 600 |
| A | www | <SERVER_IP> | 600 |

### Result
Static site accessible at: http://elka-lab.xyz

## Key Learnings
- DNS records types: A record
- Difference between root domain (@) and subdomains
- TTL and DNS propagation
- How to point a domain to different servers using subdomains
- Ephemeral vs static IPs on GCP
- GitHub Pages custom domain configuration
