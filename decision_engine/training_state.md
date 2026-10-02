# Training State Engine V2.0

Version:

2.0


# 1. Purpose


This module determines the athlete's current training state and converts that state into practical training decisions.


The system must not assume that one training split, frequency, volume, intensity, or proximity-to-failure strategy works for every athlete.


Training recommendations must be determined by the interaction between:


- Training age
- Current performance
- Recent training load
- Bodyweight trend
- Nutrition
- Recovery
- Daily activity
- Fatigue
- Target muscle response
- Current bodybuilding phase
- Individual tolerance


Core Principle:


Training is a stimulus → recovery → adaptation system.


The goal is not to maximize training stress.


The goal is to maximize productive training stimulus that the athlete can recover from and progressively adapt to.


---

# 2. Connection With Decision Engine


This module receives information from:


decision_engine/state_assessment.md


and:


decision_engine/phase_selector.md


Required inputs:


- Current physical state
- Current bodybuilding phase
- Nutrition status
- Recovery status
- Activity status
- Main limiting factor
- Training history


The training state should never be determined independently from nutrition and recovery.


---

# 3. Core Training State Model


The system classifies the athlete into one or more dominant training states.


Primary states:


## Productive Training


## Productive Gaining


## Recomposition Training


## Energy-Limited Training


## Recovery-Limited Training


## Plateau / Adaptation-Limited Training


## Deload / Fatigue-Management State


These states are dynamic.


An athlete may transition between states depending on:

- Training load
- Nutrition
- Recovery
- Stress
- Activity
- Phase


---

# 4. Required Inputs


Before changing the training program, collect:


## Body Data


- Current bodyweight
- 7-day average bodyweight
- 14-day bodyweight trend
- 28-day bodyweight trend
- Waist measurement
- Visual body-composition trend
- Recent weight-change rate


---

## Training Performance


Collect:


- Load progression
- Repetition progression
- Completed sets
- Estimated RIR/RPE
- Exercise performance
- Technique stability
- Target-muscle stimulus
- Performance trend over multiple sessions


---

## Recovery


Collect:


- Sleep duration
- Sleep quality
- Subjective fatigue
- Muscle soreness
- Motivation
- Joint discomfort
- Stress


---

## Nutrition


Collect:


- Calories
- Protein
- Carbohydrates
- Fat
- Dietary consistency
- Appetite
- Hunger
- Recent calorie changes


---

## Activity


Collect:


- Daily steps
- Cardio
- Occupational activity
- Changes in normal activity


---

## Training Structure


Collect:


- Training split
- Frequency
- Weekly productive sets
- Exercise selection
- Session duration
- Rest intervals
- Proximity to failure
- Progression model


---

# 5. Training State Decision Sequence


All training decisions must follow:


Current Phase

↓

Training State Assessment

↓

Identify Limiting Factor

↓

Select Intervention

↓

Monitor Response

↓

Reassess


The system should not modify training variables before identifying the cause of the problem.


---

# 6. Productive Training State


## Definition


The athlete is recovering adequately and producing measurable training progress.


## Indicators


Possible signs:


- Performance stable or improving
- Repetitions increasing
- Load increasing
- Technique improving
- Target muscle stimulus strong
- Recovery acceptable
- Soreness manageable
- Sleep acceptable
- Motivation acceptable
- Bodyweight trend consistent with current phase


## Training Decision


Do not automatically increase volume.


First determine whether the current training stimulus is already producing adaptation.


If performance is improving and recovery is acceptable:


Maintain the current training structure unless a specific reason exists.


Possible progression methods:


- Increase repetitions
- Increase load
- Improve execution
- Improve range of motion
- Improve stability
- Add sets only when justified


---

# 7. Productive Gaining State


## Definition


The athlete is in a calorie-surplus or maintenance-to-surplus environment and experiencing productive hypertrophy adaptation.


## Indicators


Typical pattern:


- Bodyweight gradually increasing
- Waist relatively controlled
- Performance improving
- Recovery good
- Training quality high
- Target muscles responding


## Training Strategy


The objective is:


Maximum recoverable hypertrophy stimulus.


Not:


Maximum fatigue.


Maintain:


- Appropriate frequency
- Sufficient weekly volume
- High-quality execution
- Progressive overload
- Appropriate RIR
- Recovery capacity


Increase training volume only when:


