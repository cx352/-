# Phase Selector Engine

## 1. Purpose

This module determines what the athlete should do NEXT based on current data.

The system must not assume that every athlete should immediately bulk.

The decision sequence is:

> Assess current state → identify limiting factor → select phase → select strategy → monitor → reassess.

The goal is to maximize long-term muscle gain while controlling unnecessary fat gain.

---

# 2. Required Inputs

The system should request the following information when available:

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

## Nutrition

- Current calories
- Protein
- Carbohydrates
- Fat
- Current food intake
- Recent calorie changes
- Dietary adherence

## Training

- Training frequency
- Training split
- Weekly sets
- RIR/RPE
- Main exercise performance
- Recent strength trend
- Training quality

## Recovery

- Sleep duration
- Sleep quality
- Fatigue
- Muscle soreness
- Joint discomfort
- Stress
- Motivation

## Activity

- Average steps
- Cardio
- Recent activity changes

---

# 3. First Decision: Is the Athlete in Post-Contest Recovery?

If the athlete recently completed a bodybuilding contest, first determine whether they are still in post-contest recovery.

Relevant indicators:

- recent competition
- very low competition bodyweight
- recent severe calorie restriction
- rapid increase in food intake
- rapid increase in bodyweight
- large carbohydrate increase
- glycogen restoration
- increased water retention
- unusually high hunger
- rapid performance improvement

If several indicators are present:

> classify as POST-CONTEST RECOVERY.

Do not automatically interpret rapid weight gain as fat gain.

---

# 4. Second Decision: Is Fat Loss Currently the Priority?

Consider FAT-LOSS when:

- body fat is relatively high for the athlete's goals
- waist is increasing significantly
- the athlete wants to reduce body fat
- bodyweight is intentionally decreasing
- current body composition makes further gaining undesirable

Primary strategy:

> controlled calorie deficit while preserving training performance and lean mass.

---

# 5. Third Decision: Is Recomposition Appropriate?

Consider RECOMPOSITION when:

- bodyweight is stable or slowly decreasing
- waist is stable or decreasing
- training performance is stable or improving
- body fat is not extremely low
- the athlete recently completed a diet
- the athlete is returning from a contest
- muscle gain and fat loss can reasonably occur simultaneously

Possible nutrition strategies:

- maintenance calories
- small calorie deficit
- very small surplus

Do not force weight gain when the athlete is already improving in:

- strength
- muscular appearance
- waist measurement
- recovery

---

# 6. Fourth Decision: Is the Athlete Ready for Muscle Gain?

Consider MUSCLE-GAIN when:

- body fat is acceptable
- recovery is good
- training performance is progressing
- waist is reasonably controlled
- the athlete has no immediate need for further fat loss

Then determine the appropriate rate of gain.

---

# 7. Muscle-Gain Strategy Selection

Use three primary gaining strategies.

## A. Conservative Gain

Use when:

- athlete wants to minimize fat gain
- body fat is moderate
- athlete is relatively experienced
- training performance is already good

Initial strategy:

> maintenance to approximately +100–200 kcal/day.

Target rate:

> approximately 0.10–0.25% bodyweight/week.

This is a starting range rather than a rigid rule.

---

## B. Standard Gain

Use when:

- athlete is relatively lean
- recovery is good
- training performance needs additional support
- some fat gain is acceptable

Initial strategy:

> modest calorie surplus.

Avoid unnecessarily large surpluses.

---

## C. Higher-Calorie Gain

Use only when justified.

Possible reasons:

- persistent weight loss
- high activity
- inadequate recovery
- persistent performance decline
- insufficient food intake
- genuinely low energy availability

Before increasing calories substantially, verify:

- tracking accuracy
- adherence
- activity
- training load
- sleep

---

# 8. Weight Trend Decision Tree

## Scenario 1

Weight ↓

Waist ↓

Performance ↑ or stable

Interpretation:

> Fat loss or recomposition may be occurring successfully.

Action:

> Do not automatically increase calories.

---

## Scenario 2

Weight →

Waist ↓

Performance ↑

Interpretation:

> Strong recomposition signal.

Action:

> Maintain current strategy.

---

## Scenario 3

Weight ↑ slowly

Waist stable/minimally ↑

Performance ↑

Interpretation:

> Compatible with productive muscle gain.

Action:

> Maintain current intake.

---

## Scenario 4

Weight ↑ rapidly

Waist ↑ rapidly

Performance does not improve proportionally

Interpretation:

> Possible excessive calorie surplus.

Action:

> Reduce calories slightly, usually through carbohydrate or fat adjustment.

---

## Scenario 5

Weight ↓

Waist ↓

Performance ↓

Recovery ↓

Interpretation:

> Possible excessive deficit or insufficient recovery.

Action:

> Increase energy availability and/or reduce training stress.

---

## Scenario 6

Weight →

Waist →

Performance →

Recovery good

Interpretation:

> Maintenance or plateau.

Action:

Investigate:

1. Training progression
2. Volume
3. Exercise selection
4. Sleep
5. Nutrition
6. Activity

Do not automatically add calories.

---

# 9. Carbohydrate Adjustment Engine

Carbohydrates should be adjusted primarily according to:

- bodyweight trend
- training performance
- recovery
- activity
- total calorie intake

## Increase carbohydrates when:

- bodyweight is falling unintentionally
- training performance is declining
- recovery is worsening
- activity is high
- hunger is high
- the athlete is otherwise adherent

Typical adjustment:

> +20–40 g carbohydrate/day.

Then monitor for 7–14 days.

---

## Maintain carbohydrates when:

- bodyweight trend is appropriate
- performance is improving
- waist is controlled
- recovery is good

---

## Reduce carbohydrates when:

- bodyweight rises substantially faster than planned
- waist increases rapidly
- performance does not justify the weight gain

Typical adjustment:

> -20–40 g carbohydrate/day.

Then monitor again.

---

# 10. Do Not Make Multiple Large Changes

When the athlete is stable:

Change only one major variable at a time.

Examples:

- calories
- carbohydrate
- fat
- training volume
- cardio
- steps

Avoid changing everything simultaneously.

This allows the system to identify what caused the response.

---

# 11. Adjustment Frequency

Do not react to single-day changes.

Preferred monitoring:

### 7 days

Useful for detecting short-term trends.

### 14 days

Preferred interval for most nutritional adjustments.

### 28 days

Useful for confirming long-term trends.

Major changes should generally require multiple indicator
