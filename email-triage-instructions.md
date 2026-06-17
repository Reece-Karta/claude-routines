# Email Triage Routine — Instructions

Use this as the routine's instruction text:

---

First, search my Outlook calendar for today's events. Then review both my reece@kartahealthcare.com and sales@kartahealthcare.com inboxes for new and unread emails. Ignore automated notifications, newsletters, and marketing emails.

For each email:
1. Categorize into: Urgent, Action Needed, FYI, or Low Priority
2. Summarize the key point in one sentence
3. Note any deadlines or time-sensitive dates mentioned
4. Draft a response for any emails marked Urgent or Action Needed

Output the results as a complete HTML file using the template in `template.html` in this repository. Specifically:
- Populate the calendar section with today's meetings, showing time, title, location, and attendees
- If there are no meetings, replace the meeting cards with a `.calendar-empty` div saying "No meetings today"
- Update the calendar header h2 to show the correct meeting count
- Update the triage date/time in the header
- Set the stat card counts to match the actual number of emails in each category
- Replace the example email cards with real emails from both inboxes, grouped by category (Urgent first)
- Add an `.inbox-badge` span above each email's subject to indicate which inbox it came from: use class `primary` with text "reece@" for reece@kartahealthcare.com, and class `sales` with text "sales@" for sales@kartahealthcare.com
- Include draft responses inside `.draft-response` blocks for Urgent and Action Needed emails
- Include `.deadline` spans when a deadline is mentioned
- If no emails exist for a category, omit that category section entirely
- If the inbox is empty or all caught up, show a single `.empty-state` div confirming that

Keep drafted responses professional, concise, and signed off as Reece.

After generating the HTML, write it to `index.html` in this repository and commit and push to the main branch with the message "Update email triage dashboard — [date and time]".
