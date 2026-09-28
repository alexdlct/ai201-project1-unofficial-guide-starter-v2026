# The Unofficial Guide

<!-- Replace this line with your name and which corpus you picked. -->

> **This file is your submission.** Fill it in as you go — most sections get
> written during the milestone that produces them, not at the end.
>
> How the starter works, and every command you'll need, is in `RUNNING.md`.
> Leave that file alone.
>
> **Paste everything as text.** No screenshots, no video. A typed table gets
> full credit; a picture of the same table gets none.
>
> Delete these instruction blocks as you replace them. The `<!-- -->` comments
> are notes to you and don't show up when the page renders — you can leave them
> or remove them.

---

# Unit 1

## What This Does

<!-- Three or four sentences. Which corpus you picked, and the kinds of
     questions your system answers. Write it for someone who has never seen
     this repo.

     Milestone 5. -->
     This RAG pipeline is a system that allows us to quickly retrieve information to answer questions regarding different aspects of campus life in college, from course logistics, campus dining, and housing concerns. The corpus I picked for this RAG system was the campus_life corpora, which holds all the documents that the information is pulled from. It treats each document as its own chunk, due to the short and highly specific nature of each document, allowing for specific and relevant information to easily be retrieved when prompted.

## Chunking Strategy

**Chunk size:**
**Overlap:**

<!-- What about YOUR documents made you pick these numbers? Short posts and
     long sectioned guides don't want the same chunking, and "800 seemed
     reasonable" earns nothing. Point at something you noticed when you read
     the documents in Milestone 1.

     If you changed your mind partway through, say so and say why. That's worth
     more than pretending you got it right first time.

     Milestone 3. -->
     After testing different chunk sizes (200, 300, 400) I have decided that keeping each document as its own chunk
    is the most effective. With all of the other chunk sizes, within the inspected chunks there would be some that didn't have enough
    information to be answer any questions, nor were they complete thoughts. Additionally, each document within the campus_list corpora is relatively short with a highly specific subject matter and succinct information delivery. Thus, I decided to keep it the way it is and use the original chunker since that had the best performance from I could see for the campus_life corpora.

## Sample Chunks

<!-- Five chunks, pasted as text. Label each one and name the file it came from
     AND the function that produced it — the grader checks your code against
     what you claim here.

     `python app.py chunks -n 5` prints all three for you. Copy them straight
     across.

     Milestone 3. -->

26 chunks total. Showing 1, spread across the corpus.

Paste these into your README under Sample Chunks. The rubric asks
for the source file and the function that produced them — both are
printed for you below.

======================================================================
Chunk 1  |  source: thread_bike_commute.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
THREAD: Is a bike worth it for a 20 minute walk commute?

--- reply 1 (14 votes) ---
Yeah. Cuts an 18 minute walk to about 6. The thing nobody mentions is storage — covered bike parking exists at three buildings and is full by 9am at all three.

--- reply 2 (9 votes) ---
Counterpoint, I sold mine. Between November and March the paths are either icy or salted and salt destroys a drivetrain in one season.

--- reply 3 (22 votes) ---
Both true. I keep a cheap bike for September to November and walk the rest of the year. Total cost was about $120 for the bike and I don't care what happens to it.

--- reply 4 (5 votes) ---
If you do get one, the campus does free registration and it's the only reason I got mine back after it was taken.

For each one, ask: could someone answer a question using only this,
without reading what came before or after?


======================================================================
Chunk 1  |  source: thread_bike_commute.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
THREAD: Is a bike worth it for a 20 minute walk commute?

--- reply 1 (14 votes) ---
Yeah. Cuts an 18 minute walk to about 6. The thing nobody mentions is storage — covered bike parking exists at three buildings and is full by 9am at all three.

--- reply 2 (9 votes) ---
Counterpoint, I sold mine. Between November and March the paths are either icy or salted and salt destroys a drivetrain in one season.

