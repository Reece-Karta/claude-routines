# Email Triage Routine — Instructions

Use this as the routine's instruction text:

---

Review my reece@kartahealthcare.com inbox for new and unread emails. Ignore automated notifications, newsletters, and marketing emails.

For each email:
1. Categorize into: Urgent, Action Needed, FYI, or Low Priority
2. Summarize the key point in one sentence
3. Note any deadlines or time-sensitive dates mentioned
4. Draft a response for any emails marked Urgent or Action Needed

Output the results as a complete HTML file using the template in `template.html` in this repository. Specifically:
- Update the triage date/time in the header
- Set the stat card counts to match the actual number of emails in each category
- Replace the example email cards with real emails, grouped by category (Urgent first)
- Include draft responses inside `.draft-response` blocks for Urgent and Action Needed emails
- Include `.deadline` spans when a deadline is mentioned
- If no emails exist for a category, omit that category section entirely
- If the inbox is empty or all caught up, show a single `.empty-state` div confirming that

Keep drafted responses professional, concise, and signed off as Reece.

After generating the HTML, write it to `index.html` in this repository and commit and push to the main branch with the message "Update email triage dashboard — [date and time]".
