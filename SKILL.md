---
name: character-background-generator
description: Use when creating fictional character backgrounds from sparse user prompts. Generates culturally plausible demographics, names, family history, personality, sexuality, politics, social IDs, account style, motto, legal-risk attitude, contradictions, voice, and uniqueness checks while remaining platform-agnostic for any agent and avoiding impersonation or usable real-world identity data.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [creative-writing, character-design, worldbuilding, fiction, roleplay]
    related_skills: [humanizer]
---

# Character Background Generator

## Overview

This skill turns sparse character requirements into a complete fictional character profile. The output must feel like a real person shaped by culture, class, family, language, internet habits, politics, sexuality, moral boundaries, and contradictions — not a random table of labels.

The goal is not maximum detail for its own sake. The goal is a character that remains recognizable even if the name is removed.

This skill is **agent-agnostic**. It must not assume a specific runtime, coding agent, provider, platform, CLI, tool name, or application such as Codex, Claude Code, OpenCode, Hermes-only tools, or any other execution environment. Any capable agent should be able to follow the process using plain reasoning and the user's supplied context.

## When to Use

Use this skill when the user asks for:

- Original character creation
- Fictional biography or role background
- TRPG / novel / screenplay / game NPC design
- Social-media-style fictional identity for storytelling
- A culturally plausible name and life profile
- A character with politics, sexuality, family history, online IDs, and moral boundaries
- A reusable Markdown character sheet

Do not use this skill to impersonate real people, generate fraud identities, create usable credentials, or produce operational advice for illegal activity.

## Platform-Agnostic Requirements

The skill must be usable by any agent. Follow these rules:

1. **Do not reference a specific agent platform.** Avoid instructions like “use Codex,” “call Hermes tools,” “run this CLI,” or “open this app.”
2. **Do not depend on tool availability.** If facts must be researched, say that the agent should verify with reliable sources; do not require a named search tool.
3. **Use plain Markdown output.** The final artifact should be readable in any editor, wiki, note app, or version-control system.
4. **Keep procedures conceptual and portable.** Describe what to check, not which proprietary command to run.
5. **Avoid hidden environment assumptions.** Do not assume file paths, OS, API keys, user profile, or a local skill manager.
6. **No platform-specific formatting.** Use standard Markdown only.

Completion criterion: another agent with no Hermes/Codex-specific context can still produce the same type of character profile from this skill.

## Required Inputs

If the user provides only a short prompt, infer missing values and label them as assumptions. Prefer acting over asking unless the missing detail would fundamentally change the result.

Extract or infer:

- Character purpose
- Country / culture
- Age range
- Gender or gender presentation
- Story genre
- One-sentence concept
- Occupation or social role
- Social class
- Required traits
- Forbidden traits
- Sensitive boundaries

### Minimal Input Template

```markdown
- Character purpose:
- Country or cultural background:
- Age range:
- Gender or gender presentation:
- Story genre:
- One-sentence concept:
```

### Full Input Template

```markdown
## Character Generation Request

- Purpose: novel / screenplay / TRPG / game NPC / fictional social profile / other
- Setting: modern / near-future / fantasy / sci-fi / historical / alternate world
- Region and culture:
- Age range:
- Gender:
- Sexuality: specify or generate
- Social class:
- Education level:
- Occupation or skill set:
- Political environment:
- Story function: protagonist / antagonist / supporting role / mentor / foil / unreliable narrator
- Tone: realistic / noir / coming-of-age / crime / warm / cold / absurd
- Must include:
- Must avoid:
- Sensitive boundaries:
- Need social platform IDs: yes / no
- Need legal-risk attitude: yes / no
```

## Generation Workflow

### 1. Build Constraints

Create a concise constraint list before generating:

- Cultural naming rules
- Age / birth year / career timeline
- Language and platform habits
- Political environment
- Class background
- Story function
- Safety boundaries

Completion criterion: basic identity choices do not contradict each other.

### 2. Generate Core Identity

Generate:

- Local name
- Romanized or English name where appropriate
- Nickname
- Nationality
- Growth location and current city
- Gender
- Sexuality
- Birth date
- Zodiac sign
- Age
- MBTI
- Languages
- Education
- Occupation
- Social class

