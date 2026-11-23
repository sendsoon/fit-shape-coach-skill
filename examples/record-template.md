# Record template

The person below is **fictional** and exists only to show the file shape. Do not copy these facts into a real file. In a real file, write only what the person confirmed, what a clinician confirmed, or what you advised, with a source label.

Write the real `profile.md`, `index.md`, and logs in English.

## Where files go

```text
fit-shape-records/
├── index.md
└── Kai/
    ├── index.md
    ├── profile.md
    └── logs/
        └── YYYY-MM-DD.md
```

The folder name is the nickname the person asked to be called. Do not add a chart number. Do not record a legal name, national ID, home address, phone number, marital status, or chest size. If the person types them, leave them out of the file. In conversation, use the nickname.

## Source labels

Use one of these on every health statement:

- Patient-reported
- Clinician-confirmed
- AI-generated assessment
- Unknown or unverified

## Registry `fit-shape-records/index.md`

```markdown
# Record index

| Nickname | Folder | Status | First record | Latest log |
|---|---|---|---|---|
| Kai | Kai/ | active | 2026-11-23 | 2026-11-23 |
```

## `Kai/index.md`

```markdown
# Kai

Fictional example. This is the name to use in conversation. There is no chart number.

## Latest status

- 2026-11-23: Completed a 20-minute brisk walk. No pain reported. Sleep window about 00:30–07:00. Source: patient-reported.
- Latest advice: keep sessions near 25 minutes; do not add a second workout to "make up" a miss. Source: AI-generated assessment.

## Important events

| Date | Event | Source |
|---|---|---|
| 2026-11-23 | Profile opened under the nickname Kai. | Patient-reported |
```

## `Kai/profile.md`

```markdown
---
nickname: Kai
first_record_date: 2026-11-23
status: active
---

# Kai

Fictional example. Calculate age from the stated age and `first_record_date` only as context. Do not invent a birthday. Address the person as Kai.

## 1. Basic profile

- Nickname: Kai
- Age: 34 years, stated on 2026-11-23. Source: patient-reported. Precision: year.
- Sex: not recorded. Declined.
- Height: 170 cm, stated once. Source: patient-reported. Do not ask again unless the person says a clinician remeasured it.
- Weight: not recorded. Optional. Do not schedule repeat weighs.
- Work or study: desk work, mostly seated. Source: patient-reported.
- Daily activity outside workouts: short walk to the station. Source: patient-reported.
- City: not recorded. Street address not recorded.

## 2. Training

- Experience: irregular walks, no regular strength work. Source: patient-reported.
- Recent frequency: about 2 days last week. Source: patient-reported.
- Session length they can use: 25 minutes. Source: patient-reported.
- Place and equipment: apartment, mat, no gym. Source: patient-reported.
- Preferences: walking, not running. Source: patient-reported.
- Past injuries: none stated. Asked and the answer was "no injury I know of." Source: patient-reported. Not the same as a medical clearance.

## 3. Meals and sleep

- Usual meals: coffee only at breakfast on workdays; canteen lunch; late dinner. Source: patient-reported.
- Preferences and budget: home cooking on weekends; no stated allergy. Source: patient-reported.
- Allergies or intolerances: not recorded.
- Sleep: about 00:30 to 07:00, weekends later. Night waking not recorded. Source: patient-reported.

## 4. Health limits

- Chronic disease: not recorded.
- Cardiovascular disease: not recorded.
- Clinician limits on exercise: not recorded.
- Joint, muscle, or bone problems: none stated. Source: patient-reported.
- Disability or mobility limit: none stated. Source: patient-reported.
- Post-surgical: not recorded.
- Special physiological stage: not recorded.
- Other: not recorded.

Do not add marital status or chest size to fill this section.

## 5. Aims

- More weekday energy and a repeatable 25-minute habit. Source: patient-reported.
- Not an appearance target. Do not rewrite this as a weight or shape goal.

## Profile changes

- 2026-11-23: File created. Source: AI-generated assessment of the interview.
```

## `Kai/logs/2026-11-23.md`

```markdown
# 2026-11-23

## 07:40 Session opened

- Asked for today's plan. Source: patient-reported.
- Yesterday: 20-minute brisk walk, completed, no pain. Source: patient-reported.

## Advice given

- Today: 3-minute easy walk, 15-minute brisk walk or march, 2 sets of 6–8 wall push-ups, 2-minute easy finish. Stop if chest pain or dizziness. Source: AI-generated assessment.
- Breakfast example offered: 40 g dry oats, 250 ml milk or unsweetened soy milk, one boiled egg. Source: AI-generated assessment. Not a weighed prescription.

## Not recorded

- Weight. Sex. Allergy testing. A clinician visit.
```

## Rules that are not optional

- An adult height is recorded once. A person who is still growing does not get a fixed adult height written as fact.
- Weight stays optional. Under 18, do not open a weight-change log.
- A missed session is a log line, not a punishment and not a double session the next day.
- If the write fails, tell the person nothing was saved.
