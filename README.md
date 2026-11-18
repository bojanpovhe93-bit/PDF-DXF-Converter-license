# PDF-DXF Converter license flag

This repo holds a single file, `license.json`, that the PDF-DXF Converter desktop app
checks (over HTTPS) at start-up, every 20 minutes while it is open, and before every
conversion, to decide whether it's allowed to run.

**To revoke access**: edit `license.json` on github.com (pencil icon → edit →
commit directly to `main`) and set `"enabled": false`. Every copy of the app
will stop working within 24 hours of that change (sooner if the machine is
online — 24 hours is only the outer bound for offline use).

**To restore access**: set `"enabled": true` again the same way.

`message` is shown to the user when access is disabled — edit it to whatever
you want them to see (e.g. contact info).

This repo must stay **public** — the app has no embedded credential to read a
private repo, and the flag itself contains nothing sensitive (just a
true/false and a message). Only people with push access to this repo can change it.
