# Lemon Clicker Bug Report

**Name:**
**Tickets solved:** <!-- e.g. 1, 2, 3, 5, 6 (at least five) -->

Copy the template below once for each ticket you solved. 

---

## Ticket <number>: <ticket title>

### Actual cause

<!-- Which file and function was the bug in, and what was wrong with the code?
     Explain why that code produced the behavior described in the ticket. -->

**File / function:**

**What was wrong:**

### Fix

<!-- What did you change, and why does that change fix the problem? -->

### How did you find it?

#### Hypothesis testing

**What hypothesis ultimately led you to identify the buggy code, and why?**

#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** <!-- what you saw, e.g. text on screen, console error -->
2. **Traced back to:** <!-- where that came from, e.g. a function, a request in the Network tab, a server log -->
3. **Traced back to:**
4. **Buggy code:** <!-- the file, function and line where the trace ended -->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- How did you confirm the problem is gone? -->



**LEMON RANDOMNESS FIX:**
**Tickets solved:1** 

---

## Ticket <3>: <The lemon only lands in four spots>

### Actual cause

<!-- The math.round() call encompassing the math.random() call that randomizes the lemon's next coordinates constraints
the lemon's  positions to the very corners of the ubffer area.' -->

**File / function: GameScreenView.ts**

**What was wrong: lemon only appeared in the corners in a semi-predictable pattern, which is supposed to be random**

### Fix

<!-- I remove the math.round() call completely, which removed the constraints on the lemon's position.' -->

### How did you find it? I looked into the part where the lemon's position was updated and tinkered with the random positioning math'

#### Hypothesis testing

**I noticed that the math.round() operation didn't seem necessary. To test this, I removed it.'**

#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** <!-- png of the lemon kept appearing at the corners of the screen -->
2. **Traced back to:** <!-- lemon random position generation function: randomizeLemonPosition(): void  -->
3. **Traced back to:**
4. **Buggy code:** <!-- GameScreenView.ts -->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- I replayed the game and paid attention to how the lemon updated the position, which seems to be random now as intended -->


**DATA FETCH ISSUE RESOLVED:**
**Tickets solved:1** 

---

## Ticket <1>: <Stats always say "Stats unavailable">

### Actual cause

<!-- const response = await fetch("/api/stats"); had /stat instead of /stats, causing an erronous fetch' -->

**File / function: MainMenuScreenController.ts**

**What was wrong: called fetch to wrong destination as a typo**

### Fix

<!-- Changed stat to stats.' -->

### I tinkered with the parts of the code responsible to fetching data and found that the catch error matched that of the fetch if something went wrong. I then checked index.ts to see what the server was expecting, which was app.get("/api/stats", (_req, res) => {. It is denoted as stats instead of stat for the correct call.'

#### Hypothesis testing

**I noticed that server was expecting stats instead of stats. To make sure that this inconsistency wasn't responsible for the issue, I made them the same'**

#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** <!-- catch error of unable to load stats -->
2. **Traced back to:** <!-- app.get("/api/stats", (_req, res) => {   -->
3. **Traced back to:** [text](../src/screens/MenuScreen/MenuScreenController.ts)
4. **Buggy code:** <!-- MenuScreenController.ts -->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- I replayed the game and paid attention to how the text under the play button to see if it there is no catch error. There was not. -->




**DATA FETCH ISSUE RESOLVED:**
**Tickets solved 1** 

---

## Ticket <2>: <Stats showed best as 0">

### Actual cause

<!-- const response = await fetch("/api/stats"); had /stat instead of /stats, causing an erronous fetch' -->

**File / function: Index.ts**

**What was wrong: wrong check for best score**

### Fix

<!-- Changed stat to stats.' -->

### Now with knowing index.ts handles the logic behind what gets stored, I went down the if checks for what gets stored.'

#### Hypothesis testing

**I noticed that only when the current score was lower than the high score would it be stored as a high score. This kept the best score at 0. This instead was saving the lowest score'**

#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** <!-- the best score remained 0 -->
2. **Traced back to:** f (entries[i].score <> best) {
3. **Traced back to:** [
4. **Buggy code:** <!-- index.ts -->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- I replayed the game with a fresh server and refreshed the game and saw that the highest score was no longer 0 and was saved as intended. -->



 Lemon Clicker Bug Report

**Name:**
**Tickets solved:** <!-- e.g. 1, 2, 3, 5, 6 (at least five) -->

Copy the template below once for each ticket you solved. 






---

## Ticket <4>: <Stuck on the Game Over screen>

### Actual cause : game timer kept going even when reached end game screen

<!-- Which file and function was the bug in, and what was wrong with the code?
     Explain why that code produced the behavior described in the ticket. -->

**File / function: private endGame(): void {**

**What was wrong: the function that ended the timer was called incorrectly as typo**

### Fix

<!-- changed this.stopTimer to this.stopTimer() -->

### How did you find it? I looked through the factors that were required for the game to recognize that the game had ended. The first place to search was endGame(). Everything else had () in the calls.

#### Hypothesis testing

**What hypothesis ultimately led you to identify the buggy code, and why? : My hypothesis was that the endGame() function had something wrong as that was the function that was called to end the game. All the other this.functionName() calls had the parenthesis. My hypothesis was that the stopTimer() required the () to function properly**

#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** <!-- repeated refreshing of the game over screen and a nearly nonfunctional  -->
2. **Traced back to:** <!-- GameScreenController.ts -->
3. **Traced back to:** line 87
4. **Buggy code:** <!-- private endGame(): void {
		this.stopTimer();

		// Switch to results screen with final score
		this.screenSwitcher.switchToScreen({
			type: "result",
			score: this.model.getScore(),
		});
	} -->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- Replayed the game and took my sweet time clicking the restart button, which confirmed the button was reponsive. I was brought back to the next game as intended. -->






# Lemon Clicker Bug Report

**Name: TICKET 5 fix: Leaderboard dates show "undefined"**
**Tickets solved: 1** <!-- e.g. 1, 2, 3, 5, 6 (at least five) -->

Copy the template below once for each ticket you solved. 

---

## Ticket <number>: <Leaderboard dates show "undefined"e>

### Actual cause

<!-- Which file and function was the bug in, and what was wrong with the code?
     Explain why that code produced the behavior described in the ticket. -->

**File / function: index.ts, ResultsScreenController.ts, RestultsScreenModel.ts, ResultsScreenView.ts**

**What was wrong: stored and searched for save data using 2 different tags, one was time and the other was timestamp**

### Fix

<!-- I simply ctrl+f and replaced everything with time. This keeps things standardized -->

### How did you find it? I looked at the saved data, which was fine, but noticed that the time data was stored as "time", but was called elsewhere and defined with "timestamp"

#### Hypothesis testing

**What hypothesis ultimately led you to identify the buggy code, and why?
My hypothesis initially was the data was simply not being correctly pulled. I checked this by pulling up the actual data saved about found that the data was fine. The tags were fine. My next hypothesis was that there was probably a typo error somewhere and found timestamp, which didn't match any of the saved data's tags.**

#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** <!-- saw UNDEFINED in the leaderboard stats for all of the data entries -->
2. **Traced back to:** <!-- all the files that had access to the data store -->
3. **Traced back to: anywhere that was able to access or call the datastore's data of time**
4. **Buggy code:** <!-- ^ -->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- I restarted the server and played a round. I saw that the data was now being shown correctly without UNDEFINED, which is intended behavior. -->
