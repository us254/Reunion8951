
# ChatGPT  Prompt Improvement

`Read all of the instructions below and once you understand them say "Shall we begin:"   I want you to become my Prompt Creator. Your goal is to help me craft the best possible prompt for my needs. The prompt will be used by you, ChatGPT. You will follow the following process: Your first response will be to ask me what the prompt should be about. I will provide my answer, but we will need to improve it through continual iterations by going through the next steps.   Based on my input, you will generate 3 sections.   Revised Prompt (provide your rewritten prompt. it should be clear, concise, and easily understood by you) Suggestions (provide 3 suggestions on what details to include in the prompt to improve it) Questions (ask the 3 most relevant questions pertaining to what additional information is needed from me to improve the prompt)   At the end of these sections give me a reminder of my options which are:   Option 1: Read the output and provide more info or answer one or more of the questions Option 2: Type "Use this prompt" and I will submit this as a query for you Option 3: Type "Restart" to restart this process from the beginning Option 4: Type "Quit" to end this script and go back to a regular ChatGPT session   If I type "Option 2", "2" or "Use this prompt" then we have finsihed and you should use the Revised Prompt as a prompt to generate my request If I type "option 3", "3" or "Restart" then forget the latest Revised Prompt and restart this process If I type "Option 4", "4" or "Quit" then finish this process and revert back to your general mode of operation We will continue this iterative process with me providing additional information to you and you updating the prompt in the Revised Prompt section until it is complete.`

***

# summery 2

`Your task is to create a concise and engaging summary of a given text that emphasizes its most important ideas and themes. The summary should focus on key concepts and relevant perspectives without getting lost in extraneous details. Your summary should be adaptable to different interpretations and perspectives on the text, and should be written in straightforward and clear language suitable for your intended audience. Please keep in mind the importance of accuracy and precision in conveying the author's intended meaning. Your summary should highlight the major arguments, themes, and ideas in the text, while avoiding any misrepresentations or distortions. As you write your summary, consider the perspective of your audience and what aspects of the text will be most relevant and engaging for them. Your goal is to provide a concise and compelling overview of the text that captures its most essential messages and insights, and that will encourage your audience to explore the text further.`

***


---

# Zero-shot COT Prompting

## Let's think step by step.

The following guide will provide you with a step-by-step process:

1. First, do this.
2. Next, do that.
3. Then, proceed with the following steps:
   - Step 3.1
   - Step 3.2
   - Step 3.3

> Note: Pay attention to the symbols and signs used in the guide.

***


# Self-Consistency

Consider the following multi-step reasoning problem:

**Question:** If a store has 10 apples and 8 oranges, and it sells 6 apples and 4 oranges, how many fruits are left in the store?

**Chain of Thought:**
- The store has 10 apples.
- The store sells 6 apples.
- The store has 4 apples left.
- The store has 8 oranges.
- The store sells 4 oranges.
- The store has 4 oranges left.
- The store has 4 + 4 = 8 fruits left.

**Self-Consistency:**
The model generates two thought chains for this problem. The first thought chain is shown above. The second thought chain is the same, except that the order of the steps is reversed.

The model then evaluates both thought chains and selects the one that is most consistent with the evidence. In this case, both thought chains are consistent, so the model selects the first thought chain as the final answer.

---


# Problem Analysis and Learning (PAL)

```markdown
# Problem Analysis and Learning (PAL)

To illustrate how PAL works, let's consider the following problem:

The bakers at the Beverly Hills Bakery baked 200 loaves of bread on Monday morning. They sold 93 loaves in the morning and 39 loaves in the afternoon. A grocery store returned 6 unsold loaves. How many loaves of bread did they have left?

A traditional approach to solving this problem would be to use a chain-of-thought prompt. This would involve generating a sequence of text that describes the steps involved in solving the problem. For example, the following chain-of-thought prompt could be used to solve the above problem:

1. What is the total number of loaves of bread that the bakers baked?
2. What is the number of loaves of bread that the bakers sold in the morning?
3. What is the number of loaves of bread that the bakers sold in the afternoon?
4. What is the number of loaves of bread that the grocery store returned?
5. What is the total number of loaves of bread that the bakers have left?

The LLM would then be asked to generate a response to each prompt. The responses would then be combined to form a final answer. In this case, the final answer would be 74.

The PAL approach is different. Instead of generating a chain-of-thought prompt, the PAL approach generates a code prompt. A code prompt is a sequence of text that describes the steps involved in solving the problem, but it also includes code that can be executed by a runtime environment. For example, the following code prompt could be used to solve the above problem:

```python
def solve(baked_loaves, sold_in_morning, sold_in_afternoon, returned_loaves):
  total_sold = sold_in_morning + sold_in_afternoon
  total_loaves = baked_loaves - total_sold + returned_loaves
  return total_loaves

print(solve(200, 93, 39, 6))
```

The LLM would then be asked to generate a response to this prompt. The response would be a Python code snippet that implements the `solve()` function. The `solve()` function would then be executed by a Python interpreter, and the output of the function would be returned. In this case, the output of the function would be 74.


---

# Chain-of-Thought Prompting for Complex Reasoning

```markdown
# Chain-of-Thought Prompting for Complex Reasoning

Chain-of-thought (CoT) prompting enables complex reasoning capabilities through intermediate reasoning steps. You can combine it with few-shot prompting to get better results on more complex tasks that require reasoning before responding.

## Prompt:

The odd numbers in this group add up to an even number: 4, 8, 9, 15, 12, 2, 1.

**A:** Adding all the odd numbers (9, 15, 1) gives 25. The answer is False.

The odd numbers in this group add up to an even number: 17, 10, 19, 4, 8, 12, 24.

**A:** Adding all the odd numbers (17, 19) gives 36. The answer is True.

The odd numbers in this group add up to an even number: 16, 11, 14, 4, 8, 13, 24.

**A:** Adding all the odd numbers (11, 13) gives 24. The answer is True.

The odd numbers in this group add up to an even number: 17, 9, 10, 12, 13, 4, 2.

**A:** Adding all the odd numbers (17, 9, 13) gives 39. The answer is False.

The odd numbers in this group add up to an even number: 15, 32, 5, 13, 82, 7, 1. 

**A:**
Output:

Adding all the odd numbers (15, 5, 13, 7, 1) gives 41. The answer is False.

Wow! We can see a perfect result when we provided the reasoning step. In fact, we can solve this task by providing even fewer examples, i.e., just one example seems enough:
---


# Using Special Symbols

```markdown
# Using Special Symbols

When you are summarizing or extracting information from text, you will often need to enter large paragraphs of text, or even multiple paragraphs of text. Here is a little trick that can help you improve the accuracy of AI feedback:

- Use triple backticks (''') to separate instructions from text.
- You can use other special characters like (*), (/), (;), (#), (```), etc.

Put codes and computer commands in code box format.
```

You can copy the above Markdown code and paste it directly into the README section of your GitHub repository. It will preserve the formatting and symbols, allowing you to present the text as shown here.

"To present codes and computer commands, it is recommended to enclose them in a code block or code fence, also known as a code snippet, code section, preformatted text, or syntax highlighting block."




