# Agent: REX

**Description:**
REX is a lead generation and outreach automation agent — scraping prospects, enriching contact data, scoring leads, writing personalized cold outreach, and managing follow-up sequences so no lead ever goes cold.

**Type:** automation
**Enabled:** true

## Capabilities
- web_browsing
- lead_scraping
- contact_enrichment
- lead_scoring
- outreach_generation
- followup_sequencing
- pipeline_management
- data_cleaning
- deduplication
- telegram_notifications
- task_scheduling
- data_scraping
- csv_import_export

## Default Personality
PERSONALITY.md

## Settings
- maxConcurrentTasks: 2
- enableBrowser: true
- browserProfile: rex
- headlessBrowser: true
- logLevel: info
- autonomousMode: false
- note_autonomousMode: "Set to true to let Rex send outreach without asking for approval first. Default is false — Rex drafts and waits."

## Integrations


### LinkedIn
- enabled: false
- note: Optional — provide session cookie for LinkedIn scraping if needed
- sessionCookie: `${LINKEDIN_SESSION_COOKIE}`

### Hunter.io
- enabled: false
- note: Optional — used for email finding and verification
- apiKey: `${HUNTER_API_KEY}`

### Apollo.io
- enabled: false
- note: Optional — used for contact enrichment and company data
- apiKey: `${APOLLO_API_KEY}`

### Instantly / Lemlist / Smartlead
- enabled: false
- note: Optional — Rex generates outreach copy; connect your sending platform to push sequences directly
- platform: `${OUTREACH_PLATFORM_NAME}`
- apiKey: `${OUTREACH_PLATFORM_API_KEY}`

### Google Sheets
- enabled: false
- note: Optional — sync lead lists to/from Google Sheets
- credentialsFile: `${GOOGLE_SHEETS_CREDENTIALS_JSON_PATH}`
- spreadsheetId: `${GOOGLE_SHEETS_SPREADSHEET_ID}`

### HubSpot / Pipedrive / Notion CRM
- enabled: false
- note: Optional — push qualified leads and pipeline updates to your CRM
- platform: `${CRM_PLATFORM_NAME}`
- apiKey: `${CRM_API_KEY}`

## Lead Sources
- note: Add default lead source URLs or search configs here
- sources: []

## Browser Settings
- args:
  - --disable-dev-shm-usage
  - --disable-gpu
  - --single-process
  - --disable-background-networking
  - --disable-extensions
  - --disable-software-rasterizer
- maxConcurrentBrowsers: 1

## Data Paths
- leads: /app/data/rex/leads/
- sequences: /app/data/rex/sequences/
- campaigns: /app/data/rex/campaigns/
- enrichment: /app/data/rex/enrichment/
- reports: /app/data/rex/reports/
