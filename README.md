# highlevel ai chatbot setup: three setup paths compared, real monthly costs, and how to pick without wasting a month

Setting up an AI chatbot in HighLevel is not one task. It's at least three, depending on which setup method you pick, plus a fourth question almost nobody asks until the first invoice arrives: what does this actually cost once real leads start talking to it.

This walks through all of it in order — the three native setup methods inside HighLevel, the mode settings that decide whether your bot replies or just suggests, the current pricing across plans, and where the native tooling runs out of room. Then it covers what it takes to connect a purpose-built appointment-setting agent instead, because that's the fork in the road most agencies hit somewhere around month two.

## Before you open the bot builder, settle two things

Most failed setups aren't prompt problems. They're decisions that get made halfway through building.

**One: which sub-account owns the bot.** HighLevel creates Conversation AI bots at the sub-account level. If you're an agency with fifteen clients, that's fifteen separate bots to build, train and maintain unless you're running the agency-level tooling properly.

**Two: what the bot is allowed to do without asking you.** Booking on a calendar, updating contact fields, triggering workflows, handing off to a human — each of these is a configuration choice, and changing your mind later means re-testing everything.

Get those two answered and the actual build takes under an hour. Skip them and you'll rebuild twice.

## Path 1: Guided Form Setup

This is the beginner-friendly route, and for lead capture and booking it's usually enough.

The flow in HighLevel goes:

1. Open **AI Agents** → **Conversation AI** → **+ Create Bot**.
2. Choose **Guided Form Setup**.
3. Pick a bot type — **General Q&A** or **Appointment Booking**.
4. Select or create a **Brand Voice**.
5. Configure **Bot Settings** and **Bot Goals**.
6. Save.

You can stop there, or click into **Advanced Settings** to keep going. The appeal is that you're filling in fields rather than writing system prompts, and HighLevel builds the underlying instructions for you.

The trade-off is control. If your sales process has a branching question — "are you buying, selling, or both?" — a guided form won't express it cleanly.

## Path 2: Prompt Based Bot

Prompt Based gives you the personality, goals, model selection and actions in your own words. Templates exist, but note what HighLevel says about them: picking a bot template only populates the **Prompts** section. Everything else — training, goals, actions — is on you.

Use this when you want a specific tone, custom instructions, and actions like appointment booking, workflow triggers, human handover, stop bot, transfer bot, auto follow-up and conversation summaries.

Honest caveat from the official docs: prompt quality directly determines performance. There's no shortcut around learning to write them well, and HighLevel's own help center points you to its prompting guides for a reason.

## Path 3: Flow Based Builder

The Flow Builder is for logic that's hard to describe in a paragraph. You get visual branching, multi-step objectives and conditional paths.

The setup sequence:

1. **AI Agents** → **Conversation AI** → **+ Create Bot** → **Flow Based Builder**.
2. Configure **Bot Settings**, then **Bot Training**.
3. Open **Bot Goals** → **Launch Flow Builder**.
4. Set global behavior: tone, personality and style, conversation intent, additional business information, business context.
5. Add actions — stop bot, human handover, auto follow-up.
6. Configure appointment options, enable conversation summaries if you want them.

If you've used a workflow builder before, this feels familiar. If you haven't, budget a couple of hours for the first build.

## Don't skip the mode setting

A newly saved bot is often set to **Off**. That's not a bug — it's the part of the setup most people rush past.

- **Off**: bot exists, does nothing.
- **Suggestive**: generates replies for your team to review and send manually.
- **Auto-Pilot**: sends replies automatically.

The sensible sequence is Build → Suggestive → read a week of real conversations → Auto-Pilot. Test lead capture, FAQs, booking, and specifically what happens when a lead asks something the bot can't answer. That last case is where native bots either flag you or confidently invent something, and the difference matters a lot when the invented thing is a discount.

## What native Conversation AI costs at scale

HighLevel prices AI in three ways, and this is where the setup decision turns into a budget decision.

| HighLevel AI plan | Price | Conversation AI included |
| --- | --- | --- |
| Pay-Per-Use | Token cost only | At token cost |
| AI Employee Growth | $50/month per enabled location | 1,000 agent responses/month, then pay-per-use |
| AI Employee Unlimited | $97/month per enabled location | Unlimited, subject to fair use |