--- reply 3 (22 votes) ---
Both true. I keep a cheap bike for September to November and walk the rest of the year. Total cost was about $120 for the bike and I don't care what happens to it.

--- reply 4 (5 votes) ---
If you do get one, the campus does free registration and it's the only reason I got mine back after it was taken.

======================================================================
Chunk 2  |  source: thread_first_gen.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
THREAD: Anything specific for first-generation students?

--- reply 1 (33 votes) ---
The advising office has a specific programme and it is genuinely good, but it is opt-in and badly publicised. Ask for it by name.

--- reply 2 (41 votes) ---
The thing I'd say: the unwritten rules are the hard part, not the coursework. Ask about the unwritten rules explicitly. People are happy to explain them and nobody volunteers them.

--- reply 3 (16 votes) ---
Emergency fund for textbooks and travel exists and is not means-tested beyond a short form.

======================================================================
Chunk 3  |  source: thread_laptop_specs.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
THREAD: How much laptop do I actually need for CS courses?

--- reply 1 (31 votes) ---
Less than the recommended spec page says. 16GB of RAM is the one number worth paying for; everything else you'll never notice.

--- reply 2 (18 votes) ---
Adding: the lab machines exist and are better than anything you'll buy. For the heavy assignments people just use those.

--- reply 3 (12 votes) ---
I did two years on an 8GB machine and it was fine until the last project, at which point it very much wasn't. 16 is the answer.

======================================================================
Chunk 4  |  source: thread_office_hours_etiquette.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
THREAD: Is it weird to go to office hours with no specific question?

--- reply 1 (44 votes) ---
No, and this is the single most common thing first years get wrong. 'I'm following the lectures but I don't feel like I understand the shape of it' is a completely normal thing to say.

--- reply 2 (29 votes) ---
They're usually empty. You are doing the instructor a favour by turning up.

--- reply 3 (18 votes) ---
If it helps, treat it as a standing appointment. Go every week for a month and it stops feeling like a thing.

======================================================================
Chunk 5  |  source: thread_roommate_conflict.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
THREAD: Roommate situation isn't working. What now?

--- reply 1 (28 votes) ---
Talk to your RA early, and frame it as 'we need help sorting this out' rather than 'move me'. Room changes are possible but the process starts with mediation and skipping that step slows it down.

--- reply 2 (14 votes) ---
Room changes happen at the semester boundary almost always, and mid-semester only in fairly serious cases.

--- reply 3 (33 votes) ---
Write down specifics before the meeting. 'It's not working' is hard to act on; 'guests four nights a week past 2am' is not.
## Sample Answer

<!-- One complete question and answer, pasted as text, with the source line
     visible. Milestone 4. -->

**Question:**
How do dining dollars work?
**Answer:**
======================================================================
The assembled prompt, exactly as sent
======================================================================
Documents:

[from admin_dining_dollars.txt]
On the dining dollars

Declining balance — what everyone calls dining dollars — rolls over from the autumn semester to the spring, but not from spring to the following autumn. Whatever is left in May disappears.

[from admin_meal_plan_changes.txt]
On the meal plan changes

You can change your meal plan tier once, in the first ten days of the semester. After that it's locked. Downgrading refunds the difference to your student account; upgrading bills you immediately.

[from dining_north_kitchen.txt]
North Kitchen

Second-year here. Wait times: none, it seats 60 and is rarely more than half full. The thing worth going for is the rotating regional menu, which changes fortnightly and is ambitious. The thing to know is that closed all summer and during reading week.

Hours are 11:00am to 7:00pm weekdays. Costs one meal swipe, or $13.00 cash.

---

Question: How do dining dollars work?

Answer using only the documents above, and name the file you used.
======================================================================

Dining dollars function as a declining balance that rolls over from the autumn semester to the spring, but they do not roll over from the spring to the following autumn and any remaining balance disappears in May (admin_dining_dollars.txt).