Rules:

- Zodiac must match birth date.
- Age must match birth date relative to the story year, if a story year is provided.
- MBTI must not dominate the personality.
- Names must fit the specified culture, generation, and language context.
- If using romanization, explain the system or convention briefly.
- Do not invent official-looking identity numbers, passport numbers, national IDs, phone numbers, or real addresses.

Completion criterion: the character can be placed into a plausible society without looking like a random form fill.

### 3. Explain Name and Cultural Plausibility

Include:

- Why the name fits the country or region
- Formal vs informal name usage
- Family or friend nickname patterns
- Romanization, transliteration, or English-name convention where relevant
- Any class, generation, diaspora, or regional nuance in the name

Completion criterion: a reader can see why this character's name belongs to the stated culture.

### 4. Build Causal Personality

Do not list adjectives alone. Connect:

```text
family background → formative wound → values → surface behavior → contradiction → pressure response
```

Include:

- Surface personality
- Deep personality
- Core desire
- Core fear
- Core contradiction
- Self-deception
- Stress behavior
- Intimacy weakness

Completion criterion: at least two personality traits are traceable to family, class, or formative experience.

### 5. Build Family, Class, and Daily Life

Include:

- Family structure
- Parents' occupations and values
- Sibling relationships, if any
- Family economic condition
- Education path
- Work and income status
- Daily routine
- Consumption habits
- Clothing style
- Food, caffeine, alcohol, smoking, exercise, or other habits
- Room, desk, or personal space details
- Everyday object they carry

Completion criterion: the character has enough material detail to be written in a scene.

### 6. Build Relationships and Sexuality

Sexuality should affect identity and relationships naturally, without becoming the entire character.

Include:

- Friendship style
- Intimacy pattern
- How sexuality affects self-understanding or relationship risks
- Who they are drawn to
- How they hurt others
- How others hurt them
- What they hide in relationships

Completion criterion: sexuality is integrated into the character's social life, not treated as a decorative label.

### 7. Build Politics and Social View

Generate political tendency as a product of age, family, class, education, region, and social environment.

Include:

- Political tendency
- Formation cause
- View of authority, government, police, platforms, or institutions
- Social issues that trigger them
- What they say publicly
- What they privately believe

Rules:

- Avoid flattening politics into generic left/right labels when local context matters.
- Do not claim the character represents an entire nationality, ethnicity, gender, or sexuality.

Completion criterion: politics create story pressure and have personal causes.

### 8. Build Moral Boundaries and Legal-Risk Attitude

For illegal events, describe attitude, not methods. This section is for narrative psychology and conflict design only.

Include reactions to:

- A friend committing a minor offense
- A company asking for gray-area behavior
- A family member committing a crime
- Personal gain at a stranger's expense
- Facing legal risk

Also include:

- Their moral bottom line
- What they most easily rationalize
- What they would never do
- First reaction when exposed

Safety rules:

- Do not provide procedural illegal guidance.
- Do not provide evasion, fraud, hacking, stalking, forgery, coercion, or deception instructions.
- Keep the focus on values, fear, rationalization, and story consequences.

Completion criterion: this section can drive a plot conflict without teaching how to commit wrongdoing.

### 9. Build Social and Internet Identity

Generate fictional social accounts that reflect the character.

Include:

- Main platforms
- Public ID
- Private or alt account style
- Bio
- Avatar style
- Posting frequency
- Common post topics
- Liked / saved content
- Gap between online and offline self

Safety rules:

- Do not generate passwords.
- Do not generate real phone numbers, addresses, identity numbers, bank data, or usable credentials.
- Do not use real celebrity, brand, company, government, or institution impersonation.
- Account names should be fictional and clearly story-use only.
- If an account name might plausibly be real, add a note that it is fictional and should be checked before public use.

Completion criterion: the account style reveals personality, age, class, profession, and online/offline tension.

### 10. Build Account Style and Digital Habits

Include safe, non-usable patterns only:

- Common account prefix style
- Email style, without a real mailbox claim
- Gaming ID style
- Work account style
- Password habit description, without producing an actual password
- Device preference
- Privacy attitude

Allowed:

