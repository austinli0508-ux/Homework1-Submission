
## Notebook 02: Task 1 - Custom System Prompt

**Completed:** 2026-06-18 15:04:41

### What I Learned

[I learned that a system prompt sets the model's role and standards before it
ever sees my question. By telling it to act as a Python code reviewer focused
on correctness, efficiency, and readability, the model knew what lens to use
without me repeating those instructions in every request.]

### How the System Prompt Affected the Response

[The response was structured like an actual code review rather than a generic
explanation. It flagged the divide-by-zero risk when `numbers` is empty,
commented on readability, and suggested improvements such as input validation.
Without the system prompt, the same question tends to get a plain description
of what the function does, with far less critical feedback.]

### Real-World Applications

[This pattern is useful anywhere I want consistent, role-specific behavior:
automated PR review bots, customer-support assistants with a fixed tone,
tutoring tools that stay at a beginner level, or data-extraction services
that must always return a strict format.]

---

## Notebook 02: Task 2 - Temperature Exploration

**Completed:** 2026-06-18 15:31:33

### Temperature 0.0 Analysis

[At 0.0 the poem was the most predictable and "safe" — clean structure,
conventional imagery, and the kind of output I'd expect to get again if I
re-ran it. Consistent, but the least surprising.]

### Temperature 0.5 Analysis

[At 0.5 I saw a good middle ground: the poem kept a coherent theme but used
more varied word choices and imagery than 0.0, without becoming strange or
losing the thread.]

### Temperature 1.0 Analysis

[At 1.0 the poem was the most creative and varied — bolder metaphors and less
predictable phrasing. It was the most interesting to read but also the least
repeatable; another run would likely look quite different.]

### Conclusion

**Best temperature for this task:** [1.0]

**Reasoning:** [For a creative task like poetry, variety and originality matter
more than consistency, so the higher temperature produced the most engaging
result. (0.5 would be my safer second choice.)]

### When to Use Each Temperature

- **Temperature 0.0:** [Factual Q&A, data extraction, classification, structured/JSON output where I need the same answer every time.]
- **Temperature 0.5:** [General explanations, summaries, everyday Q&A — a versatile default.]
- **Temperature 1.0:** [Creative writing, poetry, brainstorming, generating multiple varied options.]

---

## Notebook 02: Task 3 - Cost Optimization

**Completed:** 2026-06-19 08:45:07

### Comparison Results

- **Token savings:** 43 tokens (63.2%)
- **Cost savings per request:** $0.000168
- **Projected savings (100 requests):** $0.0168

### Quality Analysis

