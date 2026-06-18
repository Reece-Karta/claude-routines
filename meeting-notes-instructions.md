# Meeting Notes Export Routine — Instructions

Use this as the routine's instruction text:

---

Export all of my recent meeting notes from Granola and save them as markdown files in the `meeting-notes/` folder in this repository.

## Steps

1. Use the Granola `list_meetings` tool to fetch meetings from `last_30_days`
2. For each meeting found, use `get_meetings` to retrieve the full details (summary, attendees, metadata)
3. If any meetings have generic titles like "New note", use `get_meeting_transcript` to get the transcript and generate a descriptive title from the content

For each meeting, extract:
- **Title** and date/time
- **Attendees** (all known participants)
- **Summary** — use the AI-generated summary from Granola. Condense into clear bullet points if needed
- **Action items** — extract any next steps, follow-ups, or tasks mentioned in the summary. Include the owner/responsible person where identified
- **Key decisions** — extract any decisions, approvals, or agreements reached

## Output

Save each meeting as a separate markdown file in the `meeting-notes/` folder. Use the naming convention:

```
meeting-notes/YYYY-MM-DD-meeting-title-slugified.md
```

For example: `meeting-notes/2026-06-18-seo-strategy-review-with-jeff.md`

Each file should follow this format:

```markdown
# Meeting Title

**Date:** 18 Jun 2026, 9:00 AM
**Attendees:** Reece Munro, Jeff K.

## Summary

- Bullet point summary of the meeting
- Key topics discussed

## Action Items

- [ ] **Reece:** Send updated proposal by Wednesday
- [ ] **Jeff:** Prepare pricing comparison

## Key Decisions

- Approved $5K monthly SEO budget starting July 1
- Agreed to target US and Canada markets first
```

Rules:
- Create the `meeting-notes/` directory if it doesn't exist
- Skip any meetings that already have a corresponding file in `meeting-notes/` (avoid duplicates)
- If a meeting has no action items or decisions, omit those sections
- If there are no new meetings to export, do nothing
- One file per meeting

After writing the files, commit and push to the main branch with the message "Add meeting notes — [date]".
