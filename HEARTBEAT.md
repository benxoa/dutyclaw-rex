# HEARTBEAT.md – Rex (Lead Agent)

# Scheduled automation tasks that Rex runs periodically.
# Rex MUST notify the user via Telegram after every heartbeat run.

## Daily Tasks (run every morning at 7:30 AM user timezone)

- TASK: pipeline_status_report
  description: Scan the lead database for all active leads. Summarize: how many are in each stage (new, contacted, replied, qualified, dead), which leads need action today, and which sequences are running. Send morning pipeline briefing to user.

- TASK: followup_dispatcher
  description: Check all active outreach sequences. Identify any leads that are due for a follow-up message today based on their sequence schedule. Generate follow-up messages and notify user for approval before sending (or auto-send if user has enabled autonomous mode).

- TASK: lead_freshness_check
  description: Flag any leads that have been in the same pipeline stage for more than 5 days without activity. Alert user with suggested next action for each stale lead.

## Weekly Tasks (run every Monday at 8:00 AM)

- TASK: new_lead_scrape
  description: Run the user's saved lead search criteria against configured sources (Google Maps, LinkedIn, niche directories). Add new leads to the database, deduplicate against existing records, score them, and report how many net-new qualified leads were added.

- TASK: lead_source_performance_review
  description: Analyze which lead sources produced the most responses and conversions last week. Recommend doubling down on top sources and pausing underperforming ones.

- TASK: outreach_performance_report
  description: Summarize email/message open rates, reply rates, positive reply rates, and meeting booking rates for the past 7 days. Identify best-performing subject lines and openers. Recommend copy adjustments.

## On-Demand Triggers (user can say any of these)

- "Scrape leads from [source] for [niche/location]"
- "Enrich this lead list" _(attach CSV)_
- "Write cold outreach for [product/service] targeting [ICP]"
- "Build a 5-step follow-up sequence for [campaign]"
- "Score my lead list"
- "What's my pipeline status?"
- "Who should I follow up with today?"
- "Find decision-makers at [company/industry]"
- "Clean and deduplicate my contacts" _(attach file)_
