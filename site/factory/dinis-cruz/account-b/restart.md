# b.stories: how a new session takes over

1. Follow START.md: make your key with tools/setup-signing.sh. site/keys/b.stories.json already exists, so the signer check will NOT accept your replacement on its own (it accepts a new key only as a new file). Before the old session ends, ask it to commit your public key into that file, signed by its key (as soundcloud.b did in Site__Platform__SoundCloud 048b341). If the old session can no longer sign, ask Dinis in your own session for an owner override line: "Owner override: <his words>, <where>". Never push the key commit without one of these. Current key: session 2 (session_01Kw9UwFS5RW7qAM7VQztBa7), signing sha256:7f8a84800c7d1472.
2. Read agent.json (stories, queue, waiting_on, cadence), now.md and debrief.md here.
3. Tell maestro.b (session_01Kw9UwEbwyWMbZ7yCr81Dq9) and accountant.b (session_01Kw9UwEYZaKaf2XGuq7xQPF) that you have taken over, with your session link. accountant.b reads `external_metadata.usage.cost_usd` from get_session between turns.
4. Cadence: at most two stories in any four hours (agent.json `cadence` has the next free time). Budget per story: 3 USD, 40 tool calls, 1 hour; stop at whichever comes first and say which. Hand over before about 300k context.
5. For each story:
   - Clone the record: SovereignWebsite/Site__Agent__Maestro dev (site/factory/dinis-cruz/account-b), and, where needed, SovereignWebsite__IaC dev (sparse: board, seed) and the areas the story names. Shallow, blob-filtered clones are enough.
   - Retrace the problem from the record within a hop budget. Count what is missing, not only one case. Read the record first. Read other sessions' transcripts only when your start prompt or Dinis asks (story 0006 did), through read-only helpers, and never copy a secret. If you need a fact only another session has, ask it to record it in its own area.
   - Write the page as stories/<nnnn>-<slug>/index.html. Copy the head and style of the last story, and change the title, description and og:url.
   - Sections: what happened, the evidence (a table), the second story, the third story, the fix (each part with an owner), sources and cost.
   - Run tools/check.sh. Commit signed with Agent:, Claude-Session: and Source: trailers, then push to dev.
   - Send maestro.b the page and the fixes with their owners. Send accountant.b the start cost, tool calls and wall time.
6. After every few stories, add the story to debrief.md and look for the pattern across stories.

## Closing cost of the first session (session_01Kw9UwBqHKCrsuwSn6sYuNb)
- The last figure this session could read was cost_usd 5.251 USD, at 23:29 UTC 26 Nov, at the start of story 0003. The figure only updates between turns, so this session cannot see its own final number.
- First job of the next session: call get_session with session_id session_01Kw9UwBqHKCrsuwSn6sYuNb, read `external_metadata.usage.cost_usd`, and send it to accountant.b with your first report. That figure closes this session. Story 0003's cost is that figure minus 5.251.
