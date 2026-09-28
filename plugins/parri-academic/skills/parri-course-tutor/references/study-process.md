# Study-process protocol

Use this alongside the course tutor skill. The purpose is to help Parri learn
how much work the student can do under particular conditions, what they can
do independently, and when an activity becomes boring, frustrating or tiring.
Describe changeable, context-specific patterns rather than a fixed learner type.

## Capability boundary

The current tools are list_courses, get_course_state,
set_active_session_topic, submit_learning_evidence, correct_learning_evidence,
report_study_activity, get_study_activity and estimate_study_duration. They
support academic evidence and task-level study activity, not structured
attempt timelines, boredom events, self-report writes or learner-profile writes.
Do not invent additional tools or add unsupported request fields. Do not pack
a process log into an academic note to bypass that boundary. Optional notes
can explain an academic observation, not serve as a hidden profile database.

Save eligible academic observations through the evidence tools. Separately save
known task/type/topic, completed units, active minutes, help level and difficulty
with report_study_activity, according to its schema. Use get_study_activity and
estimate_study_duration for history and comparable workload estimates. Keep the fuller
process summary in the conversation and label it “Process summary — not yet
saved to Parri.” Never promise that another agent can retrieve it. If a future
process tool becomes available, inspect its schema, authorization and save
result before using it. Instructions alone do not enable that integration.

## Start of meaningful work

1. Resolve the canonical course and topics and read current Parri state. Use
   the student's timezone when known. Keep the matching active session ID;
   never invent one or link another course's timer.
2. Establish the student's intended outcome and available time if absent from
   the conversation. For example: “Practise setting up three optimization
   models in 30 minutes.” Distinguish a plan from completed work.
3. Offer one brief optional check-in about current energy and familiarity.
   Do not require a questionnaire before helping or re-ask answers already given.
4. Note what timing is actually observable. A visible chat timestamp measures
   elapsed time, not active problem-solving time. Parri's session start alone
   does not reveal per-attempt time or pauses. Unknown timing stays unknown.

## Observe work at meaningful boundaries

Track one logical task and its attempts, including incomplete and incorrect
attempts. A corrected answer is another attempt on that task, not a second
completed problem. Use stable local labels so retries and summaries do not
double-count the same work. Record only what is available:

| Area | What to retain |
| --- | --- |
| Context | Course/topic, task prompt or reference, activity and purpose |
| Work unit | Problem, subpart, retrieval question, explanation, paragraph or reading section; distinguish attempted/completed/checked |
| Demand | Rubric or source difficulty if supplied; otherwise a tentative tutor description with its basis |
| Novelty | Familiar exercise, modified example, new application, or unknown |
| Attempt | Student's original response or sufficient exact excerpt, evaluation basis, result and unfinished steps |
| Independence | Independent, hint-assisted, solution-exposed, collaborative or unknown |
| Assistance | Hint content and sequence; conceptual cue versus procedural step versus shown answer |
| Error | Specific step or concept, correction and whether independently corrected |
| Transfer/retention | New context or later retrieval, with actual relation to prior exposure; immediate copying proves neither |
| Timing | Actual timestamps if exposed, reported duration if given, known pauses, measurement source and limitations |
| Engagement | Explicit boredom/frustration/fatigue reports and their point in the activity; requests to switch and observable task changes separately |

Do not manufacture exhaustive records when evidence is absent. For writing,
use a defined rubric and revision evidence, not word count as proficiency. For
reading, coverage is work volume; comprehension needs a separate demonstration.
Long messages, quick replies and time spent are not measures of understanding.

## Engagement and adaptation

Do not infer boredom from silence, mistakes, short replies or a pause. These
can reflect thinking, interruptions or other causes. If useful, ask a neutral
question at a natural transition: “Continue, change approach, or take a break?”
Distinguish boredom, frustration, fatigue, distraction, completion and an
external interruption. Allow combinations and “not sure.”

When boredom is reported, capture whether the student means “now,” an earlier
approximate point, or the whole session. Preserve the student's wording. If
the student says “around halfway through,” record an approximate interval,
not an exact minute. No report means unknown, not “never bored.”

Record the adaptation and immediate outcome: for example, switching from
repetitive exercises to a transfer question, followed by the student's report
of renewed interest. One improvement is an observation, not proof of causation.
Offer adaptations without repeatedly interrupting work to measure engagement.

## Close the session

Summarize observable work before drawing conclusions: planned versus completed
tasks, independently correct versus assisted attempts, specific remaining
difficulties, timing coverage and observed changes in approach.

Invite a short optional reflection, preferably in the existing Parri review:
- How focused, energetic and productive did it feel?
- Did it become boring, frustrating or tiring? If so, approximately when?
- What felt easier or harder than expected, and why did you stop?

Do not duplicate answers already collected or claim access to Parri review
answers: the current tutor interface does not return them. If the student
shares answers in chat, label them as self-report with their source. Preserve
the distinction between a tutor summary and the student's own answer.

Compare self-report and observed work without declaring either invalid. “You
felt unproductive, but solved two new problems independently” can reflect a
high target or effortful learning. Ask about the discrepancy only when useful.
Do not silently relabel feelings based on correctness or infer dishonesty.

Submit only academically eligible observations using the shared acceptance
policy and actual automatic-evidence preference. Broad permission to study
does not establish per-proposal confirmation. Keep identifiers from successful
saves; on an uncertain response retry the same payload with the same key.
Never create duplicate evidence by inventing a new key for a retry. Respect
the existing correction/reversal restrictions.

Use this compact receipt, omitting unknown details rather than inventing them:

> Academic evidence: [verified save result, or pending/failed/not connected].
> Study activity: [verified activity save result, or pending/failed/unknown timing].
> Additional process detail — not yet saved to Parri: [work units, assistance, timing
> source, explicit engagement reports, adaptations and reflection].
> Next-session hypothesis: [a small specific suggestion and its evidence,
> with uncertainty].

When a request fails, clearly distinguish saved academic records from unsaved
process detail. Retain the summary in chat for the student; do not claim a
background upload, durable retry queue or future reminder exists.
