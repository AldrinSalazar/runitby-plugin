# Run it by

![Run it by](assets/logo.png)

Ask people outside the chat for answers or approvals by link. They answer on their phone with no sign-up, and Claude gets their answers back as JSON.

- **Forms for specific people:** shipping details, client intake, availability, RSVPs. Each person gets their own link, so every answer is attributed.
- **Open forms, surveys, polls and sign-up sheets:** one link to share anywhere, with a cap on responses.
- **Approvals and sign-offs:** named approvers, a policy (any, all, majority or a set number) and an optional email code for money, access or deletion. Claude acts only once the verdict is approved.

Claude can email each person their link in your account's name, preview the form at phone and desktop width before sending it, remind people who haven't answered, edit or extend a request, and close it. Pages work in English, Spanish, Portuguese, French, German, Italian, Japanese and Chinese.

## What's in the plugin

- **The Run it by connector** (`.mcp.json`): the remote MCP server at `https://runitby.app/mcp`, with seven tools: `createRequest`, `previewRequest`, `getStatus`, `listRequests`, `remind`, `updateRequest` and `closeRequest`.
- **The `ask-people` skill:** tells Claude when to reach for Run it by and how to pick the right kind of request, get each link to its person and read the answers back.

The plugin runs no local code. You sign in with your Run it by account the first time Claude connects; the Free plan includes 250 requests a month.

## What it sends and where

Everything goes to Run it by at `runitby.app` and nowhere else: the requests Claude creates (titles, questions, recipients' names and email addresses) and the answers people give. Run it by emails links and reminders only to the recipients Claude names, and only when asked to. Forms can't ask for passwords, card numbers or one-time codes, and every page shows who is asking.

- Docs: https://runitby.app/docs
- Privacy policy: https://runitby.app/privacy
- Terms: https://runitby.app/terms
- Support: https://runitby.app/support
