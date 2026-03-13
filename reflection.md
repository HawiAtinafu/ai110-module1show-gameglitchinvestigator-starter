# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

--- The first time i played it the hint was wrong, it told me to keep guessing higher eve when i put in numbers greater than 100 when the secret was 19. I expected the hnt to be accurate and tell me to guess lower and maybe have an error message when guessing numbers out of range.

--- when starting a new game it wouldnt remove the number in the guess box from previous guess. Previsous guess do not get remove in any case unless you manually delete them. I expected the numbers to be removed every new guess,

--- The new game button doesnt start a new game, i had to refresh the page manually for it to work. I expected the button to start a new game without me having to refresh the page.

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---I used claude to help me understand the underlysing issue i discovered. When describing ths issues and asked the agent to locate where the bug could be coming form and why, the agent did a good job in finding the logic flaws and bugs in the codes. Then i went in one by one and looked at the suggestions the agent had to fix them, afer implementing the suggested chnages and adding comments to show where we made changes. I verified the changes were woking by going back to the games and playing the scenarios i found the bugs with and also made sure that the test were passing and we didnt break anything else.

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

--- I decided a bug was fixed by manually testing the app in scenarios that previously triggered the issue, like guessing numbers way out of range to check hints, starting new games to verify input clearing and state reset, and ensuring the game felt smooth without needing page refreshes. For automated testing, I ran pytest on the test_game_logic.py file, which passed all three tests and confirmed that the check_guess function now returns correct outcomes like "Too High" with "Go LOWER!" instead of the wrong messages. The AI (Claude) helped me understand the existing tests by explaining how they worked and why they failed initially, but I updated the test assertions myself to match the fixed function's tuple returns, verifying the changes didn't break anything.

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

--- Imagine Streamlit as a magical script that rewinds and replays every time you do something, like clicking a button or typing in a box—it's called a "rerun," and the whole app restarts from the beginning. But to remember things between these rewinds, like your secret number or how many guesses you've made, we use "session state," which is like a sticky note that keeps data alive across reruns so your game doesn't forget everything. Without session state, every button click would reset the game, but with it, the app feels continuous and interactive, even though it's really just rerunning the script over and over.

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

--- One habit I want to reuse is running pytest after every major change to catch regressions early, as it quickly confirmed our fixes didn't break existing logic and gave confidence in the code's reliability. Next time with AI, I'd implement and test smaller changes one at a time instead of batching them, to better isolate what works versus what needs tweaking. This project showed me that AI-generated code can be a great starting point but often contains subtle bugs that require careful debugging and verification, making me more cautious and appreciative of thorough testing.
