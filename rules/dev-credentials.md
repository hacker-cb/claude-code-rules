# Test credentials during development

**Credentials the project itself hands you are yours to type.** They arrive in
whatever form the project chose — a line in the docs, a seeded fixture, an
`.env.example`, the banner a start-up script prints — and a login for a service
you run for development (locally, or a throwaway environment the project
documents as such) is part of the dev loop, not a secret. Sign in with it
yourself and carry on: never stop to ask the user for that step, and never route
around it — checking something adjacent instead of the thing you were asked to
verify is not the same verification. The same holds for test credentials you
create along the way.

The boundary is the **origin of the secret, not the shape of the field**. Off
limits stays the user's own material: real passwords, API keys, tokens, payment
or identity data, and any credential for a service you did not stand up for
development. Those are never typed anywhere — ask the user instead.

Where the dev credentials aren't written down anywhere, ask for them once rather
than guessing at a default.