```text
They tend to reuse pet names and old addresses in weak passwords.
```

Forbidden:

```text
Password: realOrUsablePassword123
```

Completion criterion: digital habits are useful for characterization but not usable as credentials.

### 11. Add Motto, Voice, and Dialogue

Include:

- Public motto
- What they actually believe
- Speech rhythm
- Common phrases
- Three sample lines of dialogue
- Gesture or small habit
- A disliked sound, smell, or scene

Completion criterion: the reader can hear the character's voice.

### 12. Add Character Arc and Plot Hooks

Include:

- Initial state
- Inciting event
- Midpoint choice
- Breaking point
- Possible final change
- If they fall, how they fall
- If they grow, what they lose
- Three ready-to-use plot hooks

Completion criterion: the character can enter a story immediately.

### 13. Run a Uniqueness Check

Before finalizing, check:

- Is this character too close to a common trope?
- If the name is removed, is the character still identifiable?
- Do family, politics, sexuality, online habits, and morality interact?
- Are there at least three specific details that cannot be swapped into any other character?

If the answer is weak, revise before output.

Completion criterion: the final profile includes three irreplaceable details and a clear contrast with common same-type characters.

## Output Format

Use standard Markdown. Preserve this structure unless the user requests a shorter format.

Whenever the agent environment supports file creation or attachment, also save the final character profile as a standalone `.md` file in addition to replying with the content or summary. Use a safe, portable filename derived from the character name, for example:

```text
character-sok-vichea.md
角色背景-sok-vichea.md
```

If the environment does not support writing files, output the complete Markdown content in the response and explicitly state that it is ready to copy into a `.md` file.

Completion criterion: after generation, the user either receives a Markdown file or receives complete Markdown content that can be saved directly.

```markdown
# 角色背景：{姓名}

## 1. 一句話定位

> {用一句話說明這個角色的本質、矛盾或戲劇功能。}

---

## 2. 基本資料

| 欄位 | 內容 |
|---|---|
| 中文 / 本地姓名 |  |
| 羅馬字 / 英文名 |  |
| 暱稱 |  |
| 國籍 |  |
| 成長地 |  |
| 現居地 |  |
| 性別 |  |
| 性向 |  |
| 出生年月日 |  |
| 年齡 |  |
| 星座 |  |
| MBTI |  |
| 母語 |  |
| 其他語言 |  |
| 職業 |  |
| 教育背景 |  |
| 社會階層 |  |
| 主要網路 ID |  |
| 常用帳號前綴 |  |
| 主要社群平台 |  |

---

## 3. 姓名與文化合理性

- 姓名來源：
- 為什麼符合該國 / 該地區命名習慣：
- 家人或朋友如何稱呼他/她：
- 正式場合與網路場合的名字差異：

---

## 4. 外在形象與生活感

- 外貌重點：
- 穿著風格：
- 生活作息：
- 飲食 / 咖啡 / 酒精 / 菸 / 運動習慣：
- 房間或工作桌樣貌：
- 隨身物品：

---

## 5. 家庭背景

- 家庭結構：
- 父母職業與價值觀：
- 手足關係：
- 家庭經濟狀況：
- 家庭對他/她最大的影響：
- 他/她最想逃離家庭的哪一部分：
- 他/她其實又繼承了家庭的哪一部分：

---

## 6. 性格與心理結構

### 表層性格

- 

### 深層性格

- 

### 核心慾望

- 

### 核心恐懼

- 

### 核心矛盾

- 

### 自我欺騙

- 

### 壓力下的行為

- 

---

## 7. 人際與親密關係

- 交友方式：
- 親密關係模式：
- 性向如何影響他/她的關係與自我認同：
- 容易被什麼樣的人吸引：
- 最容易傷害別人的方式：
- 最容易被別人傷害的方式：

---

## 8. 政治傾向與社會觀

- 政治傾向：
- 形成原因：
- 對政府 / 權威的態度：
- 對社會議題的敏感點：
- 他/她公開會怎麼說：
- 他/她私下真正怎麼想：

---

## 9. 道德邊界與違法事件態度

| 情境 | 反應 |
|---|---|
| 朋友輕微違法 |  |
| 公司要求灰色操作 |  |
| 親人犯罪 |  |
| 自己可能獲利但會傷害陌生人 |  |
| 面臨法律風險 |  |

- 他/她的底線：
- 他/她最可能合理化的行為：
- 他/她絕不會做的事：
- 被抓包後的第一反應：

---

## 10. 網路社群身份

| 平台 | ID / 帳號 | 使用方式 |
|---|---|---|
| Instagram |  |  |
| Threads / X |  |  |
| TikTok / YouTube |  |  |
| Discord / Reddit / Forum |  |  |
| 工作或作品平台 |  |  |

### 帳號命名邏輯

- 

### 公開 bio

```text

