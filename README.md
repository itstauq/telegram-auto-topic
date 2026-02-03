# Telegram Auto-Topic

An [OpenClaw](https://openclaw.ai) skill that turns Telegram messages into forum topics instantly.

Add `/topic` to the start of any message in a Telegram forum group → a new topic is created from it. The title is figured out from your message automatically — no need to think of one yourself.

## Example

**1.** You send a message starting with `/topic`:
> /topic I need to look into renewing my passport before March

**2.** A new forum topic **"Passport Renewal Before March"** is created with your message quoted inside it. You get a reply linking directly to the new topic.

## Install

```bash
clawhub install itstauq/telegram-auto-topic
```

Or manually — clone this repo into your OpenClaw skills directory.

## Prerequisites

- The group must be [configured in OpenClaw](https://docs.openclaw.ai/channels/telegram) (`channels.telegram.groups.<CHAT_ID>`).
- The group must have **forum/topics** enabled.
- Your bot must be an admin in the group with **Manage Topics** permission.

## How It Works

1. You send a message starting with `/topic`
2. A new forum topic is created — titled from your message automatically
3. Your message is quoted in the new topic with your name
4. You get a reply with a clickable link to the new topic
5. The bot responds to your message in the new topic

Works with media too — photos, videos, or documents with `/topic` in the caption get forwarded into the new topic.

## Optional: Telegram autocomplete

To get `/topic` in Telegram's autocomplete menu, add this to your OpenClaw config under `channels.telegram`:

```json
{
  "customCommands": [
    {
      "command": "topic",
      "description": "Create a new forum topic from a message"
    }
  ]
}
```

## License

MIT
