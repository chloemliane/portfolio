# How the Clongy portfolio was built with Claude Code

Source: git history (`git log`) plus the user prompts and tool usage recorded in three Claude Code sessions in this project (Oct 28 and Nov 5, 2026). The very first version of the site (commit `ce05468`) was made before these sessions and is not covered here.

## Setup

| Piece | What it is |
|---|---|
| Site | One static file, `index.html`, plus `assets/` (videos, posters, graphics, resume PDF). No build step. |
| Hosting | GitHub Pages, deployed from `main` / root. Pushing publishes the site. |
| Git | Claude commits when asked; the user pushes through GitHub Desktop. |
| Preview | Claude Code's built-in browser pane on a local static server (`.claude/launch.json`), including mobile-size emulation. |
| Claude Code add-ons | Superpowers `brainstorming` skill, Claude in Chrome (to fetch files from a Google Photos / email account), a task list and wrap-up box in the desktop app. |

## Timeline

1. **First version** (`ce05468`, Oct 28). Minimal portfolio, 62 files: reels, graphics, resume.
2. **Review and redesign** (session "REVIEW", Oct 28 morning). The user said they didn't like the minimalist look and pasted three TikTok portfolios as inspiration ("some have animations and are dynamic"). Claude reviewed the site and proposed edits, then rebuilt it with the Liane Yaps look and motion (`3a01294`). It also added a sideways-scrolling daily-reels showcase after the user asked for that behavior.
3. **Feedback loop on a real browser.** The user opened the live site and sent notes: empty space on the right, cut-off text, disproportionate columns, short vlogs row. Claude fixed each, the user said "Yes, commit", then pushed. This repeated several times (`19284fe`, `53f6952`).
4. **Brand details.** Favicon in mustard yellow and white; shorter tab title; Oxford comma everywhere; the site stays named "Clongy" and should not look identical to the Elelet Market site.
5. **Typography** (session "DESIGN"). The user matched the cursive to the Liane Yaps logo: they checked the logo themselves and confirmed it is Pacifico (bold display font is TAN Tangkiwood, not available free). Pink cursive straightened, section numbering started at 01 (`6da8835`).
6. **Brainstorming for the next version.** The user shared three dynamic sites (cursor interaction, story-style layout). Claude ran the brainstorming skill and asked questions about the offer. The user's answer: use AI as labor while they supply the design, story, content, and thinking, aimed at making small brands and businesses run with a lighter load. Options A and B were liked; the user chose not to finalize yet.
7. **Motion techniques** (this session, Nov 5). Evaluated a free MotionSites Claude skill, read its LICENSE (MIT for code and techniques; media stays ©), and chose not to install it. Downloaded only the technique recipes to a scratch folder, picked three that fit, showed interactive mockups first, then built them: scroll-linked word reveal on About, magnetic buttons, stacking cards on phones (`faa9690`).
8. **Mobile fix.** The user reported the Core Memory series looked wrong on a phone. Cause: two items still spanned two columns in a one-column grid. One CSS selector fix (`6269238`).

## The working pattern

- The user gives a taste-based request or a pasted reference, not a spec.
- Claude looks at the current site and the references first, then proposes options or mockups before changing code.
- Claude edits `index.html`, previews it in the browser pane (desktop and phone size), and checks the console.
- The user reviews on the live site or real phone and sends short notes.
- Commit only on the user's explicit "Commit"; the user pushes.
- Third-party code and assets are checked for license and trust before use.

## Guardrails that worked

- Mockups before building.
- Verify in the preview, not just by reading code.
- Reduced-motion users get none of the animation.
- Commit only the files for the change, leaving the user's other edits alone.
- One signature idea per page, a few quiet supporting effects.

## Limits of this write-up

- Session transcripts record prompts and tool counts, not every Claude reply, so the reasoning in steps 2 and 3 is summarized from the commits and prompts.
- Where the original media (reels, graphics) was produced is not in these transcripts. Other sessions on this machine (ClongyEditor, ClongyGraphics) probably made them, but that is not verified.
