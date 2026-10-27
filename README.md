# Noname Active Testing — 30 API Security Lab

## What this is
A deliberately insecure training API with synthetic data and 30 core API scenarios. Several high-risk behaviors are simulated rather than executed (SSRF does not make outbound requests; upload does not write files; XML does not invoke a parser; search does not execute SQL; transfers do not move money).

**Use only in an isolated environment you control and have permission to test. Do not connect real customer data, production systems, cloud metadata, internal networks, or real payment services.**

## Deploy on Render
1. Create a new GitHub repository and upload these files.
2. In Render, choose **New + → Web Service**, connect the repository.
3. Select **Docker** runtime (or use the included `render.yaml` blueprint).
4. Deploy. Render assigns a public HTTPS URL such as `https://noname-api-security-lab-xxxx.onrender.com`.
5. Open `https://YOUR-RENDER-HOST/docs` to see interactive API docs and `https://YOUR-RENDER-HOST/openapi.json` for the generated spec.
6. Replace `https://YOUR-RENDER-HOST` in the provided Swagger file's `servers[0].url` with the actual Render URL before importing to Noname.

## Test credentials
- User: `avery@example.test` / `demo123`
- Admin: `blair@example.test` / `admin123`
- Lab tokens: `demo-user-token`, `demo-admin-token`
These are intentionally predictable training credentials. Never reuse them elsewhere.

## Base URL
Use the Render service root URL, e.g. `https://noname-api-security-lab-xxxx.onrender.com`.
Do not use `/docs` or `/openapi.json` as the Base URL.

## Notes
- This lab exposes intentionally weak behaviors. Keep it isolated, use synthetic data, and delete the service after the demo.
- A scanner may not report every scenario; findings depend on Noname version, test configuration, authentication, and test coverage.
