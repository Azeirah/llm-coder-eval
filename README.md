# llm-coder-eval

What local Large Language Model (LLM) do you choose as your coding assistant? This is difficult to easily decide; to pick a model you need to find the right balance between output quality and hardware requirements. Of course that juicy 70B finetune is the best, but that won't run on your 3060. At the same time, that Camelid-13B-V2 is a great roleplaying model, but is it any good at Go?

This Repository intends to build a framework for evaluating models for exactly this. Day-to-day performance as a coding assistant for software developers.

Here are our principles

- 🔨 **It's a tool**: The questions are not meant to be interview questions, the LLM is meant to assist you during coding, it's not your next hire.
- 🔋 **Batteries included** More than just coding: A good assistant can help you with coding-adjacent tasks as well: Regular Expressions, Shell globbing, linux commandline, Windows powershell, AWS and Azure, etc.
- 👩🏽‍💻 **Human evaluated** No automated testing: Each prompt and output is to be evaluated by a software engineer with relevant experience by hand, adding nuanced commentary on how the model did, if it could have done different, if the output is correct, etc.
- 📏 **Nuanced evaluation** Similarly, no single score: You want a great model? The only way you can really know if it's any good is by using it. This evaluation is meant to replicate a thorough "test run" with realistic questions.
