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
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

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