- Performance stops progressing
- Recovery remains good
- Target muscle stimulus is insufficient
- Nutrition is adequate
- Adherence is high


Do not add volume simply because calories are increased.


---

# 8. Recomposition Training State


## Definition


The athlete is attempting to improve body composition while maintaining or gaining muscle.


## Indicators


Typical pattern:


- Bodyweight stable or slowly changing
- Waist stable or decreasing
- Performance stable or improving
- Visual physique improving
- Recovery acceptable


## Training Strategy


Primary objective:


Maintain or improve performance.


Do not reduce training intensity simply because calories are lower.


Prioritize:


- Important exercises
- High-quality working sets
- Appropriate RIR
- Fatigue management


Reduce unnecessary volume only when recovery deteriorates.


---

# 9. Energy-Limited Training State


## Definition


Training performance or recovery is negatively affected by insufficient energy availability.


## Possible Indicators


- Repeated performance decline
- Reduced repetitions at similar loads
- Reduced training quality
- Persistent fatigue
- Poor sleep
- Increased hunger
- Reduced motivation
- Bodyweight falling faster than intended


## Possible Causes


The system must determine whether the main cause is:


- Excessive calorie deficit
- Insufficient carbohydrate availability
- Excessive training volume
- Excessive training frequency
- Insufficient recovery
- Increased daily activity


## Training Strategy


The first objective:


Preserve training quality before increasing training quantity.


Intervention order:


1. Verify nutrition

↓

2. Verify carbohydrate availability

↓

3. Verify sleep

↓

4. Verify activity changes

↓

5. Reduce unnecessary fatigue

↓

6. Adjust training volume if necessary


Possible actions:


- Maintain important compound movements
- Reduce unnecessary accessory volume
- Increase RIR
- Avoid excessive failure training
- Reduce fatigue cost


Do not immediately add more training stimulus.


---

# 10. Recovery-Limited Training State


## Definition


The athlete has sufficient or apparently sufficient nutrition, but recovery cannot keep up with training stress.


## Possible Causes


- Excessive weekly volume
- Excessive session volume
- Excessive training frequency
- Excessive proximity to failure
- Poor exercise selection
- Excessive cardio
- Insufficient sleep
- Psychological stress
- Accumulated fatigue


## Indicators


- Repeated performance stagnation
- Performance decline
- Persistent soreness
- Joint irritation
- Declining motivation
- Poor session quality
- Reduced target-muscle connection
- Fatigue lasting across sessions


## Training Strategy


Reduce fatigue before adding stimulus.


Possible adjustments:


- Reduce sets
- Increase RIR
- Reduce failure training
- Remove redundant exercises
- Redistribute weekly volume
- Increase recovery days
- Temporarily reduce frequency
- Introduce deload when appropriate


The system should identify the smallest intervention that restores productive training.


---

# 11. Plateau / Adaptation-Limited Training State


## Definition


The athlete is not clearly fatigued, but measurable adaptation has slowed or stopped.


## Possible Pattern


- Performance flat
- Body composition flat
- Recovery acceptable
- Nutrition consistent
- Activity consistent
- Adherence high


## Before Changing Training Verify:


- Actual progression history
- Exercise execution
- Range of motion
- RIR accuracy
- Load recording
- Training consistency


Do not automatically:

- Add volume
- Add frequency
- Add intensity


The system must identify the true limiting factor first.


---

# 12. Deload / Fatigue Management State


## Definition


A temporary reduction in training stress is required to restore performance and recovery.


## Possible Indicators


- Accumulated fatigue
- Multiple performance declines
- Persistent soreness
- Reduced motivation
- Joint discomfort
- Poor training quality


## Possible Deload Strategies


Reduce:


- Sets
- Intensity
- Failure exposure
- Training frequency


Maintain:


- Exercise patterns
- Technical practice
- Movement quality


The purpose of deload is:

Restore future training productivity.


Not:

Stop training completely unless necessary.


---

# 13. Exercise Selection Engine


Exercise selection should consider:


- Target muscle
- Stable execution
- Range of motion
- Resistance profile
- Fatigue cost
- Joint comfort
- Progression potential
- Individual anatomy
- Training skill
- Equipment availability


The system must not classify:

Free weights

or

Machines


as universally superior.


The preferred exercise is:


The exercise that allows the athlete to produce a strong, repeatable stimulus with manageable fatigue and progressive overload.


---

# 14. Progression Engine


Progression is not limited to adding weight.


