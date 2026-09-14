# Voter guide template — how to make a new state

`TEMPLATE.html` is the Maine file with clear comment markers around the
parts that change per state. Copy it, rename to `index.html` in the new
state's repo, and edit only what's inside these marked zones:

1. **`<title>`** — page title shown in the browser tab.
2. **STATE THEME** (top of `<style>`) — optional. The CSS variable
   *names* (`--pine`, `--blaze`, etc.) must stay the same; only the hex
   values need to change if you want a state-specific palette (a
   state's flag colors are a good starting point).
3. **STATE HEADER** (top of `<body>`) — the mascot SVG, the election
   date badge, and the eyebrow/title/tagline text.
4. **STATE CONTENT** (inside `<script>`) — the big one. This is the
   `FOOTER_NOTE` string plus the `DATA` array: one object per category
   (Register, Vote in person, Vote by mail, etc.), each holding a list
   of `{ q, a }` question/answer tiles. The pill nav at the top of the
   page is generated automatically from this array — you only ever
   edit `DATA`, never the pills markup directly.

Everything else in the file (the accordion behavior, the pill-filter
logic, the mobile layout) is the reusable engine and shouldn't need to
change.

## What content to bring per state

For each new state, the most reliable path is the same one we used for
Maine: a sourced document (or links to the state's Secretary of State
pages) covering, at minimum:
- Registration: where, deadlines (in person / mail / online / BMV /
  UOCAVA), what happens if you miss it
- ID requirements to register and to vote
- Polling place lookup tool (a real URL)
- Absentee/mail voting: how to request, deadlines, what to do with the
  ballot, tracking
- Military & overseas voting process
- Accessible ballot options
- A volunteer/poll-worker section if relevant
- A "still have questions" contact (helpline, Vote411, etc.)

Every fact that references a deadline, phone number, or link should
have a real source — either from the state's own election law/SOS
site, or from a document you provide. Claude can draft the HTML tiles
once given that sourced content, and can also do supplementary web
research to spot-check specific claims, but the state-specific facts
should come from a citable source rather than general knowledge, since
election law and deadlines vary by state and change over time.
