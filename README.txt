RICKY_EX_EMOT_BOT
============

Included:
- Premium dark/gold responsive frontend
- Lightweight CSS effects for smoother rendering on mobile devices
- Supplied favicon files in /static
- Supplied Emote_API.py Flask backend
- Render deployment configuration

RENDER SETUP
1. Keep Emote_API.py in the repository root (not inside static/).
2. In Render, open the RICKY_EX_EMOT_BOT service > Settings > Build & Deploy.
3. Set Start Command to: gunicorn Emote_API:app --workers 1 --threads 8 --timeout 120
4. Open the service's Environment page. Add these two variables:
   BOT_UID = your own authorized bot account UID
   BOT_PASSWORD = that account's password
5. Save changes, then use Manual Deploy > Deploy latest commit.
6. Check Logs. The missing-credentials error should disappear after both variables are set correctly.

IMPORTANT
- Never put BOT_UID or BOT_PASSWORD in frontend code, GitHub files, screenshots, or public messages.
- Do not send account passwords in ChatGPT or to anyone else.
- InfinityFree shared hosting does not run this Python Flask backend. This package targets Render.
- Render Free services can spin down after inactivity. The first request after idle may take around 50 seconds or more; this is a hosting cold start, not a frontend animation issue.
- The API uses a game client protocol and fixed client/version/region values from the supplied script. The game provider may change these at any time; successful deployment does not guarantee live emote delivery.
- The account nickname is not changed by this API. RICKY_EX_EMOT_BOT is used as website branding.
- Keep this service private and use it only where you have permission. A publicly exposed unauthenticated game-action endpoint can allow others to trigger requests.
