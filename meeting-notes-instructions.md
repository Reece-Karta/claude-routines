# Meeting Notes Export Routine — Instructions

Use this as the routine's instruction text:

---

Export all of my meeting notes from Granola for today and save them as a formatted HTML dashboard in this repository.

## Steps

1. Use the Granola `list_meetings` tool to fetch meetings from `this_week`, then filter to today's date only
2. For each meeting found, use `get_meetings` to retrieve the full details (summary, attendees, metadata)
3. If any meetings have generic titles like "New note", use `get_meeting_transcript` to get the transcript and generate a descriptive title from the content

For each meeting, extract:
- **Title** and date/time
- **Attendees** (all known participants)
- **Summary** — use the AI-generated summary from Granola. Condense into clear bullet points if needed
- **Action items** — extract any next steps, follow-ups, or tasks mentioned in the summary. Include the owner/responsible person where identified
- **Key decisions** — extract any decisions, approvals, or agreements reached

## Output

Generate a complete HTML file using the template in `meeting-notes-template.html` in this repository. Specifically:

- Set the export date in the header to today's date
- Update the stat card counts to reflect actual totals (meetings, action items, decisions)
- Replace the example meeting card with real meetings from Granola
- Each meeting gets its own `.meeting-card` inside a `.meeting-section`
- Populate attendee chips with actual participants
- List action items with owner names where known
- List key decisions in decision items
- If there are no meetings for today, show a single `.empty-state` div saying "No meetings recorded today"
- If a meeting has no action items or decisions, omit those subsections for that meeting

Write the output to `meeting-notes.html` in this repository, then commit and push to the main branch with the message "Update meeting notes export — [date]".
