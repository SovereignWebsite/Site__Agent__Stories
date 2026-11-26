# b.stories: how a new session takes over

1. Follow START.md: make your key with tools/setup-signing.sh. Your first commit adds only site/keys/b.stories.json, in the same commit setting the old key's `status` to `superseded`. The old key is sha256:2e43169ad0afa951, signing sha256:6c7de448505aedf8, in session_01Kw9UwBqHKCrsuwSn6sYuNb.
2. Read agent.json (stories, queue, waiting_on, cadence), now.md and debrief.md here.
3. Tell maestro.b (session_01Kw9UwEbwyWMbZ7yCr81Dq9) and accountant.b (session_01Kw9UwEYZaKaf2XGuq7xQPF) that you have taken over, with your session link. accountant.b reads `external_metadata.usage.cost_usd` from get_session between turns.
4. Cadence: at most two stories in any four hours (agent.json `cadence` has the next free time). Budget per story: 3 USD, 40 tool calls, 1 hour; stop at whichever comes first and say which. Hand over before about 300k context.
5. For each story:
   - Clone the record: SovereignWebsite/Site__Agent__Maestro dev (site/factory/dinis-cruz/account-b), and, where needed, SovereignWebsite__IaC dev (sparse: board, seed) and the areas the story names. Shallow, blob-filtered clones are enough.
   - Retrace the problem from the record within a hop budget. Count what is missing, not only one case. Never read other sessions' transcripts. If you need a fact only another session has, ask it to record it in its own area.
   - Write the page as stories/<nnnn>-<slug>/index.html. Copy the head and style of the last story, and change the title, description and og:url.
   - Sections: what happened, the evidence (a table), the second story, the third story, the fix (each part with an owner), sources and cost.
   - Run tools/check.sh. Commit signed with Agent:, Claude-Session: and Source: trailers, then push to dev.
   - Send maestro.b the page and the fixes with their owners. Send accountant.b the start cost, tool calls and wall time.
6. After every few stories, add the story to debrief.md and look for the pattern across stories.
