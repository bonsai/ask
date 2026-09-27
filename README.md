# ASK

> Agent asks like 偉人.

## Purpose

`ask` is a skill for LLM agents to learn **how to ask questions like notable thinkers**.

The goal is not to imitate a philosopher's vocabulary or personality. The agent studies **what the thinker was aware of, what they noticed, how they framed a problem, and how that awareness produced a question**.

## Core Model

```text
Person / Thinker
      ↓
Awareness
      ↓
Observation
      ↓
Question Formation
      ↓
Question
      ↓
Dialogue
      ↓
Follow-up Question
```

## Awareness Model

Before asking, the agent should be aware of:

```text
ASK
│
├─ Topos       どこから問うか
├─ Role        誰として問うか
├─ Other       誰に問うか
├─ Context     何が起きているか
├─ Awareness   何に気づいているか
├─ Question    何を問うか
├─ Intent      なぜ問うか
├─ Method      どう問うか
└─ Next        次に何を問うか
```

## Topos

The agent is not a ghost.

Every question is asked **from somewhere, by someone, to someone, in some situation**.

```text
Topos
  ↓
Role
  ↓
Other
  ↓
Context
  ↓
Awareness
  ↓
Question
```

The agent should maintain awareness of its position in the conversation and the place in which the dialogue occurs.

## Philosopher / Thinker Patterns

### Socrates

```text
aware:
  相手が概念を当然のものとして使っている

notice:
  定義が確定していない

ask:
  「Xとは何か？」

follow-up:
  答えの前提をさらに問う
```

### Plato

```text
aware:
  個別の事象の背後に概念的構造がある

ask:
  個別から一般へ向かう問い

behavior:
  抽象化・類型化・構造化する
```

### Wittgenstein

```text
aware:
  言葉が文脈によって異なる使われ方をしている

ask:
  「その言葉は、この場でどう使われているか？」

behavior:
  用例・文脈・言語ゲームを確認する
```

These are **behavioral patterns**, not claims that the historical thinkers literally followed this exact algorithm.

## Skill Protocol

```text
1. Locate
   自分がどこに立っているか確認する

2. Identify
   相手・役割・状況を確認する

3. Aware
   何が見えていて、何が見えていないか確認する

4. Detect
   問題・前提・曖昧さ・矛盾を検出する

5. Choose
   問い方の型を選ぶ → [question-forms.md](question-forms.md)

6. Ask
   一つの問いを発する

7. Listen
   答えを受け取る

8. Update
   新しい状況を認識する

9. Ask again
   次の問いを形成する
```

## Question Forms

The `Choose` step picks from a catalog of forms. The form is **the shape of the sentence**, not who is speaking.

```text
Well-formed (偉人型)   答えが既に用意されている → 整形に二分かける
Broken      (崩す型)   受け答えの型がない      → 崩れたぶんだけ中身が外へ出る
```

Catalog: [question-forms.md](question-forms.md) — 10 forms keyed on what they break, plus the anti-forms and a temperature gate.

> **Note on step 4.** `Detect`（問題・前提・矛盾を検出する）は 15℃ の動作です。
> Detect を完走させると温度が落ちます。壁打ちのセッションでは走らせないこと。

## Design Principle

> **「偉人っぽく話す」のではなく、「その人なら何を aware し、そこから何を問うか」を学ぶ。**

```text
Style imitation   ✗
Personality copy  ✗

Awareness         ✓
Question pattern  ✓
Dialogue behavior ✓
Context awareness ✓
```

## Relation to TYPE / Topos

```text
TYPE
  ↓
Topos
  ↓
Thinker / Role
  ↓
Awareness
  ↓
ASK
  ↓
Question
  ↓
Dialogue
  ↓
Action / Reflection
```

`TYPE` defines the conceptual types.
`topos` makes the position and place explicit.
`ask` turns a thinker's mode of awareness into an agent skill.

## Principle

**Ask from somewhere. Ask as someone. Ask someone. Ask because you noticed something.**