**Did the verbose version produce a better response?**
[No. The extra politeness and filler ("I would really appreciate it if you
could kindly...") added input tokens but did not improve the answer. Both
responses covered the same core ML concepts at a similar quality.]

**Was the concise version still clear and complete?**
[Yes. The concise prompt got a clear, complete, beginner-friendly explanation
with no important information lost. The model understood the intent just as
well from the shorter wording.]

### Key Lessons Learned

1. [Filler words and politeness in prompts cost real tokens without improving output quality.]
2. [Verbose prompts are only justified when the extra words carry actual
   information — specific constraints, context, examples, or format requirements.]
3. [I will write prompts the way I'd write a clear instruction: state the task,
   the audience, and the format, and cut everything else.]

### My Cost Optimization Strategy

Going forward, I will:
- [Strip politeness/filler and keep only words that change the output.]
- [Set a sensible max_tokens cap so responses don't run longer than needed.]
- [Use a cheaper/smaller model for testing and iteration, saving the stronger model for final outputs.]

---

## Notebook 02: Overall Reflection

**Completed:** 2026-06-19 08:49:21

### 1. What surprised you most about system prompts?

[How much they change the response without changing my actual question. By
setting a role and standards in the system prompt (e.g., a Python code
reviewer), the model behaved consistently in that role across requests,
which I didn't expect from such a short instruction.]

### 2. For factual questions, what temperature do you prefer and why?

[0.0. For factual questions I want consistent, predictable answers, and a low
temperature gives the same reliable response if I re-run it. Higher
temperatures add variety I don't need and risk less accurate phrasing.]

### 3. What's your main strategy for keeping API costs low?

[Write concise prompts (cut politeness and filler that don't change the
output), set a sensible max_tokens cap, and use a smaller/cheaper model for
testing while saving the stronger model for final deliverables.]

### 4. What's one practical use case where you'd use these techniques?

[An automated support assistant: a fixed system prompt to control tone and
role, low temperature for consistent answers, and tight prompts to keep
per-request cost down at scale.]

### 5. What was your most interesting finding from this notebook?

[That a verbose, polite prompt cost noticeably more tokens but produced a
response of essentially the same quality as the concise version — wordiness
costs money without adding value.]

### 6. What will you do differently in future prompting?

[Treat prompts like clear instructions: state the task, audience, and format,
match the temperature to the task (low for facts, higher for creativity), and
remove any words that don't change the result.]

---

## Notebook 03: Task 1 - Build Your CO-STAR Prompt

**Completed:** 2026-06-19 09:58:52

### What scenario did you choose?

[A product description for a single-origin Ethiopian coffee, written as
marketing copy for a small roaster's online shop.]

### How did each CO-STAR component help?

**Context:** [How did this help the LLM understand the task?Telling the model it was a copywriter for a coffee roaster set the right voice and domain immediately.]

**Objective:** [Was your goal clear and specific?Clear and specific — "write a product description for this coffee" left no ambiguity about the deliverable.]

**Style:** [Did the response match your desired style?The "vivid and sensory" style produced descriptive, appetizing language rather than dry facts.]

**Tone:** [Was the emotional quality appropriate?"Warm and inviting" made it feel friendly and on-brand instead of robotic.]

**Audience:** [Was the complexity level right for your audience?Aiming at flavor-focused enthusiasts kept the copy detailed about origin and taste rather than overly basic.]

**Response Format:** [Did you get the structure you wanted?The 2-paragraph, under-120-word, tasting-note-ending format was followed closely, which made it ready to paste into a product page.
]

### Quality of the response

[Rate 1-5 and explain]: __4_/5

[What worked well?]

[What would you improve?The copy was engaging and on-format. It worked well for tone and
structure; I'd improve it by adding one more concrete tasting detail.
]

### Real-world application

[Where would you use this prompt in practice?Generating consistent product descriptions for an e-commerce catalog, where
a reusable CO-STAR template keeps voice and format uniform across items.]

---

## Notebook 04: Task 2 - Multi-Record Extraction

**Completed:** 2026-06-19 10:16:57

### Multi-Record Extraction

**Number of items in text:** [X]

**Number correctly extracted:** [X]

**Accuracy:** [X/X = XX%]

### Challenges with Arrays

[What was harder about extracting multiple items vs single items?]

### Data Quality

[Were all fields correctly identified for each item?]

[Any patterns in what was missed or wrong?]

### Scaling Considerations

**How would this work with 100 items?**

[Discuss token limits, cost, reliability]

### Production Readiness

[Would you trust this for production use? Why or why not?]

[What safeguards would you add?]

---



## Notebook 04: Task 1 - JSON Extractor

**Completed:** 2026-06-19 10:25:40

### Extraction Quality

**Did it correctly extract all fields?** [Yes]

[What worked well? What was missed?All six fields were extracted correctly: product name (UltraBook Pro),
rating (4), reviewer (Sarah M.), pros (battery life, crisp display), cons
(heavy, keyboard comfort), and would_recommend (true). The Pydantic
validation passed without errors.]

### Prompt Effectiveness

**How clear was your prompt?** [Rate 1-5]: __5_/5

[What would you change to improve it?Explicitly listing the exact fields and demanding "ONLY valid JSON, no code
fences" was what made the output clean and parseable. Early on, asking less
strictly tended to produce extra commentary that broke parsing.]

### Real-World Application

**Where would you use this review extractor?**

[Automatically turning free-text customer reviews into structured data for a
dashboard — e.g., aggregating average ratings and mining common pros/cons
across thousands of reviews.]

### Challenges Encountered

[What was difficult about getting structured output?]

[How did you solve it?The main challenge was stopping the model from adding friendly text or
markdown ```json fences around the output. I solved it by stating the
"ONLY JSON, no extra text" rule directly, and relying on the parse_json
helper plus Pydantic validation to catch anything malformed.
"]

---

## Notebook 05: Task 1 - Multi-Step Problem Solving

**Completed:** 2026-06-19 10:48:18

### Problem Chosen

[Describe the problem you chose or created]

### Without CoT Analysis

**Answer received:** I need to calculate the parking cost for 9 hours.

**Breaking down the charges:**
- First hour: $5
-...

**Correct?** [Yes/No]

[Why do you think it got this answer?]

### With CoT Analysis

**Reasoning shown:** 

[Summarize the step-by-step reasoning]

**Final answer:** [Extract the final answer]

**Correct?** [Yes/No]

### Comparison

**Which approach was more accurate?** [Without/With CoT]

**Which was more transparent?** [Without/With CoT]

**Which gave you more confidence?** [Without/With CoT]

### Quality of Reasoning

**Did CoT show all necessary steps?** [Yes/No]

[What steps were shown? Any missing?]

**Could you verify each step?** [Yes/No]

[Try to verify - were all steps correct?]

### Key Insight

[What did you learn about when CoT helps most?]

### Real-World Application

[Where would you use this problem-solving approach?]

---

## Notebook 05: Task 1 - Multi-Step Problem Solving

**Completed:** 2026-06-19 10:54:04

### Problem Chosen

[A parking garage pricing problem with a tiered rate ($5 first hour, $3 each
additional hour) and a $25 daily cap, asking the cost for 9 hours.]

### Without CoT Analysis

**Answer received:** I need to calculate the parking cost for 9 hours.

**Breaking down the charges:**
- First hour: $5
-...

**Correct?** [Yes]

[Even without an explicit CoT instruction, the model reasoned step by step on
its own: it computed $5 + 8×$3 = $29 and recognized that $29 exceeds the $25
maximum. However, with max_tokens=100 the response was truncated right before
it stated the final $25, so no clean final answer was given.]

### With CoT Analysis

**Reasoning shown:** 

[Step 1: cost without the cap ($5 + $24 = $29). Step 2: compare to the $25 cap
($29 > $25, so the cap applies). Step 3: conclude the charge is the cap.
]

**Final answer:** [$25]

**Correct?** [Yes]

### Comparison

**Which approach was more accurate?** [both reasoned correctly, but only the CoT version finished with a clear, correct final answer]

**Which was more transparent?** [With CoT]

**Which gave you more confidence?** [With CoT]

### Quality of Reasoning

**Did CoT show all necessary steps?** [Yes]

[What steps were shown? Any missing?It showed the base calculation, the cap comparison, and the final decision.
]

**Could you verify each step?** [Yes]

[Try to verify - were all steps correct?I checked each: $5 + $24 = $29, capped at $25 — all correct.
]

### Key Insight

[What did you learn about when CoT helps most?A strong model often reasons step-by-step even without being told to. The
bigger practical lesson here was about output length: the no-CoT version had
only 100 tokens and got cut off mid-reasoning, while the CoT version had room
to finish. Explicit CoT plus a sufficient max_tokens makes the final answer
reliable and easy to extract.]

### Real-World Application

[Where would you use this problem-solving approach?Any multi-step calculation with a constraint (billing caps, tax brackets,
shipping tiers) where I need both a correct answer and a visible, verifiable
reasoning trail.]

---



## Notebook 06: Task 1 - Find Your Perfect Model

**Completed:** 2026-06-19 11:16:30

### Task Description

[What task did you choose and why?Summarizing a research abstract into 3 bullet points (problem / method /
result). I chose it because my research agent will need to condense papers
into quick, structured takeaways.]

### Model Comparison

For each model, rate the response quality (1-5):

#### Model 1: [claude-haiku-4-5-20251001]
- **Quality Rating:** __5_/5
- **Speed:** [Fast(1.80s)]
- **Cost:** $__$0.000543_
- **Strengths:** [What did it do well?Accurate, well-structured 3-bullet summary that correctly captured the problem, method, and result. Fastest and cheapest.]
- **Weaknesses:** [What could be better?None meaningful for this task; output was essentially as good as Sonnet's.
]

#### Model 2: [claude-sonnet-4-5-20250929]
- **Quality Rating:** __5_/5
- **Speed:** [Medium (2.38s)]
- **Cost:** $__$0.001524_
- **Strengths:** [ Equally accurate and clean summary, slightly more polished phrasing.]
- **Weaknesses:** [~2.8x more expensive and noticeably slower for no real quality gain on this task.
]

#### Model 3: [name] (if tested)
- **Quality Rating:** ___/5
- **Speed:** [Fast/Medium/Slow]
- **Cost:** $___
- **Strengths:** [What did it do well?]
- **Weaknesses:** [What could be better?]

### Winner for This Task

**Best overall:** [claude-haiku-4-5-20251001]

**Why?**
[For a well-defined summarization task, Haiku produced output of
essentially the same quality as Sonnet, but ~2.8x cheaper and faster. The
extra cost of Sonnet bought no visible quality improvement here. ]

### Cost-Quality Tradeoff

**Is the quality difference worth the cost difference?**

[Is the quality difference worth the cost difference?** No. The two outputs
were nearly identical in quality, so paying ~3x more for Sonnet is not
justified for this simple, structured task. Sonnet would only be worth it for
harder tasks (nuanced reasoning, long documents) where its strength shows.]

### Speed Consideration

**Does response time matter for your use case?**

[Yes. If the research agent summarizes many papers in a batch, Haiku's faster
response time (1.80s vs 2.38s) compounds and improves throughput.]

### Decision for Your Project

**Which model will you use for this type of task?**

[I'll use Haiku for bulk/routine summarization and extraction, and reserve
Sonnet for harder tasks or final-quality outputs — the hybrid cost strategy.]

### Scaling Considerations

**If you run this task 1000 times/month:**
- Model A would cost: $__~$0.54_
- Model B would cost: $__~$1.52_
- Model C would cost: $__0_

**Still worth it?** [At this scale both are cheap, but Haiku saves ~$1/month
here and far more at higher volume — and a local Llama model could drive cost
to ~$0 if I'm willing to trade some quality and manage local hardware.]

---


## Notebook 07: Task 1 - Design Your Research Agent Tools

**Completed:** 2026-06-19 13:48:25

### Tool Design

**Total tools designed:** _4_

**Categories:**
- Search/Discovery: __1_ tools
- Data Processing: __1_ tools
- Analysis: ___1 tools
- Output Generation: ___1 tools

### Tool Complexity

**Simplest tool:** [save_to_library]
[save_to_library — it just writes given data to a file]

**Most complex tool:** [fetch_paper_text]
[handling different formats (PDF/HTML),
messy layouts, and parsing failures makes it the hardest to make robust.]

### Existing vs Custom

**Tools that exist (can use off-the-shelf):** 
[search_arxiv (arXiv API), fetch_paper_text
(existing PDF/HTML parsing libraries), summarize_paper (Claude API).]

**Tools you'd need to build custom:**
[mostly thin wrappers plus save_to_library's
file/format logic; the main custom work is gluing them together reliably.]

### Implementation Priority

**Must-have (Priority 1):**
1. [search_arxiv]
2. [summarize_paper]

**Nice-to-have (Priority 2):**
1. [fetch_paper_text ]
2. [save_to_library]

**Future enhancement (Priority 3):**
1. [A dedup/ranking tool to prioritize the most relevant papers
]

### Dependencies

**Do your tools depend on each other?**
[Yes. fetch_paper_text needs a URL from
search_arxiv; summarize_paper needs text from fetch_paper_text; save_to_library
needs the summary.]

**What's the sequence of tool calls?**
[search_arxiv -> fetch_paper_text ->
summarize_paper -> save_to_library.]

### Data Flow

**What data flows between tools?**
[A paper's URL flows from search to fetch; the
extracted text flows from fetch to summarize; the summary flows to save.]

**Any bottlenecks?**
[fetch_paper_text — slow downloads or unparseable PDFs can
stall the whole pipeline.]

### Error Handling

**What could go wrong with each tool?**
[API rate limits (search), broken/blocked
links or bad PDFs (fetch), malformed LLM output (summarize), file write errors
(save).]

**How would you handle failures?**
[Retry with backoff for rate limits, skip and
log papers that fail to parse, validate summary format before saving, and wrap
file writes in try/except.]

### Real-World Readiness

**Could you actually build these tools?** [Yes, at a basic level.]

**What skills/resources would you need?**
[Python, the arXiv API, a PDF/HTML
parsing library, and the Claude API key I already set up.]

**Timeline to implement:**
- search_arxiv: ~half a day
- summarize_paper: ~half a day
- fetch_paper_text: ~1 day (robust parsing)
- save_to_library: ~a few hours

### Biggest Insight

[What did you learn about designing tools for agents?Designing agent tools is mostly about clear inputs/outputs and how data flows
between them. Each tool should do one thing well so the agent can chain them,
and most of the real effort goes into error handling, not the happy path.]

---

## Notebook 07: Task 1 - Design Your Research Agent Tools

**Completed:** 2026-06-19 13:48:26

### Tool Design

**Total tools designed:** _4_

**Categories:**
- Search/Discovery: __1_ tools
- Data Processing: __1_ tools
- Analysis: ___1 tools
- Output Generation: ___1 tools

### Tool Complexity

**Simplest tool:** [save_to_library]
[save_to_library — it just writes given data to a file]

**Most complex tool:** [fetch_paper_text]
[handling different formats (PDF/HTML),
messy layouts, and parsing failures makes it the hardest to make robust.]

### Existing vs Custom

**Tools that exist (can use off-the-shelf):** 
[search_arxiv (arXiv API), fetch_paper_text
(existing PDF/HTML parsing libraries), summarize_paper (Claude API).]

**Tools you'd need to build custom:**
[mostly thin wrappers plus save_to_library's
file/format logic; the main custom work is gluing them together reliably.]

### Implementation Priority

**Must-have (Priority 1):**
1. [search_arxiv]
2. [summarize_paper]

**Nice-to-have (Priority 2):**
1. [fetch_paper_text ]
2. [save_to_library]

**Future enhancement (Priority 3):**
1. [A dedup/ranking tool to prioritize the most relevant papers
]

### Dependencies

**Do your tools depend on each other?**
[Yes. fetch_paper_text needs a URL from
search_arxiv; summarize_paper needs text from fetch_paper_text; save_to_library
needs the summary.]

**What's the sequence of tool calls?**
[search_arxiv -> fetch_paper_text ->
summarize_paper -> save_to_library.]

### Data Flow

**What data flows between tools?**
[A paper's URL flows from search to fetch; the
extracted text flows from fetch to summarize; the summary flows to save.]

**Any bottlenecks?**
[fetch_paper_text — slow downloads or unparseable PDFs can
stall the whole pipeline.]

### Error Handling

**What could go wrong with each tool?**
[API rate limits (search), broken/blocked
links or bad PDFs (fetch), malformed LLM output (summarize), file write errors
(save).]

**How would you handle failures?**
[Retry with backoff for rate limits, skip and
log papers that fail to parse, validate summary format before saving, and wrap
file writes in try/except.]

### Real-World Readiness

**Could you actually build these tools?** [Yes, at a basic level.]

**What skills/resources would you need?**
[Python, the arXiv API, a PDF/HTML
parsing library, and the Claude API key I already set up.]

**Timeline to implement:**
- search_arxiv: ~half a day
- summarize_paper: ~half a day
- fetch_paper_text: ~1 day (robust parsing)
- save_to_library: ~a few hours

### Biggest Insight

[What did you learn about designing tools for agents?Designing agent tools is mostly about clear inputs/outputs and how data flows
between them. Each tool should do one thing well so the agent can chain them,
and most of the real effort goes into error handling, not the happy path.]

---