Two details that change the math:

**Conversation AI is token-billed, not message-billed.** Cost depends on input tokens (customer messages, history, instructions, knowledge base content) and output tokens (the replies). HighLevel's own example: 100,000 input tokens and 25,000 output tokens on GPT-5 pricing works out to roughly $0.375 for that conversation. A chatty conversation with a large knowledge base costs more than a short one on the same model. That's fine — but it's not predictable, which is a problem when you're quoting a client a flat monthly fee.

**Rebilling requires the $497/month agency plan.** If you're selling AI to clients, that's a real line item on top of whatever the locations cost.

Do the arithmetic on a handful of sub-accounts and AI Employee Unlimited gets expensive fast: at $97 per location, ten locations is $970/month before you've charged anyone anything.

## Where the native setup runs out of room

None of this is a knock on HighLevel's bot. It's a general-purpose feature inside an all-in-one platform, and it behaves like one. The friction points that show up at scale:

- Bots are sub-account specific. Handoffs between bots are workable but clunky, and each bot books to a single calendar.
- No image understanding. If a lead sends a photo — a room, a damaged part, a listing — the native bot can't work with it.
- Custom field updating has historically been capped, though HighLevel has raised that limit.
- The prompting is a black box. When output quality drifts, you're debugging behavior you can't read.

If your AI is a side feature of your service, that's all manageable. If AI appointment setting *is* the service you sell, those limits show up in client churn.

## The other route: build the agent outside HighLevel and connect it

This is where a tool like CloseBot enters the picture, and it's worth understanding the architecture before the pricing.

CloseBot is a conversational AI platform that connects to your CRM and takes over the text channels already flowing through it. It supports HighLevel, HubSpot, LeadConnector and custom CRMs. It does not connect to Instagram or WhatsApp directly — your CRM owns those connections, and CloseBot answers the conversations that land there.

The HighLevel connection is OAuth-based:

1. Go to the **Sources** page in CloseBot and add a new source.
2. Select **HighLevel Sub-Account** → **Connect**. An OAuth popup opens.
3. Approve permissions and choose the sub-account you want to connect.
4. Return to CloseBot, click **Add Source**, and confirm the source appears in the list.

The first agent is auto-created for you on registration based on the industry you pick, so you're not starting from a blank canvas.

After that, the build is three pieces:

**Persona** — the voice. You set an avatar and color (internal only), a name, response behavior like extra reply delay, occasional typos and message splitting, plus up to three voice style words and free-form instructions. Typos and message splitting automatically drop to 0% on email channels, which is a sensible touch. You also pick a primary AI provider and any number of fallbacks, so a provider outage doesn't take your agent down with it.

**Job Flow** — the actual work. This is a drag-and-drop builder with nodes for objectives, conversation, custom scenarios and bookings. A basic flow collects name and email in one objective node, drops into a conversation node to answer questions, and jumps to a booking node when the lead asks for a demo. Deeper flows branch on what the lead says and route to different calendars.

**Knowledge Library** — the reference material your agent pulls from when answering questions.

Worth knowing: OpenHighLevel and HubSpot are the native integrations, and CloseBot also does a pass-through on things like Stripe payments and property data lookups inside the conversation.

Some users on G2 do flag a learning curve during initial setup, and that complaint shows up in agency communities too. The drag-and-drop builder is more capable than a prompt box, which is exactly why it takes an afternoon rather than ten minutes.

## CloseBot plans, in full

CloseBot splits into a business track and an agency track, and all four tiers are live on the plans page.

