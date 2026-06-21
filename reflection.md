# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?

The game showed a simple interface. The interface had instructions for the user to play the number guessing game in which the user is given 8 attempts to guess the secret number that is between 1 and 100. The game provides three different levels of difficulty: easy, medium, and hard.

- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

The first bug I noticed had to do with entering the first guess and clicking "Enter" on the keyboard. The input provides a small note in the righ-hand side that says "Press Enter to apply." This did not produce the result I expected which was for the app to receive the input and give me feedback.

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

I used Claude Code for identifying and fixing bugs. One example of Claude making a correct suggestion was when it identified the correct lines of code in the Try block of the check_guess function that needed to be fixed for the high/low hint bug. I tested this fix by playing the game again. I noticed that the hints were still occassionally wrong. This is an example of a case where Claude was somewhat incorrect in its fix of the high/low hint bug. It correctly fixed the bug inside of the Try block, but the bug was also present inside of the Except block. I guided Claude to look at the Except block, and after it implemented the bug fix in the Except block, I verified the solution worked by testing the hints in the game.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I determined if a bug was actually fixed by manually testing the fix and by using Claude to run a pytest it created. The pytest failed, which prompted me to look at the test file. I asked Claude to help me determine what the issue was with the test file because the failures appeared to stem from the test cases that came with the source code for the project. Claude pointed out that test cases were incorrectly written for the check_guess function because the function returned a tuple that was directly tested against a string in the tests, which was incorrect. Claude definitely helped in this regard because I had not realized the check_guess function was returning a different data type than what the test expected.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

I did not dig deep into Streamlit for this project. However, in an effort to better answer this question I did some research. Reruns refer to python scripts automatically rerunning to display an updated UI whenever the user interacts with a view. Session state refers to Streamlit caching data locally rather than redoing computations when reruns occur.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects? This could be a testing habit, a prompting strategy, or a way you used Git.
  - I liked the ability to have Claude create and run tests for me. I would like to incorporate this more in future labs and projects because it can be easy to get lazy and not test my code. Claude makes it easy and removes any excuses in this regard.
- What is one thing you would do differently next time you work with AI on a coding task?
  - I would like to figure out a way to keep track of work I have completed and what I was working on when I logged out for the day. I often found myself having to go through my chats with Claude to remember the context of my own work.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
  - This project changed the way I think about AI generated code by helping me learn for myself that AI won't simply edit my code on its own. I was concerned that Claude would make changes that I was not aware of, but this was not the case as it asked me before making edits.
