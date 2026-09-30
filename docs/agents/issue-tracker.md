# Issue tracker: GitHub

Issues and specs live in GitHub Issues for jakeboxer/Dropshot-releases.
Use the gh CLI from this clone; it infers the repository from origin.

## Operations

- Create: gh issue create --title "..." --body-file <file>
- Read: gh issue view <number> --comments
- List: gh issue list --state open --json number,title,body,labels,comments
- Comment: gh issue comment <number> --body-file <file>
- Label: gh issue edit <number> --add-label "..." --remove-label "..."
- Close: gh issue close <number> --comment "..."

For multiline bodies, write the exact text to a temporary file and use
--body-file. Fetch labels with gh issue view <number> --json labels.

“Publish to the issue tracker” means create a GitHub issue.
“Fetch the relevant ticket” means read the issue and its comments.

## Pull requests as a triage surface

PRs as a request surface: no.

## Wayfinding

- Keep the map in one issue labelled wayfinder:map.
- Link child tickets as GitHub sub-issues. If unavailable, use a task list
  in the map and a “Part of #<map>” line in each child.
- Label children wayfinder:research, wayfinder:prototype,
  wayfinder:grilling, or wayfinder:task.
- Record blockers using native issue dependencies when available;
  otherwise use a “Blocked by: #<number>” line.
- The frontier is the first open, unassigned child in map order whose
  blockers are all closed.
- Claim a ticket with gh issue edit <number> --add-assignee @me.
- Resolve by commenting with the result, closing the ticket, and adding
  a result summary and link to the map’s Decisions-so-far section.
