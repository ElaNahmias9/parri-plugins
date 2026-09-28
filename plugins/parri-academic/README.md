# Parri Academic

Study with a tutor that uses your actual Parri course topics, review priorities,
assessments and learning history. Parri Academic helps Claude choose useful
practice, record demonstrated learning, and estimate future study time from
comparable work you have already completed.

## Connect

Install Parri Academic, connect the bundled connector, then sign in to
[Parri](https://parr-seven.vercel.app) and select the courses Claude may access.
An active Parri account and courses are required. No API key or client secret
is needed. You can revoke access from Parri's Academic Connections screen.

## Try it

- “Read my Parri course state and help me choose what to study.”
- “Tutor me on a weak topic and record only what I demonstrate.”
- “Estimate how long this practice set will take from comparable study work.”

## What it can do

The connector lists authorized courses, reads their academic state, changes the
topic on a matching active study timer, submits and corrects grounded learning
evidence, records study activity, reads activity history, and estimates study
durations. It cannot start or stop your timer, change courses, or assign mastery
scores. Parri calculates academic state. Reading and elapsed time are not proof
of understanding. Ambiguous learning observations require your confirmation.

## Data and permissions

The plugin uses the declared remote connector at
`https://parr-seven.vercel.app/mcp`. It accesses only the courses you approve.
Academic records can include topic names, assessments, student-response excerpts,
learning observations, and reported study activity. Submitted evidence and study
activity are stored in your Parri account; the plugin itself has no independent
storage or analytics endpoint. Do not include unrelated sensitive information
in academic observations. Revoking a connection stops future access; it does
not erase records already saved to your account.

See Parri's [privacy policy](https://parr-seven.vercel.app/privacy),
[terms](https://parr-seven.vercel.app/terms), and
[support page](https://parr-seven.vercel.app/support).

## Availability

This repository is a public plugin source. A public Claude Discover listing is
available only after Anthropic accepts and publishes its directory submission.
The Parri application and backend are separate from this plugin package.
