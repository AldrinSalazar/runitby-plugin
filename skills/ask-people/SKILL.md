---
name: ask-people
description: Collect answers from people outside the chat by link with Run it by. Ask specific people for details (a shipping address, client intake, availability, an RSVP), make an open form, survey, poll or sign-up sheet, or get approval or sign-off from named people (human in the loop), then read the answers back.
---

# Run it by

Run it by sends a person a link. They answer on their phone with no sign-up, and the answers come back as structured data. Use it whenever the user needs something from someone who isn't in this conversation, instead of asking the user to relay the question.

## Pick the shape

- **One person or a known group (up to 50):** `createRequest` with `mode: "form"` and a named audience, so every answer is attributed.
- **Anyone with the link (surveys, polls, sign-ups):** `mode: "form"` with `audience: { kind: "open", maxSubmissions }`.
- **Sign-offs and votes:** `mode: "approval"` with named recipients and a `policy` (`any`, `all`, `majority` or `{ n }`). Add `approval.verify: "email"` when the decision moves money, grants access or deletes something.

Write the title and questions in the respondent's language and set `locale` to match. Set `requester` to how the user wants to introduce themselves. When the form matters, call `previewRequest` first: it returns phone and desktop screenshots and plain-language lint without creating anything.

## Get each link to its person

With `sendEmail: true`, named recipients with an email get their link by email; `links[].email` says what happened to each. Give the user every link that wasn't sent and say who it's for.

## Hear back

- `getStatus` with `wait` (up to 25 seconds) returns as soon as someone answers; call it again to keep waiting.
- `notifyEmail` emails the user a summary when someone answers or when the request ends, for when this conversation may be over.
- `listRequests` finds requests created earlier.

Act on an approval only when `verdict` is `"approved"`. `"declined"` and `"expired"` mean no.

## Follow up

`remind` emails the link again to people who haven't answered (once a day each). `updateRequest` edits a request until its first answer and adds people or extends the expiry until it ends. `closeRequest` stops a request that's no longer needed.

## What it won't do

Forms can't ask for passwords, card numbers, CVVs or one-time codes, and Run it by can't send payments.
