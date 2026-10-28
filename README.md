# RESOLVO-
AI-powered WhatsApp complaint resolution for Nigerian fintechs and banks.
Customers who face a failed transfer, a missing reversal or a duplicate charge usually wait hours or days for support. Resolvo answers on WhatsApp in seconds. It resolves safe queries automatically and sends anything involving money, fraud or an upset customer to a human agent.
How it works
A customer sends a complaint on WhatsApp (Twilio).
An n8n webhook receives it.
GPT-4o-mini classifies the complaint (category, sentiment, urgency).
The transaction is looked up in Airtable.
A Switch node decides: auto-resolve (Tier 1) only if the category is on the approved whitelist AND sentiment is not negative AND urgency is not high. Anything touching money, fraud or negative sentiment goes to a human agent (Tier 2) with a case summary.
Every case is logged in Airtable.
Proactive monitoring
A scheduled workflow scans transactions for stuck transfers, failed reversals and duplicate charges, so customers can be told before they complain.
Stack
n8n, OpenAI GPT-4o-mini, Airtable, Twilio WhatsApp API.
Safety design
AI never acts on money. Auto-resolve is limited to informational queries only.
Roadmap
Pidgin, Yoruba and Hausa support. Voice note transcription. Plain-language explanations of why a transaction failed. Live trust and impact counter.
Status
Working prototype. Built by Daniel Ogungbemi, Ibadan, Nigeria.
