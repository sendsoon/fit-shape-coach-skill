# fit-shape-coach-skill

**English** | [简体中文](README.zh-CN.md)

Agent skill for long-term, practical coaching of movement, meals, sleep, and habits. It fits the plan to age, health limits, time, and feedback.

```text
Use this skill when the person asks what to train, what to eat, how to sleep, or how to keep a health habit going.
```

This skill does **not** diagnose, prescribe, or replace a clinician, and it does **not** treat body shape as a measure of worth.

```bash
npx skills add sendsoon/fit-shape-coach-skill
```

## What this skill does

`fit-shape-coach-skill` is a workflow for coding agents (Cursor, Claude Code, Codex, and others that load `SKILL.md`). When a person describes a real situation, the agent:

1. Matches one nickname, or asks before mixing two people
2. Reads that person's local profile, index, and latest log
3. Checks for emergency symptoms before giving ordinary advice
4. Separates guideline recommendations, established knowledge, a personal suggestion, and unknown facts
5. Gives a step with a food, a portion, a minute, or a movement
6. Asks one missing question instead of a long form
7. After confirmation, updates the English record and appends a log without deleting history

For anyone under 18, the skill does not set a weight-loss goal or an energy deficit.

## Records

Records live in `fit-shape-records/<nickname>/` in the **current workspace**. The folder name is the nickname the person chose. Profiles and logs are English. Each fact is marked patient-reported, clinician-confirmed, AI-generated assessment, or unknown or unverified.

The folder is gitignored except for this directory's README. The repository does not contain a real history. The fictional shape is [examples/record-template.md](examples/record-template.md).

Do not store a legal name, national ID number, street address, phone number, marital status, or chest size.

## When to use it

Use it for a training week, a single session, meals, snacks, convenience food, eating out, sleep, recovery, and adjusting the plan after a miss or a new limit.

Do not use it to rehabilitate an undiagnosed injury, to promise a body change, to put a child on a weight-loss plan, or to delay emergency care. In mainland China the public medical emergency number is 120. Elsewhere, use the local emergency number.

## Install

```bash
npx skills add sendsoon/fit-shape-coach-skill
```

Or clone the repository and copy `SKILL.md`, `references/`, and `examples/` into your agent's skills directory. Keep those relative paths.

The [skills.sh](https://skills.sh/) catalog page updates after install telemetry arrives.

## Update the skill

If you installed with the Skills CLI, pull the latest `SKILL.md` from GitHub:

```bash
npx skills check
npx skills update fit-shape-coach-skill
```

`check` only reports whether a newer hash exists. `update` reinstalls this skill into the same agents as before. To refresh every installed skill:

```bash
npx skills update
```

Skip the confirm prompt with `-y`:

```bash
npx skills update fit-shape-coach-skill -y
```

Re-running the install command also refreshes the files:

```bash
npx skills add sendsoon/fit-shape-coach-skill
```

If you copied files by hand, `git pull` this repository and copy `SKILL.md`, `references/`, and `examples/` over the previous copy.

## Usage

```text
I can train 25 minutes at home after work. I usually sleep at 00:30. What should today look like?
I skipped yesterday. Do I double today's session?
My knee hurts on stairs. Can you give me a rehab plan?
```

If a fact that changes safety is missing, the agent asks one question. It does not guess an injury diagnosis.

## Output

Emergency symptoms: the reply is the emergency step.

A simple question: a short answer, not all five sections.

A day plan, in Chinese:

1. 今日健康状态
2. 今日饮食建议
3. 今日运动建议
4. 今日睡眠建议
5. 今日心理建设

A fictional example is in [examples/output-template.md](examples/output-template.md).

## Project layout

```text
fit-shape-coach-skill/
├── SKILL.md
├── skills.sh.json
├── skills-lock.json
├── README.md
├── README.zh-CN.md
├── LICENSE
├── references/
│   ├── activity-guidelines.md
│   ├── nutrition.md
│   ├── sleep-and-mind.md
│   ├── special-situations.md
│   ├── emergency-warning.md
│   └── follow-up.md
├── examples/
│   ├── output-template.md
│   └── record-template.md
└── fit-shape-records/        # local, gitignored except README.md
```

| File | Role |
|---|---|
| `SKILL.md` | What the agent executes. YAML `name` / `description` control discovery. |
| `references/` | Activity, meals, sleep, special situations, emergencies, and reviews. Open only the file the question needs. |
| `examples/` | Reply shape and a fictional record. Not real people. |
| `fit-shape-records/` | One folder per nickname. |
| `skills.sh.json` | Grouping label for a skills.sh repo page, if this repository is published. It does not change coaching behavior. |
| `skills-lock.json` | Local lock. No upstream hash, because this copy is not a published release. |

## Sources

Reference files cite the WHO 2020 physical activity guideline, the WHO healthy-diet fact sheet and 2012 sodium guideline, the 2022 Chinese dietary guidelines, the AASM/SRS adult sleep consensus (2015), the AASM pediatric sleep consensus (2016), CDC talk-test intensity, and ACOG Committee Opinion 804 for activity in pregnancy. They were checked on 2026-11-23. They are not a substitute for the current official text, and they do not cite papers that were not identified.

## License

[MIT](LICENSE)
