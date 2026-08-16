# Cantinarr — Unraid Community Applications template

The Unraid template for **[Cantinarr](https://github.com/windoze95/cantinarr)**, a
self-hosted request and media-management front end for Radarr, Sonarr, and Chaptarr.

This repository exists only to hold the template. All the code, docs, and issues
live in the [main repository](https://github.com/windoze95/cantinarr).

| File | Purpose |
|---|---|
| `ca_profile.xml` | Repository profile shown in Community Applications |
| `templates/cantinarr.xml` | The app template Unraid installs from |

## Installing

Once Cantinarr is listed, install it from the **Apps** tab. Until then, drop the
template into Unraid's user-template folder yourself — Unraid removed custom
template repositories, so this is the manual path:

```bash
curl -o /boot/config/plugins/dockerMan/templates-user/my-cantinarr.xml \
  https://raw.githubusercontent.com/windoze95/cantinarr-unraid/main/templates/cantinarr.xml
```

Then **Docker > Add Container**, pick `Cantinarr` from the Template dropdown, and
Apply. It publishes port 8585 and keeps the database and encryption key in
`/mnt/user/appdata/cantinarr`.

Two advanced fields are worth opening: **Public URL**, the origin your arrs POST
webhooks back to, and the read-only **Media library** mount plus **Media roots**,
which together turn on completed-media downloads.

## Keeping it honest

Community Applications re-reads this repository on its own schedule, so a stale
template is wrong on an admin's first boot with no release to gate it. Any change
to Cantinarr's published port, its `/config` contract, or an environment variable
an admin is expected to set has to land here too — `AGENTS.md` in the main
repository carries that rule.

## Support

- **Bugs** — the [issue tracker](https://github.com/windoze95/cantinarr/issues)
- **Feature requests** — [cantinarr.com/roadmap](https://cantinarr.com/roadmap/), no account needed

## License

AGPL-3.0, matching Cantinarr itself — see [LICENSE](LICENSE).