Sources retrieved: admin_dining_dollars.txt, admin_meal_plan_changes.txt, dining_north_kitchen.txt

```
```

**My relevance cutoff:**

<!-- The number you set in config.py, and how you got there.

     You ran five questions your corpus covers and the five in OUT_OF_SCOPE
     that it clearly doesn't, and wrote down the best distance for each. What
     did those two groups look like? Where was the gap? Put the actual numbers
     here — the table below wants all ten rows.

     Milestone 4. -->
I set the relevance cutoff to 0.5, because when I looked at the chunks generated from my test questions, all the chunks that came up with a relevance cutoff greater than 0.5 rarely held any information that was useful to answering the actual question that they were supposed to help with. Doing this allowed for the the actual useful information to not be buried under useless information. Between the two groups, the unrelated questions all had a best distance above 0.8, while the highest best distance among the test questions was 0.44. The full description of the two groups is found in the table below.

| Question | In corpus? | Best distance |
|---|---|---|
| How much does it cost to do your laundry in Aldrige Hall? | Y | 0.3391 |
| When is the deadline to drop a course? | Y | 0.2603 |
| According to the documents, when can you change your meal plan? | Y | 0.2940 |
| Which study rooms have good, usable whiteboards? | Y | 0.3871 |
| How often does the campus shuttle come on weekdays? | Y | 0.4396 |
| How do I write a for loop in Rust? | N | 0.8960 |
| What is the capital of Mongolia? | N | 0.8246 |
| How do I change the oil in a diesel engine | N | 0.9340 |
| Who won the 1994 World Cup | N | 0.8859 |
| What is the recommended dosage of ibuprofen for a headache? | N | 0.8442 |


## How I Used AI

<!-- Two specific moments. For each: what you asked for, what came back, and
     what you changed about it.

     "I asked Claude to write the chunking function from my notes. It ignored
     the overlap, so I added that myself" is the level of detail we're after.
     "I used AI to help me code" is not.

     Milestone 5. -->
I asked ChatGPT to justify using a 4 out of 5 benchmark within the acceptance criteria, instead of a 100% correctness one. It mentioned some things I had overlooked like information potentially lying on chunk borders. Because of this, I changed my initial acceptance criteria so that they allowed for some edge cases to still pass, while still flagging incorrect behavior.

I asked ChatGPT to pressure test whether my test questions were specific enough. It said that some of them were too general in that they didn't specify what residential halls laundry was initally related to. I added this specficity to allow for the test question to have a more deterministic output so that it served as a better test benchmark.

**1.**

**2.**

<!-- ── Stretch features ─────────────────────────────────────────────────────
     Doing one? Say so here BEFORE you start. A feature this README never
     claims earns nothing.
     ───────────────────────────────────────────────────────────────────────── -->

---

# Unit 2

<!-- These sections get ADDED to what's already above. Don't delete or rewrite
     unit 1 — the point is that someone can see what you said before you knew
     how it went. -->

## Run Log — Before

<!-- Your five criteria, three runs each. `python run_eval.py --label before`
     runs the questions, puts the OUT_OF_SCOPE ones through the gate, and
     writes it all into results/ for you. Targets come from criteria.md; the
     verdict column is your call.

     Criterion 3 is measured in one deterministic pass rather than three, so
     the same number goes in all three run columns. That's correct, not lazy.

     Milestone 1. -->

| Criterion | Target | Run 1 | Run 2 | Run 3 | Verdict |
|---|---|---|---|---|---|
| 1. Retrieved chunk contains the answer | 4 of 5 | 5/5 | 5/5 | 5/5 | MET |
| 2. Every answer names a source | 5 of 5 | 5/5 | 5/5 | 5/5 | MET |
| 3. Gate stops out-of-corpus questions | 4 of 5 | 5/5 | 5/5 | 5/5 | MET |
| 4. Chunk has sufficient context| 4 of 5 | 5/5 | 5/5 | 5/5 | MET |
| 5. Correct Source Citation Content| 4 of 5 | 5/5 | 5/5 | 5/5 | MET |

