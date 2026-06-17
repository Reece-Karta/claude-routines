# Inbox Cleanup Routine — Instructions

Use this as the routine's instruction text:

---

Scan my reece@kartahealthcare.com Inbox for **read** emails only. Leave all unread emails untouched in the Inbox.

For each read email:

1. Read the full email content (subject, sender, body)
2. Auto-categorize it into one of these folder recommendations based on content:
   - **Clients** — emails from or about specific clients, patient-related correspondence
   - **Finance** — invoices, budgets, expense reports, payment confirmations
   - **HR / People** — leave requests, onboarding, team updates, performance reviews
   - **Compliance / Legal** — regulatory updates, policy changes, audit-related items
   - **IT / Systems** — system notifications, outage reports, access requests, technical updates
   - **Projects** — project updates, milestones, deliverables, status reports
   - **Internal Comms** — company-wide announcements, all-staff emails, meeting notes
   - **Newsletters / Marketing** — external newsletters, promotional content, subscriptions
   - **Archive** — catch-all for anything that doesn't fit the above but has been dealt with
3. Assign a confidence level: High, Medium, or Low
4. Note if the email has attachments

## Output

Generate a complete HTML file using the template in `inbox-cleanup-template.html` in this repository. Specifically:

- Update the cleanup date/time in the header
- Set the stat card counts to match the actual number of emails per category
- Replace example email cards with real emails, grouped by category
- Include the suggested folder name in a `.folder-tag` span on each card
- Include confidence level in a `.confidence` span
- Mark emails with attachments using a `.has-attachment` indicator
- If no read emails are found, show a single `.empty-state` div saying the inbox is clean
- Omit any category section that has zero emails

After generating the HTML, write it to `inbox-cleanup.html` in this repository and commit and push to the main branch with the message "Update inbox cleanup report — [date and time]".

## Important Notes

- **Never touch unread emails** — they must remain in the Inbox
- Paginate through all read emails (up to 25 per request) to get a complete picture
- If an email could fit multiple categories, pick the most specific one
- Use the email subject, sender domain, and body content to inform categorization
