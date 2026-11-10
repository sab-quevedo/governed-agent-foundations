# Lab notes: Agents I (governing actions)

Name: Sabrina Quevedo
GitHub username: sab-quevedo

Write one to three sentences per lab, with numbers or names from YOUR run. Commit and push this file to your fork by 9:25, then open a pull request titled "Lab notes: Firstname Lastname".

## Lab 0: the loop
What are the five things the loop does on every step, and which two of them are governance rather than intelligence?

- The five things the loop does on every steps is  it observed, chose a tool, passed a policy check, acted, and wrote a line of evidence. Check and log are governance.

## Lab 1: the model as a tool
P003 and P006: their probabilities and bands from your run. Which feature drove P006's risk most? Who authored the model card the agent relies on?

- P003  scored **0.128, LOW**, so the agen stopped. P006 scored **0.909, HIGH**, so top driver was **prior_admissions_12m (3)**, followed by er_visits_6m (2) and lives_alone. 

## Lab 2: capability is not permission
Three refusals: the tool or patient, and the policy line that caused each. After your edit (max_patients_per_task, max_tool_calls_per_task), what finished that did not before, and who should be allowed to make that edit?

- Three refusals, each with a policy line behind it are: export_records, P011, P004, P006, P008. After I raised max_patients_per_task to 3 and max_tool_calls_per_task to 12,the results finished all three patients in **11 calls**: P004 0.56 HIGH, P006 0.91 HIGH, P008 0.48 MEDIUM

## Lab 3: the approval gate
What did the log record when you approved and when you rejected? Name one action in your final project that belongs in approval_required, and one that does not, with a reason.

- The approval gate P007 was HIGH risk. The agent wanted to book a follow up call but it had to stop to ask first. When I said 'Y', the log recorded that I approved it, and the call got booked. When I said 'no', the log recorded that I rejected it, and the call never happened. 

## Lab 4: evidence
From your audit summary: tasks, allowed calls, refusals, approvals. Who should read this log, how often, and what would make them pull the agent?

- The log showed everything I did in about 8–10 tasks, about 25 tool calls, 3 refusals (the export, the wrong-hospital patient, and the too-many-patients limit), and 1 rejection by me

## Lab 5: a language model in the planner's seat (if you ran it)
Did the model take the same route as the scripted planner? With --inject on P009: did it try export_records, and what stopped it?

- The AI took about the same steps as the rule-based planner (look up, score, ask me to book, write a note). The rules and the log worked the same way. 
- If it tried to export: P009's note had a hidden instruction telling the AI to export all records, and the AI tried to do i

## Declaration
I ran every command above in my own Codespace and the numbers are from my own run.  Initials: SQ
