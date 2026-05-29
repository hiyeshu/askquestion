# AskQuestion

[中文](README.zh.md) / [English](README.md) / [日本語](README.ja.md)

AskQuestion은 대화 속에서 계속 자기 자신을 갱신하는 질문형 agent loop입니다.

모호한 아이디어를 지금 쓸 수 있고 다음 Shannon이 다시 소화할 수 있는 loop state로 압축합니다.

## 흐름

```text
Input -> Shannon -> Ockham -> Feynman -> Judge -> Loop State -> next Shannon pass or stop
```

- Shannon: 문제를 명확하게 만든다.
- Ockham: 불필요한 말을 잘라낸다.
- Feynman: 현재 결론을 사람이 다시 말할 수 있을 만큼 압축한다.
- Judge: 멈출지, 압축된 상태를 다음 Shannon에게 돌려보낼지 판단한다.

Feynman은 끝점이 아닙니다. 대화가 계속되어야 한다면 그 출력은 다음 Shannon의 입력이 됩니다.

## 기본 출력

```text
Current conclusion:

Compression:

Why:

Loop state:
- Root problem:
- Scope:
- Success signal:
- Biggest risk:

Shannon hooks:
1.
2.
3.

Next:
```

## 적합한 용도

- 프로젝트 착수
- 제안서 압축
- 요구사항 정리
- 의사결정 브리프
- 인터뷰 질문 설계
- agent loop 설계

## 저장소 내용

```text
SKILL.md
references/thinking-tools.md
README.md
README.zh.md
README.ja.md
README.ko.md
```

루트의 `SKILL.md`가 skill 본체입니다. 추가 `skills/askquestion` 래퍼는 없습니다.

선택적 전역 메모리는 `~/.askquestion/memory.md`에 둡니다. 이것은 사용자 수준 상태이며 저장소 내용이 아닙니다.

## 설치

[skills CLI](https://www.skills.sh/docs)로 Codex에 설치합니다:

```bash
npx skills add hiyeshu/askquestion -g --agent codex --skill askquestion
```

skills CLI 텔레메트리를 끄려면:

```bash
DISABLE_TELEMETRY=1 npx skills add hiyeshu/askquestion -g --agent codex --skill askquestion
```

## 60초 버전

```text
어떤 문제가 있는가?
누구에게 영향을 주는가?
왜 지금 처리해야 하는가?
이번에는 무엇을 하고, 무엇을 하지 않는가?
성공은 어떤 변화로 확인되는가?
가장 큰 위험은 무엇인가?
다음 Shannon은 무엇을 확인해야 하는가?
```
