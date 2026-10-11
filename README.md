# forecode-policies

Part of the ForeCode test estate: the `forecode-ai` organisation's ForeCode policy repository. ForeCode reads it on
every change to the default branch and turns it into a new policy version (check run on the commit).

| Path | What |
|---|---|
| `guardrails/default/` | ForeCode's default pack, exported unchanged (`policy_check.py --export-defaults`) |
| `guardrails/org/` | The organisation's own guardrails: tests before production deploys, no SSH deploys to production, a rollout check for the digital department |
| `exceptions/` | A time-limited exception for `sample-legacy-risky` (expires within the 30-day production limit) |
| `admins.yaml` | Who may approve exceptions, per scope |
| `settings.yaml` | Environment aliases (`production` → `prod`) and exception limits |
| `ranking/` | Signal weights and a deprecation (SSH deploys are demoted) |

Check it locally from the ForeCode repository: `uv run python scripts/dev/policy_check.py PATH`.