Possible progression variables:


- Increased repetitions
- Increased load
- Improved ROM
- Better execution quality
- Increased stability
- Better tempo/control
- Improved RIR performance
- Increased productive work


---

# 15. Double Progression Framework


Example:


Target:

8–12 repetitions


Process:


1.

Select manageable load.


↓

2.

Increase repetitions while maintaining technique.


↓

3.

When upper repetition range is achieved with appropriate RIR:


Increase load.


↓

4.

Return toward lower repetition range.


↓

5.

Repeat.


The exact progression model may differ according to:

- Exercise type
- Training experience
- Individual response


---

# 16. Training Frequency × Volume Interaction


Frequency must not be evaluated independently from volume.


Example:


High-frequency training:


18 weekly sets distributed across multiple sessions.


Low-frequency training:


Same 18 weekly sets performed in fewer sessions.


The key questions:


- Can the athlete recover?
- Does performance remain high?
- Is target-muscle stimulus maintained?
- Is progression occurring?
- Is the schedule sustainable?


Therefore:


Frequency is mainly a distribution variable.


Weekly productive work and recovery remain central.


---

# 17. Training × Nutrition Interaction


Training decisions must be interpreted together with nutrition.


## Calorie Surplus


Usually provides greater capacity for:


- Training volume
- Recovery
- Performance progression


However:


A surplus does not automatically justify increasing volume.


---

## Maintenance / Recomposition


Prioritize:


- Performance retention
- High-quality sets
- Recovery management
- Controlled fatigue


---

## Calorie Deficit


As deficit increases:


- Recovery capacity may decrease
- Training tolerance may decrease
- Performance maintenance becomes harder


Primary objective:


Preserve muscle and training quality while controlling fatigue.


---

# 18. Training × Activity Interaction


Daily activity must be considered.


Monitor:


- Steps
- Cardio
- Occupational activity
- Lifestyle changes


A sudden increase in activity can change energy availability.


Example:


Food intake unchanged

+

Steps increase substantially


May result in:


- Slower weight gain
- Faster weight loss
- Worse recovery
- Reduced performance


Activity changes must be included in decisions.
# 19. Muscle-Specific Volume Adjustment


The system must not assume every muscle requires identical training volume.


Each muscle should be evaluated individually.


Evaluation factors:


- Performance progression
- Target-muscle stimulus
- Recovery
- Soreness
- Visual development
- Technique quality
- Exercise selection
- Training frequency


Possible outcomes:


## Under-Stimulated


Indicators:


- No progression
- Weak target-muscle sensation
- Insufficient weekly work
- Recovery capacity available


Possible actions:


- Increase productive sets
- Improve exercise selection
- Increase frequency
- Improve execution


---

## Adequately Stimulated


Indicators:


- Performance improving
- Muscle development improving
- Recovery acceptable


Action:


Maintain current training dose.


---

## Over-Fatigued


Indicators:


- Performance declining
- Persistent soreness
- Poor recovery


Possible actions:


- Reduce sets
- Redistribute volume
- Reduce failure exposure
- Increase recovery


---

## Technically Limited


Indicators:


- Poor execution
- Incorrect stimulus distribution
- Compensatory movement patterns


Action:


Improve technique before increasing volume.


---

# 20. Weak-Point Development Engine


Weak points should be addressed through targeted training strategies.


The system should not solve every weakness by simply increasing total workload.


Possible interventions:


- Increase frequency
- Add targeted isolation work
- Improve exercise selection
- Improve ROM
- Improve execution
- Place priority exercise earlier
- Redistribute existing volume
- Reduce competing fatigue


Priority:


Redistribute resources before adding excessive volume.


---

# 21. High-Frequency Training Framework


High-frequency training can be effective when each session is controlled.


Requirements:


- Manageable per-session volume
- Controlled proximity to failure
- Stable exercise execution
- Adequate recovery
- Clear progression
- Fatigue monitoring


High frequency does NOT mean:


Training every muscle hard every day.


The key variable:


Total recoverable training stimulus.


---

# 22. State Transition Rules


Training state should be reassessed continuously.


## Productive → Recovery-Limited


Possible transition:


- Performance decline
- Fatigue accumulation
- Recovery deterioration


---

## Productive → Energy-Limited


Possible transition:


- Increasing calorie deficit
- Bodyweight dropping too quickly
- Performance decline


---

## Productive → Plateau