| Plan | Price | Billing | Messages | Notable inclusions |
| --- | --- | --- | --- | --- |
| [ Free plan](https://app.closebot.com/a?fpr=li87) | $0 | Always free | 100/month | 1 agent, 1 user seat, 1 MB storage, unlimited account connections |
| [ Core (Business)](https://app.closebot.com/a?fpr=li87) | From $64/mo monthly; $53/mo equivalent on annual, billed as $640/yr | Monthly or annual | Costs included in base price; scales by volume tier | 15+ templates (50+ on annual only), human support, $5 per extra seat, add-on storage and agents |
| [ Core (Agency)](https://app.closebot.com/a?fpr=li87) | $397/mo monthly; around $331/mo equivalent on annual | Monthly or annual | Unlimited messages at $0.012 each, rebillable | White-label client portal, rebill all costs, unlimited agents and sources |
| [ Growth](https://app.closebot.com/a?fpr=li87) | Custom quote | Custom | High volume | HIPAA compliance, quarterly audits, 99.99% priority uptime, priority support, 50+ templates |

The business track scales with monthly message volume rather than agent count, which is the part to study before committing:

| Monthly messages | Core (Business) price |
| --- | --- |
| 100–500 | $64/mo |
| 1,000 | $84/mo |
| 2,000 | $109/mo |
| 5,000 | $176/mo |
| 20,000 | $454/mo |
| 50,000 | $806/mo |
| 100,000 | About $1,059/mo |

Three practical notes from CloseBot's own documentation:

**A message is a segment — usually.** One message equals one segment, except when you switch on the Agent Node's unlimited potential (many tools, unlimited instruction size), where billing moves to token costs and a single message can consume several segments.

**Overages work differently per plan.** On the free plan, messages beyond 100 cost $0.08 each. On business plans, your ceiling is 500 messages by default and going over is billed at a 2x overage rate drawn from a wallet you top up.

**There are no refunds.** What exists instead is the free-forever tier under 100 messages and a 7-day trial of any paid plan. Plans are month to month with no contract.

Storage follows the same pattern: 1 MB is included on free and business plans, business add-on storage runs from roughly $0.10 to $3.00 per MB per month depending on how much you buy, and agency accounts pay $0.006 per MB per day, rebillable with markup.

## Native HighLevel bot vs a dedicated agent

Same job, different shapes. This is the comparison that actually decides it.

|  | HighLevel Conversation AI | CloseBot |
| --- | --- | --- |
| Where the bot lives | Inside HighLevel, per sub-account | Inside HighLevel, HubSpot, LeadConnector or custom CRM |
| Build method | Guided form, prompt-based, or Flow Builder | Persona + drag-and-drop Job Flow |
| Pricing model | Token-based; $50 or $97/month per location for AI Employee plans | Tiered by message volume; flat $397/mo agency plan |
| Rebilling | Requires the $497/month agency plan | Built into the agency plan, client portal white-labeled |
| Image handling | No | Yes, on inbound images |
| AI provider choice | Set by HighLevel | Five providers with automatic fallback |
| Learning curve | Lower to start | Steeper, more control |

Two things worth flagging honestly. First, CloseBot's own comparison content is vendor material — the split-testing claims in it come from the company, not an independent audit. Second, the cheapest line in that comparison table is misleading on its own: the pay-per-use conversational AI option at HighLevel can price lower than CloseBot at low volume, but it doesn't include the agency tooling, the multi-agent routing or the white-label portal.

## How to choose without overthinking it

**Use the Guided Form setup** if you need a lead capture bot, appointment booking and FAQs on one or two locations, and you want it live today. It's the fastest path and it's free to try.

**Use Prompt Based or Flow Builder** if your sales conversation has branches and you're willing to maintain it. Budget for prompt iteration; expect the first version to be mediocre.

**Look at a dedicated agent platform** if any of these describe you: you're selling AI setting to clients under your own brand; you're paying $97 per location across enough sub-accounts that the bill hurts; you need one agent handling many sub-accounts; or you need behavior you can see and debug rather than a black box.

**Ignore all of it** if your leads arrive as Instagram DMs and you don't run a CRM. CloseBot connects to CRMs, not channels. Adding a CRM to run an agent is a real cost — HighLevel Starter is $97/month on top of the agent subscription — and for a solo operator that usually isn't the right shape.

## Setup checklist worth keeping

Whatever you build on, these decisions come back around:

- **Calendar first.** No configured calendar, no booking. Confirm which calendar the bot writes to and whether appointment types differ.
- **Training material second.** Garbage knowledge base, garbage answers. Keep uploads tight and factual; storage is billed on text size.
- **Channel scope third.** Which channels is the bot allowed to respond on — SMS, email, chat widget, social DMs? Scope it before it goes live, not after it replies to something odd.
- **Escalation last.** Decide what happens when the bot is unsure. Notification to a human beats a confident guess.
- **Then test in Suggestive mode for a week.** Read the actual transcripts. This is the step people skip and the one that catches the most problems.

The setup itself is rarely the hard part. Knowing what you want the bot to refuse to do is.
