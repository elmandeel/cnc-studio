# CNC Studio automatic cloud AI (Gemini + Cloudflare Worker)

## Status
The frontend and Worker source are included in GitHub. **Cloud AI is disabled until an administrator deploys the Worker and configures its secrets and public site key.** Local diagnostics and 2D/3D simulation remain available.

## One-time administrator setup

1. Create a Gemini API key at https://aistudio.google.com/apikey. Check free-tier availability and set API quota/billing limits. Model configured: `gemini-3.1-flash-lite`.
2. Create a Cloudflare Turnstile widget that allows hostname `elmandeel.github.io`. Keep the **secret** private; its **site key** is public.
3. Deploy this Worker with Wrangler (requires a Cloudflare account):

```bash
cd worker
npx wrangler login
npx wrangler secret put GEMINI_API_KEY
npx wrangler secret put TURNSTILE_SECRET
npx wrangler deploy
```

4. Set repository `ai-config.json`:

```json
{
  "enabled": true,
  "endpoint": "https://YOUR-WORKER.YOUR-ACCOUNT.workers.dev/validate",
  "turnstileSiteKey": "YOUR_PUBLIC_TURNSTILE_SITE_KEY"
}
```

Never commit Gemini keys or Turnstile secrets. Check https://developers.cloudflare.com/workers/runtime-apis/bindings/rate-limit/ for rate-limit binding configuration.

## Automatic behavior
- The existing local program checks and 2D/3D simulation work regardless of cloud AI availability.
- Enter the assignment requirements once, then edit or import G-code.
- The AI panel waits **6 seconds** after edits stop. Subsequent changes trigger new reviews. It does not send a request on every keystroke.
- Cloud reviews use a **30-second minimum interval**, **12 per browser session hour**, server-side Turnstile verification and an approximate **3 requests/minute per IP** rate-limit binding.
- A visitor might occasionally need to complete a Turnstile challenge. No manual *Validate* click is required if verification succeeds.
- Optional **Review now** button and **Automatic review** toggle remain available.
- The AI report is advisory; any edits while an AI request is running cause obsolete results to be discarded. Local diagnostics still run independently.

## Privacy and security
Requests to Gemini contain G-code, assignment requirements, stock, G54, and local diagnostic text. Avoid personal student information or confidential test answers, especially if using the provider's free tier. Gemini free-tier prompts may be used for product improvement. CORS is not authentication. The Cloudflare Worker requires a verified one-use Turnstile token and rate limiting; configure provider quotas and monitor usage to mitigate public abuse. Neither AI nor the simulator certifies code correctness or real-machine safety.
