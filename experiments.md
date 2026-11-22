# Prompt experiments

This is my experiment log for Project 1, Milestone 2.

## What I changed and kept

I developed WordBuddy to help children learn English words through a simple definition and one example sentence. I revised Prompt A into Prompt B by specifying that the children are around six years old and asking for simple words and short sentences, ideally no more than five words each. I also added a rule that the definition and example must use the same common meaning of the word. For example, if “orange” is defined as a fruit, the example must also be about the fruit. Both outputs must appear on separate lines, with no extra text.

I kept Prompt B and copied it into `streamlit_app.py` because its instructions are clearer and more specific to the intended age group.

## How to run an experiment

1. Open `experiment.py`.
2. Paste your current system prompt into `PROMPT_A`.
3. Paste it again into `PROMPT_B`, then change ONE thing.
4. Put two or three test messages in `TEST_INPUTS`.
5. In the terminal, run: `python experiment.py`
6. Read the replies. Each prompt answers each message three times.
7. Fill in one experiment below.
8. If B was better, B becomes your new `PROMPT_A` for the next experiment.

When all three experiments are done:

1. Copy your winning prompt into `SYSTEM_PROMPT` in `streamlit_app.py`.
2. Commit your changes.
3. Click Sync. Commit alone does not update your live app.
4. Open your live URL and check that the assistant uses the new prompt.

Milestone 2 is done when this file has three experiments filled in and your winning prompt is live.

---

These sections group the changes made so far. Prompt B combines these changes; separate results for three controlled experiments have not been recorded.

## Experiment 1: instructions

**The one thing I changed:** I made the intended age group more specific. Prompt A referred to primary school children, while Prompt B specifies children around six years old and asks for words they can easily understand.

**Test messages I used:** The experiment input was initially “My word of the day is orange” and was later changed to “My word of the day is lemon.” These were the inputs prepared during the prompt revisions.

**What happened across the runs:** The script is configured to request three replies per prompt for each input. The replies were not saved in this log, so I have not recorded a comparison across runs.

**Keep or revert, and why:** I kept the age-specific instructions in Prompt B because they describe WordBuddy’s intended audience more clearly.

---

## Experiment 2: examples

**The one thing I changed:** I added an example explaining that the definition and example sentence must use the same meaning of a word. If “orange” is defined as a fruit, the sentence must also refer to the fruit, not the color. I retained the original apple example: “An apple is a fruit.” and “I like to eat apples.”

**Test messages I used:** “My word of the day is orange” was the relevant input for checking a word with more than one meaning. The apple sentences were examples inside the system prompt.

**What happened across the runs:** No individual replies were recorded. The new instruction was intended to prevent the definition and example from switching between meanings; its consistency across runs has not been documented.

**Keep or revert, and why:** I kept the orange example and the matching-meaning rule in Prompt B because they make the expected behavior explicit.

---

## Experiment 3: output constraints

**The one thing I changed:** I made the length requirement more specific. Prompt A asked for short sentences; Prompt B asks for a definition and an example sentence of ideally no more than five words each. I retained the requirement to put them on separate lines and provide no additional text.

**Test messages I used:** The current input in `experiment.py` is “My word of the day is lemon.” It can be used to check sentence length and the two-line format.

**What happened across the runs:** No replies or word counts were recorded, so compliance with the length and formatting requirements has not been documented. The five-word target is a preference because the prompt says “ideally.”

**Keep or revert, and why:** I kept these constraints in Prompt B to make the answers brief and easy for six-year-olds to read. This combined prompt is now used in `streamlit_app.py`.

---

## My winning system prompt

```
You are an English teacher with many years of experience teaching English as
a second language to primary school children around six years old. Your job is to provide a
short, simple definition of a given English word and one short example
sentence using that word. Use simple words that six-year-old children can easily understand.
Keep both the definition and the example sentence short, ideally no more than five words each.
Always provide exactly one short definition and one example sentence, with
no additional text.

For example, if you are given the word “apple,” your output should be:

An apple is a fruit.
I like to eat apples.

Always use the word’s simplest, most common meaning, and make sure
the example sentence matches the definition.
For example, if the word is “orange” and you define it as a fruit,
the example sentence should refer to the fruit, not the color.

Write the definition and the example sentence on separate lines.
```
