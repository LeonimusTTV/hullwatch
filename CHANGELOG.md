# Changelog

All notable changes to HullWatch. The same notes are published at [hullwatch.dev/changelog](https://hullwatch.dev/changelog).

## 1.4.2 (October 19, 2026)

### Notifications

- Mute an item for 1 hour, 4 hours, until tomorrow morning, 24 hours, a week, or until you unmute it. If it's still failing when the time is up, you get a "Still failing" notification
- Pause all notifications from the menu bar icon's right-click menu or from Settings. The panel shows "Paused" until you resume
- Quiet hours, with times and days: notify without sound, don't notify, or get a summary when they end. Critical problems can still come through
- Problems remember when they started, and recovery notifications say how long they lasted ("Back to healthy after 7 min")
- Fixed muting a Proxmox usage alert from the problems banner

### Destinations

- Send alerts to ntfy, Discord, Slack (and Mattermost or Rocket.Chat), Microsoft Teams, Telegram, Pushover, Gotify or any JSON webhook
- For each destination, choose the events, the minimum severity and the alert channels, and whether it follows pauses and quiet hours (turn that off for an on-call destination)
- Credentials stay in your Keychain. Send a test, see how the last delivery went, and failed deliveries are retried once

### Activity

- New Activity section: ongoing problems and how long they've lasted, recent alerts, and a log of the actions you ran from HullWatch, failures included
- Keep 7 to 365 days of history, export it as CSV or Markdown, or copy the last 24 hours as Markdown for a post-mortem

### Uptime

- TCP, ping and DNS checks (with an optional expected answer), alongside HTTP(S)
- HTTP options: method, expected status codes ("200-299, 401"), a keyword that must or must not be in the body, headers (stored in your Keychain), redirects, self-signed certificates and timeout
- Consecutive failures before alerting, shown as "1/3" in the meantime
- 24-hour uptime percentage and a latency sparkline for each check
- Fixed Check now, which now runs that one check

### Service status

- Instatus and Better Stack status pages, alongside Atlassian Statuspage and incident.io, detected automatically
- Ongoing maintenance, and maintenance planned in the next 2 days, shown next to the service, with the affected components in the tooltip
- Optional alerts for minor incidents and maintenance. New suggestions: Render, Fly.io, Supabase and DigitalOcean

### Proxmox

- Several hosts or clusters. Your current host moves over automatically, with its token, alerts and mutes
- Nodes (online, CPU, memory), storage usage (shared storage listed once), and failed backups or backups with warnings over the last 1 to 30 days
- New alerts for nodes, storage (with a threshold you choose) and backups
- Take a snapshot of a guest, and open nodes and tasks in the web interface
- CPU sparkline for running guests, and a disk usage alert for containers
- Fixed an online node being shown as "Offline" when the token can't read its usage

### Pterodactyl

- Several panels. Your current panel moves over automatically
- Backups, checked every 30 minutes: age of the latest one in the row, an alert when it failed, and an optional alert when the last successful one is more than a few days old
- CPU, memory and disk alerts against each server's limits
- CPU sparkline, and an Open backups action

### Docker

- Containers grouped by Compose project. Start, restart or stop a whole project, pull and recreate it, follow its logs, open its folder in Terminal or your editor, or take it down
- Pull and recreate a single service from its container
- Docker contexts (Docker Desktop, OrbStack, Colima, remote hosts over SSH), picked from the section or Settings
- CPU and memory of running containers, with a sparkline

### Kubernetes

- Nodes (Ready, cordoned, memory and disk pressure), with their own alerts
- Running and failed jobs, with logs and delete, and their own alerts. Only each cron job's latest run counts, so an old failure followed by a success isn't a problem anymore
- Cron jobs: schedule, last success, Run now and Suspend / Resume
- Recent Warning events
- Watch other contexts: their failing pods and deployments raise alerts even while another context is shown
- New Kubernetes settings page

### GitHub

- My pull requests: checks on the latest commit, review decision and draft state, with an alert when checks fail
- Latest release in the tooltip and as an action
- Open Dependabot alerts (optional)
- Re-run the failed jobs of the latest failed run

### GitLab

- Several instances, gitlab.com and self-hosted. Each project picks its instance, and your current setup moves over automatically
- Sign in with a GitLab application (OAuth) instead of a personal access token, for instances that delete tokens after a day. No client secret needed, the session renews itself, and you're alerted if it ever needs a new sign-in
- A pipeline that passed with warnings now shows yellow instead of green, in GitLab and in Git repos

### Deployments

- Cloudflare Pages, Render and Fly.io, alongside Vercel and Netlify
- Cloudflare Workers: each Worker's live deployment, gradual deployments, and the latest Workers Builds build, with an alert when it fails
- Test connection for every provider: shows the projects found, the exact error, or a warning when the connection works but returns no projects
- Cloudflare Pages projects that were never deployed now show up

### Git repos

- CI status of the current commit, from GitHub Actions or GitLab pipelines. A failed run turns the repo red
- Pull (fast-forward only), open on GitHub or GitLab at the current branch, open the CI run, and copy the branch name

### Mac

- Command palette (⌃⌥⌘K by default): search every action of every item, and HullWatch's own commands
- Widgets: HullWatch Status in three sizes, and a HullWatch Section widget for the section you choose
- Shortcuts, Spotlight and Siri: count and list problems, refresh, open the panel filtered, pause or resume, show or hide a section, switch profile
- hullwatch:// links to open, filter or refresh the panel, open Settings, pause or resume, run a check, and more
- Profiles (like Work, Home or On call), each with its own sections and, if you want, its own alerts
- Pin items to the top of the panel
- Show the problem count or a section's badge next to the menu bar icon
- Panel sizes (compact, large, tall), and a detachable panel in a window you can resize and keep on top
- Export and import your settings. Tokens are only included with a password and are encrypted
- First launch finds Docker, kubectl, Homebrew and your git repos, and helps you connect your services

## 1.3.0 (October 5, 2026)

- Added Pterodactyl support
- Added Proxmox server management with alerts when CPU or memory usage stays too high for a period of time

## 1.2.0 (October 1, 2026)

- Added icons for GitLab and Git
- Added dark icons
- Replaced the app icon in the menu bar with the HullWatch logo

## 1.1.0 (September 30, 2026)

- Update system

## 1.0.0 (September 28, 2026)

- Initial release
