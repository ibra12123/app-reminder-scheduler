# App reminder scheduler

GitHub Actions job that calls the protected scheduler endpoints of Accord and Reflect every 30 minutes,
so automatic reminders and queued emails are sent even while the apps are idle (scaled to zero).

| Secret (Settings > Secrets and variables > Actions) | Must equal the app's Neander Environment value |
|---|---|
| `ACCORD_JOB_TICK_SECRET` | Accord `JOB_TICK_SECRET` |
| `REFLECT_CRON_SECRET` | Reflect `CRON_SECRET` |

To move it to another account: copy `.github/workflows/tick.yml`, add the two secrets, and run the workflow once
from the Actions tab (Run workflow). Every run's log shows each app's HTTP status and job summary.

Schedule: every 30 minutes at :07 and :37 UTC (GitHub may delay scheduled runs by a few minutes under load).
