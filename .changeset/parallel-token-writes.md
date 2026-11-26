---
'@cloudflare/workers-oauth-provider': patch
---

Reduce token endpoint latency. The authorization-code and refresh-token grants now write the
updated grant and the new access token to KV concurrently instead of one after the other. Responses
are unchanged, and a grant write failure still takes precedence over an access-token write failure.
