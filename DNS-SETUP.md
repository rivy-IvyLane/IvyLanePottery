# Domain Setup: IvyLanePottery.com

## Step 1 — Enable GitHub Pages

1. Go to the repository on GitHub → **Settings** → **Pages** (left sidebar)
2. Under **Build and deployment → Source**, select **Deploy from a branch**
3. Set branch to `main` and folder to `/ (root)`, then click **Save**
4. Under **Custom domain**, type `IvyLanePottery.com` and click **Save**
5. After DNS propagates, check **Enforce HTTPS** (GitHub auto-issues the certificate)

The `CNAME` file already in the repo root handles custom-domain identification automatically.

---

## Step 2 — Add DNS Records at Your Registrar

Log in to wherever you purchased **IvyLanePottery.com** (GoDaddy, Namecheap, Google Domains, etc.) and add the following records.

### A Records — apex domain (`IvyLanePottery.com`)

| Type | Name / Host | Value           | TTL  |
|------|-------------|-----------------|------|
| A    | @           | 185.199.108.153 | 3600 |
| A    | @           | 185.199.109.153 | 3600 |
| A    | @           | 185.199.110.153 | 3600 |
| A    | @           | 185.199.111.153 | 3600 |

### CNAME Record — `www` subdomain

| Type  | Name / Host | Value                             | TTL  |
|-------|-------------|-----------------------------------|------|
| CNAME | www         | `<your-github-username>.github.io` | 3600 |

> Replace `<your-github-username>` with the actual GitHub account username.

### AAAA Records — IPv6 (optional but recommended)

| Type  | Name / Host | Value                 | TTL  |
|-------|-------------|-----------------------|------|
| AAAA  | @           | 2606:50c0:8000::153   | 3600 |
| AAAA  | @           | 2606:50c0:8001::153   | 3600 |
| AAAA  | @           | 2606:50c0:8002::153   | 3600 |
| AAAA  | @           | 2606:50c0:8003::153   | 3600 |

---

## Step 3 — Verify

DNS changes can take up to 48 hours to propagate globally (usually much faster).

To check from the command line:

```
nslookup IvyLanePottery.com
```

Once GitHub detects the correct A records, it will issue a free SSL certificate and the site will be live at:

- `https://IvyLanePottery.com`
- `https://www.IvyLanePottery.com` (redirects to apex)

---

## Notes

- **Do not** add a CNAME record for the apex domain (`@`) — use A records only for the root.
- GitHub's IP addresses are static. Authoritative source: [GitHub Docs — Managing a custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
