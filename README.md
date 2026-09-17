# Review Leaderboard display page

A single static page (`index.html`) that renders a team leaderboard on a 16:9 TV.
It is laid out on a fixed 1920 x 1080 canvas and scaled to whatever viewport the
TV browser reports, so it looks the same on every device.

The page holds no data. It reads a JSON feed whose address is passed in the
query string:

```
https://<host>/index.html?src=<feed URL>
```

Only `https://script.google.com/macros/...` feeds are accepted. The page refreshes
every 30 minutes and reloads itself once a day.

Feed shape:

```json
{
  "entries":   [{ "rank": 1, "name": "Name", "reviews": 9 }],
  "totals":    { "reviews": 14, "participants": 3, "goal": 30 },
  "unclaimed": 1,
  "contestEnd": "2026-10-14T23:59:59",
  "updatedAt":  "2026-09-17T17:31:10Z"
}
```
