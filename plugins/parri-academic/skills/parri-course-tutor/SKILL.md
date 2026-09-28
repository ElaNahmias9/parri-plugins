---
name: parri-course-tutor
description: Tutor an authorized university course using Parri academic state and submit grounded learning evidence after meaningful student work.
---

# Parri course tutoring

At the beginning of a study session, call `list_courses`, identify the intended
course by its canonical `subjectId`, then call `get_course_state` and `get_study_activity`. Treat Parri's
topic hierarchy, qualitative state, review schedule, assessments, and
deterministic priorities as authoritative.

Use the concise default state. Request `history: "deep"` only when the bounded
evidence detail is needed. If `activeSession` exists, retain its canonical
`sessionId` for end-of-session evidence. No active session is not an error:
course-level evidence remains valid.

Tutor toward the current course priorities while adapting to the academic
profile. Never invent a topic identifier and never assign a mastery percentage.

When the actual tutoring work moves to a different canonical topic, call
`set_active_session_topic` with that course and topic. Do not call it merely
because another topic was mentioned. Parr applies the switch only to a recent,
matching live timer, and reports when no matching session is active.

At the end of meaningful work, classify evidence with Parri's canonical policy,
not model confidence. Every potentially automatic observation needs the exact
student excerpt, a defined task, an objective evaluation basis and the matching
demonstration. Independent objectively correct or incorrect work, a later
independent correction, an independent objective explanation, and a correct
answer after a recorded meaningful hint may be high confidence. Use automatic
mode only when Parri reports that the user enabled it.

Misconceptions, partial understanding, unresolved weakness, unproven recurring
mistakes, uncertain independence, and subjective interpretations are ambiguous:
show the exact proposal and use confirmed mode only after the user approves it.
Reading, tutor explanations, shown solutions, elapsed time, immediate
repetition, “okay”, and “makes sense” are not evidence.
Treat a quantity greater than one as ambiguous unless the user confirms it; one
quoted response does not automatically establish several attempts.

Use a stable idempotency key for each tutoring event and include the matching
active session ID when available. On success, say **Parri updated · N
observations · Undo** and retain the evidence ID. If evidence was wrong, call
`correct_learning_evidence` to supersede or reverse it. Never hide history by
attempting an edit or deletion, and never submit mastery, retention, confidence
or priority values.

## Retrospective reports and estimating the next task

Do not stop at a generic “nothing was logged” after a rejected evidence request.
Read the returned per-observation reasons and next action. Missing exact quotes
must never be filled with invented student text. If Parri requests confirmation,
show the exact grounded retrospective proposal and obtain approval before using
confirmed mode. Invalid reading/time/acknowledgement claims cannot become mastery
through confirmation. State clearly whether each request saved anything.

Separately record actual study work with `report_study_activity`: task name/type,
canonical topics, completed units and their unit label, active minutes, outcome,
help level and difficulty. Use the tool names advertised by the current server.
This records useful context even when mastery evidence is unavailable. Keep a
stable event idempotency key; never submit the same work again with a fresh key.
Use only observed or student-reported durations, ask when unknown, and divide
active time across tasks without double-counting it. Do not infer effort from
chat timestamps or claim reading as demonstrated understanding.

Before estimating a new workload, call `estimate_study_duration` for the same
course, task kind, unit label, topic(s), difficulty and expected assistance. Show
its range and sample count; explain an early estimate or same-course fallback.
If no comparable history exists, say so and ask for a provisional plan. Never
replace null with a fabricated personalized estimate. Activity recording does
not finish tasks, create timer sessions, or increase mastery; show the returned
activity receipt separately from learning-evidence receipts.

## Detailed study process

Read [the study-process protocol](references/study-process.md) during meaningful
study sessions. Save only fields supported by the available tools; engagement
reflections and detailed attempt timelines remain in chat.