```

### 常見發文內容

- 

### 收藏 / 按讚內容

- 

### 網路人格與現實人格差異

- 

---

## 11. 常用帳號與數位習慣

> 只產生虛構、安全、不可登入的帳號風格；不產生真實密碼、個資、證件號或可冒用資訊。

- 常用帳號前綴：
- 常用 email 風格：
- 遊戲 ID：
- 工作帳號風格：
- 密碼習慣描述：僅描述風格，不產生實際密碼
- 裝置偏好：
- 對隱私的態度：

---

## 12. 人生座右銘

> {一句符合角色世界觀但不過度中二的座右銘。}

- 他/她公開會說的版本：
- 他/她真正相信的版本：

---

## 13. 語言習慣與對話樣本

### 說話特徵

- 

### 常用詞

- 

### 三句對話樣本

1. 「」
2. 「」
3. 「」

---

## 14. 角色弧線

- 初始狀態：
- 觸發事件：
- 中段選擇：
- 最大崩潰點：
- 最終可能變化：
- 如果黑化，會怎麼黑化：
- 如果成長，會失去什麼：

---

## 15. 獨特性檢查

- 這個角色最不像模板角色的地方：
- 三個不可替代細節：
  1. 
  2. 
  3. 
- 如果把姓名拿掉，仍能辨認他/她的特徵：
- 與常見同類角色的差異：

---

## 16. 可直接使用的劇情鉤子

1. 
2. 
3. 
```

## Safety Boundaries

This skill may create fictional identity *style*, but not usable identity infrastructure.

Allowed:

- Fully fictional characters
- Fictional social IDs for storytelling
- Account naming style
- Email style without claiming the mailbox exists
- Password habit description without actual passwords
- Psychological attitude toward illegal or gray-area events
- Moral conflict design

Forbidden:

- Real addresses, phone numbers, identity numbers, passport numbers, bank data, or passwords
- Fraud-ready persona packages
- Instructions for impersonation, social engineering, stalking, hacking, forgery, or evasion
- Claims about real people’s sexuality, politics, mental health, or private life
- Operational steps for illegal acts

## Common Pitfalls

1. **Name-only culture swap.** Fix by changing language, family, politics, platform habits, and social class together.
2. **MBTI determinism.** MBTI is shorthand, not destiny.
3. **Contradiction-free character.** Add a desire/fear conflict.
4. **Fake realism through trivia.** Details must reveal character or story pressure.
5. **Unsafe identity generation.** Never produce usable credentials, real addresses, ID numbers, or fraud-ready profiles.
6. **Illegal attitude becomes illegal instruction.** Keep it psychological and narrative.
7. **Platform leakage.** Do not mention Codex, Hermes, Claude Code, OpenCode, or any other agent platform in the generated character file unless the user explicitly asks for a meta note about the tool used.
8. **Over-asking.** If missing details can be safely inferred, generate with assumptions instead of asking many setup questions.

## Verification Checklist

- [ ] Name fits country, generation, and language convention
- [ ] Birth date, age, and zodiac are consistent
- [ ] Family background explains at least two personality traits
- [ ] Political stance has social and personal causes
- [ ] Sexuality affects relationships without becoming the whole character
- [ ] Online IDs reflect personality and platform culture
- [ ] No real credentials, address, ID number, or impersonation target included
- [ ] Illegal-event section describes moral attitude only
- [ ] Character has a core contradiction
- [ ] Character has three irreplaceable details
- [ ] Character remains recognizable if the name is removed
- [ ] Final output is standard Markdown and contains no platform-specific execution instructions