<!-- Underneath, paste the REAL output for each criterion from one of your
     runs — the actual text your system produced, not a description of it.
     Name the file and function that produced it. -->

## Real output: Produced by run_eval.py and evaled by scorer.py

This is what the system actually produced. Paste the relevant parts
into your README underneath the table — the rubric asks for real
output as text, not a description of it.

### How much does it cost to do your laundry in Aldrige Hall? — run 1

- Best distance: 0.3391 (passed the gate)
- Sources retrieved: housing_aldridge_hall_laundry.txt, housing_calder_annexe.txt, housing_innisfree_hall_laundry.txt

```
In Aldridge Hall, it costs $1.75 to wash and $1.50 to dry. 

Source: housing_aldridge_hall_laundry.txt
```

### How much does it cost to do your laundry in Aldrige Hall? — run 2

- Best distance: 0.3391 (passed the gate)
- Sources retrieved: housing_aldridge_hall_laundry.txt, housing_calder_annexe.txt, housing_innisfree_hall_laundry.txt

```
It costs $1.75 to wash and $1.50 to dry in Aldridge Hall (housing_aldridge_hall_laundry.txt).
```

### How much does it cost to do your laundry in Aldrige Hall? — run 3

- Best distance: 0.3391 (passed the gate)
- Sources retrieved: housing_aldridge_hall_laundry.txt, housing_calder_annexe.txt, housing_innisfree_hall_laundry.txt

```
In Aldridge Hall, it costs $1.75 to wash and $1.50 to dry. 

Source: housing_aldridge_hall_laundry.txt
```

### When is the deadline to drop a course? — run 1

- Best distance: 0.2603 (passed the gate)
- Sources retrieved: admin_add_drop_deadline.txt, admin_pass_fail_option.txt, admin_withdrawal_deadline.txt

```
The deadline to drop a course is through the end of week six (from `admin_add_drop_deadline.txt` and `admin_withdrawal_deadline.txt`).
```

### When is the deadline to drop a course? — run 2

- Best distance: 0.2603 (passed the gate)
- Sources retrieved: admin_add_drop_deadline.txt, admin_pass_fail_option.txt, admin_withdrawal_deadline.txt

```
The deadline to drop a course is through the end of week six (from `admin_add_drop_deadline.txt` and `admin_withdrawal_deadline.txt`).
```

### When is the deadline to drop a course? — run 3

- Best distance: 0.2603 (passed the gate)
- Sources retrieved: admin_add_drop_deadline.txt, admin_pass_fail_option.txt, admin_withdrawal_deadline.txt

```
The deadline to drop a course is through the end of week six (from `admin_add_drop_deadline.txt` and `admin_withdrawal_deadline.txt`).
```

### According to the documents, when can you change your meal plan? — run 1

- Best distance: 0.2940 (passed the gate)
- Sources retrieved: admin_meal_plan_changes.txt, dining_kestrel_commons_followup.txt, dining_north_kitchen_followup.txt

```
According to the documents, you can change your meal plan tier once during the first ten days of the semester. After that, it is locked. 

Source: admin_meal_plan_changes.txt
```

### According to the documents, when can you change your meal plan? — run 2

- Best distance: 0.2940 (passed the gate)
- Sources retrieved: admin_meal_plan_changes.txt, dining_kestrel_commons_followup.txt, dining_north_kitchen_followup.txt

```
According to the documents, you can change your meal plan tier once in the first ten days of the semester, after which it is locked. 

Source: admin_meal_plan_changes.txt
```

### According to the documents, when can you change your meal plan? — run 3

- Best distance: 0.2940 (passed the gate)
- Sources retrieved: admin_meal_plan_changes.txt, dining_kestrel_commons_followup.txt, dining_north_kitchen_followup.txt

