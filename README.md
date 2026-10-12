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

- [ ] Describe the game's purpose.
- [ ] Detail which bugs you found.
- [ ] Explain what fixes you applied.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. User Decides which setting diffculty he will like, easy normal or hard. 
2. Easy Gets 6 Attempts, Normal gets 8, Hard gets 5
3. User will then enter a guess number of 1( Secret number is 14)
4. Game returns too low! Go higher!
5. User enters 20 
6. Game returns too high! Go lower!
7. User enters 6 more attemps wrong and the game ends with no attempts left 
8. User clicks New Game. The secret number changes, but the game still says "Game over. Start a new game to try again." (the New Game bug isn't fixed yet)
9. User refreshes the page to start a fresh game, guesses the correct number, and the game ends with You won! The secret was 74. 

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

============================================================================ test session starts =============================================================================
platform darwin -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /Users/alanreyes/ai110-module1show-gameglitchinvestigator-starter
plugins: anyio-4.15.1
collected 4 items                                                                                                                                                            

tests/test_game_logic.py ....                                                                                                                                          [100%]

============================================================================= 4 passed in 0.01s ==============================================================================

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
