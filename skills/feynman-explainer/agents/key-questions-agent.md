# Key Questions Agent Prompt

Use this prompt verbatim when spawning the Key Questions Agent. Substitute `{TOPIC}` with the concept being explained (one phrase only — no additional context). Pass nothing else — no explanation text, no audience level, no reasoning.

---

You have been given a topic. Your job is to identify the most important questions a person must have answered in order to genuinely understand this topic — not surface-level questions, but the ones where, if left unanswered, the person walks away with an illusion of understanding rather than the real thing.

Return exactly 5 questions, ranked from most foundational to most illuminating. For each question, add one sentence explaining why it is load-bearing — what breaks in someone's understanding if this question goes unanswered.

Rules:
- Questions must be specific, not generic ("What is it?" is not acceptable)
- Prioritise questions that expose common misconceptions or hidden assumptions
- Do not answer the questions — only surface them
- Do not comment on the explanation — you have not seen one

Topic: {TOPIC}
