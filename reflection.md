# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

  -The first bug was hints were completely wrong, on normal mode i submitted 5 guesses starting from 5 and going down by one each guess. 5,4,3,2,1. It kept saying go lower. None were the coorect answer and for normal it starts from 1-20 so any lower would have been impossible 
  -Second concrete bug is the game not updatiing at all when finshing the game for the first time, it does not allow for any more chances once first game is done. the button new game does not give any more new attempts but it does update the secret.
  - another bug is the games for both easy and normal they are capped at 1-10 and 1-100 the game secret is almost always above the cap numbers for easy. 
  - game mode hard is only 1-50 which is the opposite of and thats what normal should be.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| New game | New attempts given| No new attempts given| No output only update to new number|
| Diffcutly Hard| Should Give range 1-100| Gives range 1-50| "GO HIGHER" when submitting the max range for hard which is capped at 50|
| guess of 55| "GO HIGHER" | "GO LOWER"| none|
|random guesses between 1-100| game should save and accordinly reflect number of attempts| does not save and gives inaccurate attempts left| Game over.  Guess a number between 1 and 100. Attempts left: 1Start a new game to try again|

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
I used Copilot and Claude 

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).

An AI suggestion that was correct, I asked the AI to move check_guess out of app.py and into logic_utils.py, and to update the import in app.py. It moved the function with my high/low fix included, deleted the old copy from app.py, and added from logic_utils import check_guess at the top. To check it, I looked over the diff for each file it changed. Then I ran python -m pytest, and all 4 tests passed. I also ran the game with streamlit run app.py and tried guesses above and below the secret number. The hints pointed the right way: "Go LOWER" when I was too high and "Go HIGHER" when I was too low.


- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

An AI suggestion I didn't accept as written, When I ran plain pytest, I got an error saying it couldn't find logic_utils. The AI explained that plain pytest only looks in the tests folder, and it suggested adding a pytest.ini file with pythonpath = . so the command would always work. That would have fixed it, but it meant adding a config file the assignment didn't ask for, and I wanted to stick to the prompt. So I took the other option it gave me and ran python -m pytest, which finds the main folder without any extra files. When I ran it that way, all 4 tests passed, so I didn't need the extra file.



---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I decided a bug was really fixed when it passed in two places, the pytest tests and the actual game. For the hints bug I didn't trust the code just because it looked right, I ran streamlit run app.py, opened Developer Debug Info to see the secret, and guessed above and below it. Going over the secret said "Go LOWER" and going under said "Go HIGHER", which is the opposite of what it did before. For the second bug, the secret was getting turned into a string on every other attempt, so comparing my guess to it was messed up. After I took that out, I submitted a bunch of guesses in a row and the hints stayed right every time instead of flipping.

- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  The main pytest test I ran was test_hint_direction_matches_outcome, which checks that a guess of 60 with a secret of 50 says "Too High" and "LOWER", and a guess of 40 says "Too Low" and "HIGHER". When I first ran pytest, all 3 starter tests failed, but not because the game was broken. The tests expected check_guess to return just "Win", and it actually returns two things, the outcome and the message. That showed me the tests have to match what the function really returns, not what you assume it returns. After updating them, all 4 tests passed with python -m pytest.
- Did AI help you design or understand any tests? How?
AI helped me with both. I had it write the new test aimed at the high/low bug, and I read through it to make sure it was checking the hint direction and not just the outcome. It also explained why the 3 starter tests were failing, and why plain pytest couldn't find logic_utils but python -m pytest could, which I wouldn't have figured out as fast on my own.


---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
