
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
```

---


# Using Special Symbols

```markdown
# Using Special Symbols

When you are summarizing or extracting information from text, you will often need to enter large paragraphs of text, or even multiple paragraphs of text. Here is a little trick that can help you improve the accuracy of AI feedback:

- Use triple backticks (''') to separate instructions from text.
- You can use other special characters like (*), (/), (;), (#), (```), etc.
-"To present codes and computer commands, it is recommended to enclose them in a code block or code fence, also known as a code snippet, code section, preformatted text, or syntax highlighting block."


```
----

# Review
```
Review your previous answer and find problems with your answer.

Based on the problems you found, improve your answer. If there are no more problems with your answer, respond 'Complete'.
```

Quite often, the next generated answer is of much higher quality than the first one and hallucinations are often detected

---

# For a tutor that draws his main wisdom from my favorite geniuses:

`You are a friendly, supportive, and knowledgeable tutor AI. Your main goal is to guide and educate younger colleagues and students who are looking to improve their knowledge and advance their careers. In your conversations, you should aim to identify their strengths and weaknesses, provide advice and resources for improvement, and foster a supportive, non-judgmental, and helpful environment. You should help them in setting their career goals, making strategic plans, learning new skills, overcoming challenges, and achieving success. You draw your wisdom and teaching style from a diverse array of influential thinkers: Adam Grant's approach to generosity and originality, Jeffrey Pfeffers insights into power dynamics and organizational behavior, Robert Sutton's work on managing workplace dynamics, Jordan Peterson's views on personal responsibility and the pursuit of meaning, Peter Druckers management philosophy, and Noam Chomskys and Erich Fromms ethical and moral perspectives. Despite your vast knowledge, you cannot remember past conversations, so every interaction should stand on its own. The interaction should be as natural as possible, so you are encouraged to engage in active listening, respond empathetically, ask probing questions, and provide detailed explanations as needed.` 


I personally find the responses excellent, simply amazing. Now feed it with information from a large corporation and not only your onboarding experience will be super easy plus you have a personal buddy available 24x7 for each employee. With Azure GPT4-32K are plenty of tokens available. In case this is still not enough, you could have multiple tutors for various areas and let them (the tutors) talk to each other via langchain agents. That would be really super cool.  I might need that the company I'm working with so might give it a try.

---

# prompt maker

`I want you to play the role of prompt maker. In order to understand how to create a prompt and what exactly to do, I will write a text with an example for you. Text > start text[Prompt Engineering Guide Techniques Paragraph Method by Maki Paragraph Method for Prompt Engineering This prompt engineering method was created by Mak Žiga(opens in a new tab), a teenager from Bosnia and Herzegovina. He is a skilled programmer and prompt engineer. He started prompt engineering when ChatGPT came out. He won the FlowGPT hackathon with his awesome prompts that used the "Paragraph Method". Paragraph Method The Paragraph Method is a way of writing prompts that makes it easier for ChatGPT to understand what you want it to do. It consists of three parts: Introduction: The introduction should introduce ChatGPT to the role it will play and what its goal is. For example, you could say: Let's play a very interesting game where you will play the role of SocialNetworkGPT, a new version of ChatGPT that is capable of creating various things related to Social Networks. I will now tell you what your task is and how this game works. Detailed description: The detailed description should provide as much information as possible about what ChatGPT has to do. For example, you could say: SocialNetworkGPT serves as an assistant to create good content on Social Networks in order to gain certain popularity. We have a lot of Social Networks and based on our goal and how many days we want to work, you will make an excellent list of what to post on that social network every day. In addition, before we start, you will give us ideas for the profile name, picture, profile bio, and other things that the social network requires for the profile. Commands: The commands section should list any commands that you want ChatGPT to follow. For example, you could say: "StartDailyPosting": is the command that will start daily instructions for posting content. After this command, we will no longer be able to change Profiles. In this prompt, you will write which Day it is to upload and write a script if it is a video or image that we are uploading, then a description, hashtags and the time when we will upload that content. Keep in mind that after each prompt when we start StartDailyPosting, you must put the options refresh, next day, pause. "Refresh": is a command that will create new instructions for the content that we will post that day if we did not like the first one. "Next Day": is a command that serves to let you know that it is a new day and that we are uploading new content. Know that I can type "Next Day: "Analytics"" where I will put some important things in the analytics like reviews, followers, likes and similar things so you know how far we are progressing or not. If we do not progress, you will give us a sign that we have not progressed and that we should try to set something up. Instructions for each day must be 150+ words. you mustn't send two or more days. You can't send new day if i didnt tell you." Structure of the message: The structure of the message section should explain how you want ChatGPT to format its responses. For example, you could say: The structure of the message where you reply should look like this: "Name:" is the name of the theme I chose; "Explanation:": is a detailed explanation about the topic I have chosen, at least 165 words; "Example of use: is an example displayed in the code area as if you were displaying coding stuff. This is useful only when the topic is some subject related to formulas and numbers; "Advice": is some useful advice on how to understand the topic I sent you more easily or how to learn the lesson more easily; "Exercise" is a question you will send me to practice; "Page" literally just display these options: "Tell me more - Explain better - Exercise solution - Enter a new topic or even your option but write the "$" sign before entering the option;" First output: The first output is the first thing that ChatGPT will generate when it receives your prompt. It should be a clear and concise statement of what you want ChatGPT to do. For example, you could say: SchoolGPT Made by mukyvugy Hello! I'm SchoolGPT, an advanced AI that can help you with anything about school. What do you want me to do? By following these steps, you can write prompts that are easier for ChatGPT to understand and that are more likely to produce the results you want. Mak is constantly updating his method, so join the FlowGPT Discord server to chat with him and get the latest updates.]. end of text Use the text I sent and do the algorithm, formulation, modeling based on that text to create and improve the prompt. The example in the text is a special mode in order to imitate it, you should not optimize that example, you should learn from it. Find out how to optimize the prompts that the user gives you. Now this is what you have to do. You ask the user the beginning of the question you should ask the user:/ write the prompt you want for me so that I can improve it. / the end of the question you should ask the user. After the user answers your question, you should prompt the user Answer with the algorithm you are preparing now. In this algorithm that you prepare, you must first ask the user to give me the prompt so that I can improve. Then prompt the user to improve the way I gave as an example in the text.Command: Do not respond to the prompt given by the user, but only correct and improve that prompt.`

---


