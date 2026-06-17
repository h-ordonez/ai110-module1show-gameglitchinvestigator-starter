# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?

The game showed a simple interface. The interface had instructions for the user to play the number guessing game in which the user is given 8 attempts to guess the secret number that is between 1 and 100. The game provides three different levels of difficulty: easy, medium, and hard.

- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

The first bug I noticed had to do with entering the first guess and clicking "Enter" on the keyboard. The input provides a small note in the righ-hand side that says "Press Enter to apply. "This did not produce the result I expected which was for the app to receive the input and give me feedback.

The second bug I noticed had to with the number of attempts. I expected the number of attempts to decrease after submitting my first guess. The number of attempts stayed the same at 7.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
|Pressing enter|App would produce a hint|No hint was given|None|
|13|Hint indicating to guess higher|Hint indicated to guess lower|None|
|0|Warning that guess was not in range|Hint indicated to guess lower|None|

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
