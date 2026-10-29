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
**Tickets solved:3** 

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