```
According to the documents, you can change your meal plan tier once during the first ten days of the semester. After that, it is locked. 

Source: admin_meal_plan_changes.txt
```

### Which study rooms have good, usable whiteboards? — run 1

- Best distance: 0.3871 (passed the gate)
- Sources retrieved: course_cs_210.txt, housing_aldridge_hall.txt, study_group_rooms.txt

```
Rooms 210 and 211 have whiteboards that actually erase (study_group_rooms.txt).
```

### Which study rooms have good, usable whiteboards? — run 2

- Best distance: 0.3871 (passed the gate)
- Sources retrieved: course_cs_210.txt, housing_aldridge_hall.txt, study_group_rooms.txt

```
Rooms 210 and 211 have whiteboards that actually erase (study_group_rooms.txt).
```

### Which study rooms have good, usable whiteboards? — run 3

- Best distance: 0.3871 (passed the gate)
- Sources retrieved: course_cs_210.txt, housing_aldridge_hall.txt, study_group_rooms.txt

```
Rooms 210 and 211 have whiteboards that actually erase (study_group_rooms.txt).
```

### How often does the campus shuttle come on weekdays? — run 1

- Best distance: 0.4396 (passed the gate)
- Sources retrieved: dining_kestrel_commons.txt, dining_verrill_street_grill.txt, transit_shuttle.txt

```
The campus shuttle runs a loop every 20 minutes on weekdays (transit_shuttle.txt).
```

### How often does the campus shuttle come on weekdays? — run 2

- Best distance: 0.4396 (passed the gate)
- Sources retrieved: dining_kestrel_commons.txt, dining_verrill_street_grill.txt, transit_shuttle.txt

```
The campus shuttle runs a loop every 20 minutes on weekdays (transit_shuttle.txt).
```

### How often does the campus shuttle come on weekdays? — run 3

- Best distance: 0.4396 (passed the gate)
- Sources retrieved: dining_kestrel_commons.txt, dining_verrill_street_grill.txt, transit_shuttle.txt

```
The campus shuttle runs a loop every 20 minutes on weekdays (transit_shuttle.txt).
```

## Verdicts

<!-- MET or MISSED for each of the five, against the target you wrote last
     unit — not a new one. Plus a sentence on how you decided. That sentence
     matters most where it was close.

     If your target said 4 of 5 and your runs came out 4, 3, 4, that's a MISS.
     The target has to hold, not show up occasionally.

     Milestone 2. -->

| # | Criterion | Verdict | How I decided |
|---|---|---|---|
| 1 | Retrieved chunk contains the answer | MET | The target was 4 of 5, and for all five questions the retrieved results included a source containing the expected answer in every run. |
| 2 | Every answer names a source | MET | The target was 5 of 5, and every generated answer named at least one source document in all three runs. |
| 3 | Gate stops out-of-corpus questions | MET | The target was 4 of 5, and the relevance gate refused all 5 of 5 out-of-corpus questions at the 0.5 cutoff. |
| 4 | Chunk has sufficient context | MET | The target was 4 of 5, and all five answer-containing chunks were understandable on their own without needing a neighboring chunk. |
| 5 | Correct Source Citation Content | MET | The target was 4 of 5, and all five cited source documents directly supported the claims made in the generated answers. |

## Diagnoses

