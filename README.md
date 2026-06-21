# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [X] Describe the game's purpose.
    - The purpose of the game is to allow a user a limited number of attempts to correctly guess a secret number.
- [X] Detail which bugs you found.
    - I found three bugs. The first bug had to do with pressing Enter on the keyboard and the game not receiving the input. The input was only received after clicking the Submit Guess button. The second bug I found had to with the game giving incorrect hints. For example, if the user guessed a number already lower than the secret number, the game would tell the user to go lower. The third bug had to with the game not warning the user when they guess values that were outside of the given range. For example, if the range was 1 to 100 and the user guessed 0, the user was not told they were out of range.
- [X] Explain what fixes you applied.
    - I corrected the high/low bug by using Claude to correctly provide the correct hints to users when their guesses are too low or too high. I also implemented a fix so that users are given a warning when their guesses are outside of the given range of possible values.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. User enters a number within the specified range: 13
2. The guess is too low, so the game tells the user to GO HIGHER!
3. The user enters 50
4. The guess is too high, so the game tells the user to GO LOWER!
5. The user enters 30
6. The game tells the user they guessed correctly and shows some balloons.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
# pytest tests/
# ========================= X passed in 0.XXs =========================
```
```
====================================================================== test session starts =======================================================================
platform win32 -- Python 3.14.5, pytest-9.0.3, pluggy-1.6.0 -- C:\Users\hordo\Projects\ai110-module1show-gameglitchinvestigator-starter\.venv\Scripts\python.exe
cachedir: .pytest_cache
rootdir: C:\Users\hordo\Projects\ai110-module1show-gameglitchinvestigator-starter
plugins: anyio-4.13.0
collected 5 items                                                                                                                                                 

tests/test_game_logic.py::test_winning_guess PASSED                                                                                                         [ 20%]
tests/test_game_logic.py::test_guess_too_high PASSED                                                                                                        [ 40%]
tests/test_game_logic.py::test_guess_too_low PASSED                                                                                                         [ 60%]
tests/test_game_logic.py::test_too_high_hint_says_go_lower PASSED                                                                                           [ 80%]
tests/test_game_logic.py::test_too_low_hint_says_go_higher PASSED                                                                                           [100%]

======================================================================= 5 passed in 0.05s ========================================================================

```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