Possible transition:


- Performance stops progressing
- Recovery remains acceptable
- Adherence remains high


---

## Recomposition → Productive Gaining


Possible transition:


- Calories increase
- Bodyweight begins rising gradually
- Performance improves


---

## Recomposition → Energy-Limited


Possible transition:


- Deficit becomes excessive
- Performance declines
- Recovery worsens


---

## Recovery-Limited → Productive


Possible transition:


- Fatigue reduced
- Recovery restored
- Performance stabilizes


---

# 23. Minimum-Change Principle


When the athlete is progressing:


Change as little as necessary.


When the athlete is not progressing:


Change the smallest number of variables necessary to identify the limiting factor.


Avoid changing simultaneously:


- Calories
- Carbohydrates
- Training volume
- Frequency
- Exercise selection
- Cardio
- Steps


unless there is a clear reason.


Otherwise:

The system cannot determine which intervention caused the response.


---

# 24. Monitoring Windows


Do not judge a training intervention from one workout.


## Short-Term

Approximately:

3–7 days


Monitor:


- Session performance
- Recovery
- Soreness
- Sleep
- Motivation


---

## Medium-Term

Approximately:

7–14 days


Monitor:


- Performance trend
- Bodyweight trend
- Waist trend
- Recovery
- Training quality


---

## Long-Term

Approximately:

28 days


Monitor:


- Body composition trend
- Strength progression
- Hypertrophy indicators
- Fatigue
- Adherence
- Sustainability


---

# 25. Evidence Integration


Training decisions combine three evidence sources.


---

## Layer 1 — Scientific Evidence


Used to establish general principles:


Examples:


- Resistance-training volume
- Training frequency
- Proximity to failure
- Repetition ranges
- Rest intervals
- Hypertrophy mechanisms


---

## Layer 2 — Natural Athlete Case Evidence


Used as practical examples.


Possible sources:


- Documented natural athletes
- Competition preparation records
- Long-term training logs


Examples:


- Chengyi Tan
- Wang Zhenghao
- Kaisheng Wang
- Yuan Shilin


Used for:


- Training frequency
- Exercise selection
- Volume distribution
- Progression methods
- Recovery strategies
- Preparation structures


Important:


Athlete practice is not proof of causation.


---

## Layer 3 — Individual Response


The athlete's own longitudinal data has the highest priority for personalization.


The system must prioritize:


Actual response

over

theoretical expectation.


---

# 26. Natural Athlete Case Integration


When relevant, the system may reference:


athlete_database/


Example cases:


- Chengyi Tan
- Wang Zhenghao
- Kaisheng Wang
- Yuan Shilin


The system may compare:


- Training frequency
- Exercise selection
- Weekly volume
- Progression style
- Recovery management
- Nutrition interaction
- Competition preparation


Rules:


Natural athlete cases:

Provide practical patterns.


They do NOT:


- Replace scientific evidence
- Become universal prescriptions
- Override individual response


---

# 27. Training State Confidence


Every assessment must include confidence.


## High Confidence


Multiple indicators agree.


Example:


Performance increasing

+

Recovery good

+

Stable bodyweight trend


---

## Moderate Confidence


Some indicators support the conclusion.

More monitoring required.


---

## Low Confidence


Insufficient information.


Avoid major training changes.


---

# 28. Final Training State Output Format


## A. Current Training State


State:


Confidence:


Evidence:


---

## B. Current Phase Interaction


Bodybuilding phase:


Nutrition condition:


Recovery condition:


---

## C. Main Limiting Factor


Current limitation:


Supporting evidence:


---

## D. Training Decision


Training frequency:


Weekly volume:


Exercise selection:


Sets per exercise:


Repetitions:


RIR/RPE:


Rest intervals:


Progression method:


---

## E. Fatigue Management


Need adjustment:


YES / NO


If yes:


Adjustment:


---

## F. Monitoring Plan


Monitor:


- Performance
- Bodyweight trend
- Recovery
- Sleep
- Fatigue
- Adherence


Reassessment:


7–14 days


or


28 days for long-term evaluation.


---

# 29. Final System Principle


The purpose of Training State Engine is not to maximize training difficulty.


The purpose is:


Identify the current training state

↓

Find the limiting factor

↓

Apply the smallest effective adjustment

↓

Restore productive adaptation

The best program is not the hardest program.


The best program is the program that produces continuous adaptation while remaining recoverable.
