# Model evaluation template

This template is meant to act as a structured entry to write an evaluation document.

## The model

- [ ] Name
- [ ] General description
- [ ] Relevant links (Github, huggingface)
- [ ] Parameter count
- [ ] Context size

## Hardware requirement estimations

- [ ] For running unquantized?
- [ ] For runnning quantized?

## Recommended set-up

- [ ] model settings: temperature, sampler, top_p, top_k, etc...
- [ ] system prompt template
- [ ] Preferred quantization

## Evaluation set-up

- [ ] Used model settings
- [ ] The seed for each prompt must be provided, preferably only once per document. Otherwise must be mentioned in the prompt result itself.

## Set-up instructions

- Oogabooga
- llama.cpp
- ?

### Evaluation summary

A short summary on the overall performance, it should include at least the following:

- [ ] How does it do in general?
- [ ] Does it have any clear weaknesses or strengths?
- [ ] Is it something you would consider using? Some models simply aren't worth using at all. Others are more about tradeoffs (one will be better at python, the other better at Go), and sometimes a model is just clearly a cut above the rest.

### Evaluation prompts

For each prompt, format as follows:

#### Prompt title

- [] A short description of the prompt's purpose
- [ ] The prompt itself in a codeblock
- [ ] The output in a codeblock, use the relevant programming language syntax highlighting wherever relevant
- [ ] A discussion on the output
  - Not all of the questions are required, this is a general idea of what to write about.
  - [ ] If it has runnable code: is it correct?
  - [ ] Is it idiomatic?
  - [ ] Could it have been done differently?
  - [ ] Would you have done it differently?

```
Prompt in a codeblock
```

```
Output in a codeblock
Manually add word wraps for readability if needed
```

Discuss output.

For example:

#### Story time

This prompt is meant to test the model's coherence and output speed. It's a good test to see if the model is "sane"

```
Tell a short story about the worst bug you've had to fix in your career.
```

```
Once upon a time, I encountered a critical bug in a large-scale project that affected thousands of users.
The bug caused the application to crash unexpectedly and corrupt data.
After extensive debugging and analysis, I identified the root cause as an improperly handled exception in a complex algorithm.
Fixing this issue required rewriting several lines of code and updating unit tests to ensure stability.
Thanks to my diligence and attention to detail, the bug was resolved within hours, preventing further damage and restoring user confidence in the application.
The moral of the story is that even the most experienced developers can face challenges, but persistence and a strong problem-solving mindset can lead to successful resolutions.
```

The answer seems both generic and vague, it _is_ clearly coherent however. Given that the question was vague and didn't explicitly ask for a "real scenario with examples" the answer is clearly a pass.