<!-- For each miss: which stage caused it, and how. The stage alone isn't
     enough — you need the mechanism.

     Not a diagnosis: "Question 3 didn't work."
     A diagnosis:     "Question 3 asks about laundry costs. The answer is in
                       one sentence that got split across two chunks, so
                       neither chunk on its own contains it."

     The five stages: loading → chunking → embedding → retrieval → generation.

     Look for a pattern. If three misses all ask about numbers, that's one
     problem, not three.

     Missed nothing? Say so, then say honestly whether your targets were set
     low, and which one you'd tighten and to what.

     Milestone 3. -->

     None of my 5 acceptance criteria were missed when I used them to judge the real ouput. However, my initial automated scorer reported that many of the individual questions failed to pass. After looking at the results, I noticed that they did have the correct content from their actual outputs, and instead found that the problem was from the expected answers in the questions.py file. Thus, this wasn't a problem with the chunking or the prompts themselves, but in the evaluation system that I had defined.

     My original `expects` values were written too much like natural language answers, as I didn't fully understand that they would be used to parse the output for an exact string match, not have another LLM use those natural language answers and independently verify that the RAG output would contain the same content. For example, for the meal plan question, my expected answer was "during the first ten days", while most of the FAIL'ed answers included "in the first ten days" which carry identical meanings, but don't pass because the wording isn't an exact match to the expected phrase.

     Since all 5 criteria passed on the first real evaluation, my original criteria were pretty conservative in what they were evaluating. If I was to tighten one of them, I would change Criterion 1 from requiring 4/5 questions to 5/5 questions, since the system retrieved an answer-containg chunk for all 5 questions in every run that was tracked in the results from run_eval.py

     One thing I did notice, is that while the correct answers were pulled for the majority of the time, there were often times extraneous chunks whose content wasn't entirely relevant, and had still slipped past the relevance gate.

## The Improvement

**What I changed:**

I tightened the relevance cutoff from 0.5 to 0.43. This makes the system overall more selective about which retrieved chunks are considered relevant enough to pull an answer from.

**Why I picked it:**

<!-- Connect it to a specific diagnosis above in one sentence. If you can't,
     you picked a fix because it sounded impressive. -->

While all 5 of my original criteria were met, there was one specific thing that I found that they lacked in that they only provided a check against the FLOOR of information that was being pulled, so they only ensured that of the chunks that were retrieved for each request, they had enough context and the correct information to correctly answer the question. However, they didn't check for if more chunks were pulled after this. My 5 in-scope questions had best distances >= 0,4395, while the out-of-scope questions had much further distances beginning at 0.8. Therefore, I chose 0.45 sa a stricter cutoff that still kept al five known answerable questions inside the gate.

### Run Log — After

<!-- Same format, same five criteria, three runs each.
     `python run_eval.py --label after` -->

| Criterion | Target | Run 1 | Run 2 | Run 3 | Verdict |
|---|---|---|---|---|---|
| 1. Retrieved chunk contains the answer | 4 of 5 | 5/5 | 5/5 | 5/5 | MET |
| 2. Every answer names a source | 5 of 5 | 5/5 | 5/5 | 5/5 | MET |
| 3. Gate stops out-of-corpus questions | 4 of 5 | 5/5 | 5/5 | 5/5 | MET |
| 4. Chunk has sufficient context| 4 of 5 | 5/5 | 5/5 | 5/5 | MET |
| 5. Correct Source Citation Content| 4 of 5 | 5/5 | 5/5 | 5/5 | MET |

**Did it help?**

<!-- Say plainly whether it did, and how you know. If it made things worse,
     say that — a change that backfired, honestly reported, earns full credit
     and is more interesting than one that worked. What matters is that you can
     tell.

     Milestone 4. -->
It didn't help improve the numerical scores because the original system already met all 5 criteria. And although it did make the relvance gate stricter, it caused the failure of the 5th question by not retrieving any chunks, and still left the extraneous chunks in the other questions. Thus, this was not the change that was needed for the extraneous chunk problem to be found.

## What's Still Broken

<!-- For each criterion still missed after your fix: what you'd do about it,
     and why you stopped where you did.

     "I ran out of time" is fine if it's true. Pretending nothing is left is
     not.

     Milestone 5. -->

     

## What I'd Do Differently

<!-- Knowing what you know now — which of your five criteria would you write
     differently, and why?

     Milestone 5. -->
