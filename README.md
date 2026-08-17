# Cantinarr, Unraid Community Applications template

The Unraid template for **[Cantinarr](https://github.com/windoze95/cantinarr)**, one app
over your whole media stack. This repository holds only the template. All the code,
docs, and issues live in the [main repository](https://github.com/windoze95/cantinarr).

| File | Purpose |
|---|---|
| `ca_profile.xml` | Repository profile shown in Community Applications |
| `templates/cantinarr.xml` | The app template Unraid installs from |

## Installing

Search **Cantinarr** in the **Apps** tab. The listing was approved on 2026-08-16 and
appears once the next Community Applications build publishes.

If it is not there yet, drop the template into Unraid's user-template folder
yourself. Unraid removed custom template repositories, so this is the manual path:

```bash
curl -o /boot/config/plugins/dockerMan/templates-user/my-cantinarr.xml \
  https://raw.githubusercontent.com/windoze95/cantinarr-unraid/main/templates/cantinarr.xml
```

Then go to **Docker > Add Container**, pick `Cantinarr` from the Template dropdown,
and Apply.

Two advanced fields are worth opening. **Public URL** is the origin your arrs POST
webhooks back to, so it has to be reachable from those containers. The read-only
**Media library** mount and **Media roots** work together to let signed-in users
download completed files, and both are blank by default, which keeps that off.

## Keeping it honest

Community Applications re-reads this repository on its own schedule, so a stale
template is wrong on an admin's first boot and no release gates it. Any change to
Cantinarr's published port, its `/config` contract, or an environment variable an
admin is expected to set has to land here too. `AGENTS.md` in the main repository
carries that rule.

## Support

- Problems go to the [issue tracker](https://github.com/windoze95/cantinarr/issues).
- Feature requests go to [cantinarr.com/roadmap](https://cantinarr.com/roadmap/), no account needed.

## License

AGPL-3.0, matching Cantinarr itself. See [LICENSE](LICENSE).
