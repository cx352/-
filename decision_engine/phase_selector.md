# Phase Selector Engine V2.0

Version:

2.0


# 1. Purpose


This module determines what the athlete should do NEXT based on current data.


The system must not assume that every athlete should immediately bulk.


The decision sequence is:


Assess current state

↓

Identify limiting factor

↓

Select phase

↓

Select strategy

↓

Monitor

↓

Reassess


The goal:

Maximize long-term muscle gain while controlling unnecessary fat gain.


Core principle:


The athlete's current physiological state determines the phase.

Not the athlete's desired label.


---

# 2. Connection With State Assessment Engine


This module receives information from:


decision_engine/state_assessment.md


Required inputs:


- Current physical state
- Body composition trend
- Nutritional state
- Training state
- Recovery state
- Activity state
- Main limiting factor
- Confidence level


Phase selection should not operate independently from state assessment.


---

# 3. Required Inputs


The system should request the following information when available.


## Body


- Age
- Sex
- Height
- Current bodyweight
- 7-day average bodyweight
- 14-day average bodyweight
- 28-day average bodyweight
- Waist circumference
- Estimated body-fat percentage
- Progress photos
- Recent competition date
- Competition bodyweight


---

## Nutrition


- Current calories
- Protein
- Carbohydrates
- Fat
- Food intake consistency
- Recent calorie changes
- Dietary adherence


---

## Training


- Training frequency
- Training split
- Weekly sets
- RIR/RPE
- Main exercise performance
- Strength trend
- Training quality


---

## Recovery


- Sleep duration
- Sleep quality
- Fatigue
- Muscle soreness
- Joint discomfort
- Stress
- Motivation


---

## Activity


- Average steps
- Cardio
- Recent activity changes


---

# 4. Phase Selection Priority


When multiple phases appear possible:


Use the following priority:


1. Post-contest recovery


↓

2. Recovery limitation


↓

3. Fat-loss requirement


↓

4. Recomposition opportunity


↓

5. Muscle gain


The system should solve urgent physiological problems before optimizing long-term goals.


---

# 5. First Decision: Post-Contest Recovery


Determine whether the athlete is still recovering from competition.


Indicators:


- Recent bodybuilding competition
- Very low competition bodyweight
- Severe calorie restriction
- Rapid increase in food intake
- Rapid bodyweight rebound
- Large carbohydrate increase
- Glycogen restoration
- Increased water retention
- High hunger
- Rapid improvement in performance


If several indicators exist:


Classify as:


POST-CONTEST RECOVERY


Important:


Do not automatically interpret rapid weight gain as fat gain.


Consider:


- Glycogen restoration
- Water restoration
- Sodium changes
- Gastrointestinal content


Primary objective:


Establish stable physiological baseline.


---

# 6. Recovery Limitation Phase


Before selecting gaining or cutting phases:


Check whether recovery is the primary limitation.


Indicators:


- Persistent fatigue
- Performance decline
- Poor sleep
- High soreness
- Joint discomfort
- Low motivation


Possible strategy:


- Reduce training stress
- Improve recovery
- Adjust nutrition if required


Do not immediately increase calories or training volume.


---

# 7. Fat-Loss Phase


Consider FAT-LOSS when:


- Body fat is relatively high for the athlete's goal
- Waist is increasing significantly
- Fat reduction is the priority
- Bodyweight is intentionally decreasing
- Current body composition makes gaining inappropriate


Primary strategy:


Controlled calorie deficit while preserving:


- Lean mass
- Strength
- Training quality


Monitor:


- Weight loss rate
- Waist reduction
- Strength retention
- Recovery
- Hunger


---

# 8. Recomposition Phase


Consider RECOMPOSITION when:


- Bodyweight is stable or slowly decreasing
- Waist is stable or decreasing
- Training performance is improving
- Body fat is not extremely low
- Athlete recently completed dieting
- Muscle gain and fat loss may occur simultaneously


Possible nutrition strategies:


- Maintenance calories
- Small deficit
- Very small surplus


Do not force weight gain when improvement is already occurring in:


- Strength
- Muscular appearance
- Waist measurement
- Recovery


---

# 9. Muscle-Gain Phase Selection


Consider MUSCLE-GAIN when:


- Body fat is acceptable
- Recovery is good
- Training performance is progressing
- Waist is controlled
- No immediate fat-loss requirement exists


Then select gaining speed.


---

# 10. Muscle-Gain Strategy Selection


## A. Conservative Gain


Use when:


