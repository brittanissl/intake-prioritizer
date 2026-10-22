# Project Intake & Prioritization Tool

A simple, no-install web tool that helps a PMO or operations leader decide which project requests to **approve, queue, defer, or decline** based on consistent scoring and the team's real capacity.

**[Try it live →]([https://YOUR-USERNAME.github.io/intake-prioritizer/](https://brittanissl.github.io/intake-prioritizer/))**  <!-- Replace YOUR-USERNAME after GitHub Pages is turned on -->

---

## The problem

Every team gets more requests than it can deliver. Without a shared way to compare them, the loudest request wins, priorities shift weekly, and the team says yes to more than it can finish.

In my PMO work, I brought department-level trackers into a single intake process. Scoring requests the same way and checking them against capacity made it possible to decline or defer about a quarter of incoming requests and free up capacity for the work that mattered most. This tool is a small, working version of that approach.

## What it does

- **Captures requests** with a name, requesting team, and the problem each one solves
- **Scores each request** from 0 to 100 on five criteria: business value, urgency, strategic fit, risk if not done, and effort (lower effort scores higher)
- **Ranks requests** and assigns a decision:
  - **Approve**: scores at or above the approval bar and fits in remaining capacity
  - **Ready, no capacity**: scores high, but the team is full. Next in line.
  - **Defer**: worth revisiting next cycle
  - **Decline**: below the bar
- **Explains each decision** in plain language, so the "why" can be shared with the requester
- **Lets leaders tune the model**: adjust criteria weights, team capacity, and decision thresholds
- **Exports to CSV** for a steering committee or status report

## How the score works

Each criterion is rated 1–5. Effort is inverted, so a 1 (a few days) helps the score and a 5 (months) hurts it. The score is a weighted average scaled to 0–100.

Default weights: Business value 30 · Urgency 20 · Strategic fit 20 · Risk if not done 15 · Effort 15

Requests are approved in rank order until the team's capacity (measured in effort points) is used up.

## How I built it

I built this with **Claude** (Anthropic's AI assistant). I defined the problem, the scoring criteria, the decision rules, and the sample scenarios based on my PMO experience. Claude wrote the code. I then tested it, reviewed the results against how I would have prioritized the same requests, and refined it.

It's a single HTML file with no server, database, or login. Data is saved only in the user's own browser.

## Try it

1. Open the live link above
2. Click **Load sample data** to see eight fictional requests ranked
3. Open **Scoring settings** and change the weights or capacity to see how the decisions shift
4. Add your own requests

## What I'd add next

- A shared version so a whole team can submit and see requests
- AI-assisted intake that drafts the scores from a plain-language request description
- A quarterly view showing what was approved versus delivered

---

*Sample data is fictional and does not reflect any company I have worked with.*