- Athlete wants minimal fat gain
- Body fat moderate
- Athlete experienced
- Performance already good


Initial strategy:


Maintenance to approximately:

+100–200 kcal/day


Target:


0.10–0.25% bodyweight/week


This is a starting framework.

Not a universal rule.


---

## B. Standard Gain


Use when:


- Athlete relatively lean
- Recovery good
- Performance requires more energy
- Some fat gain acceptable


Strategy:


Moderate calorie surplus.


Avoid unnecessary large surpluses.


---

## C. Higher-Calorie Gain


Use only when justified.


Possible reasons:


- Persistent weight loss
- High activity
- Poor recovery due to low energy availability
- Insufficient food intake


Before increasing calories substantially:


Verify:


- Tracking accuracy
- Adherence
- Activity
- Training load
- Sleep


---

# 11. Weight Trend Decision Tree


## Scenario 1


Weight ↓

Waist ↓

Performance ↑ or stable


Interpretation:


Fat loss or recomposition may be occurring.


Action:


Do not automatically increase calories.


---

## Scenario 2


Weight →

Waist ↓

Performance ↑


Interpretation:


Strong recomposition signal.


Action:


Maintain strategy.


---

## Scenario 3


Weight ↑ slowly

Waist stable/minimal increase

Performance ↑


Interpretation:


Compatible with productive muscle gain.


Action:


Maintain current intake.


---

## Scenario 4


Weight ↑ rapidly

Waist ↑ rapidly

Performance does not improve proportionally


Interpretation:


Possible excessive surplus.


Action:


Reduce calories slightly.


---

## Scenario 5


Weight ↓

Waist ↓

Performance ↓

Recovery ↓


Interpretation:


Possible excessive deficit.


Action:


Increase energy availability and/or reduce training stress.


---

## Scenario 6


Weight →

Waist →

Performance →

Recovery good


Interpretation:


Maintenance or possible plateau.


Investigate:


- Training progression
- Volume
- Exercise selection
- Sleep
- Nutrition
- Activity


Do not automatically add calories.


---

# 12. Carbohydrate Adjustment Engine


Carbohydrates should be adjusted according to:


- Bodyweight trend
- Performance
- Recovery
- Activity
- Total calorie intake


Increase carbohydrates when:


- Weight falling unintentionally
- Performance declining
- Recovery worsening
- Activity high
- Hunger high


Typical adjustment:


+20–40g carbohydrate/day


Monitor:

7–14 days


---

Maintain carbohydrates when:


- Weight trend appropriate
- Performance improving
- Waist controlled
- Recovery good


---

Reduce carbohydrates when:


- Weight increasing faster than planned
- Waist increasing rapidly
- Performance does not justify gain


Typical adjustment:


-20–40g carbohydrate/day


---

# 13. Adjustment Rules


Do not make multiple large changes simultaneously.


Change one major variable:


Examples:


- Calories
- Carbohydrates
- Fat
- Training volume
- Cardio
- Steps


Then monitor response.


---

# 14. Monitoring Period


Preferred:


7 days:

Short-term trend


14 days:

Normal adjustment period


28 days:

Long-term confirmation


Do not react to single-day fluctuations.


---

# 15. Athlete Database Reference


The system may compare phase decisions with:


athletes/


Including:


- Natural athlete cases
- Competition preparation records
- Long-term physique development


However:


Athlete examples are references only.


They cannot override:


- Scientific evidence
- Individual response
- Actual user data


---

# 16. Phase Confidence System


Every decision must include confidence.


## High Confidence


Multiple consistent indicators.


## Moderate Confidence


Some indicators support the decision.

More monitoring required.


## Low Confidence


Insufficient information.

Avoid aggressive changes.


---

# 17. Phase Selector Output Format


## Selected Phase


Current phase:


---

## Evidence


Bodyweight evidence:


Body composition evidence:


Nutrition evidence:


Training evidence:


Recovery evidence:


---

## Main Reason


Why this phase was selected:


---

## Main Limiting Factor


Current limitation:


---

## Confidence


High / Moderate / Low


---

## Next Module


Continue to:


- bulking.md

- cutting_engine.md

- contest_prep.md

- recovery.md


---

## Monitoring Plan


Reassess after:


7–14 days

or

28 days for long-term confirmation.


---

# Final Principle


The system does not choose the phase based on the athlete's wish.


It chooses the phase based on:


Current state

+

Evidence

+

Individual response.


Assess first.

Select phase second.

Adjust strategy third.
