# Bootstrap Guide

이 문서는 `.ai-dev-template` 자체의 목적과 사용 순서를 빠르게 이해하기 위한 임시 안내서다.
프로젝트 전용 지침과 핵심 문서가 생성되기 전까지만 참고한다.

이 문서는 프로젝트의 source of truth가 아니다.
프로젝트 시작 후 실제 기준은 `docs/` 산출물과 05단계에서 생성한 프로젝트 전용 지침이다.

---

## 1. 이 템플릿의 목적

이 템플릿은 다음 균형을 맞추기 위해 존재한다.

- 초기부터 일관성과 구조 안정성을 확보한다
- 하지만 미래 기능을 미리 구현하거나 과도한 추상화를 만들지 않는다
- 코드, 문서, 지침의 역할을 분리해 장기 유지보수 비용을 낮춘다

핵심 원칙:

- spec 없이 구현하지 않는다
- architecture 없이 구조를 늘리지 않는다
- MVP baseline 전에는 프로젝트 지침을 구현 중 상태에 맞춰 흔들지 않는다
- baseline 이후에만 review/guideline-update 루프를 통해 지침을 보강한다

---

## 2. 문서 역할

초기 단계에서 문서 역할은 아래처럼 구분한다.

- `docs/SPEC.md`: 무엇을 만들지, 범위와 요구사항은 무엇인지
- `docs/PROJECT_CONTEXT.md`: 이 프로젝트의 핵심 맥락이 무엇인지
- `docs/DECISIONS.md`: 왜 그런 선택을 했는지
- `docs/ARCHITECTURE.md`: 어떤 구조와 경계로 구현할지
- 프로젝트 전용 지침 (`CLAUDE.md` 등): 구현 시 반복 적용할 규칙

중요:

- 코드가 source of truth인 세부 inventory를 문서에 복제하지 않는다
- 템플릿 설명 문서는 규칙을 소유하지 않는다
- 프로젝트 전용 지침 생성 후에는 이 문서를 계속 참조하지 않는다

---

## 3. 권장 흐름

1. `01_spec_draft.md`로 초안을 만든다
2. `02_critical_questions.md`로 설계 결정 질문을 정리한다
3. `03_final_spec.md`로 scope, acceptance criteria, contracts & invariants를 확정한다
4. `04_architecture.md`로 구조, 경계, 계약, 확장 포인트를 설계한다
5. `05_project_rules.md`로 프로젝트 전용 지침과 checkup 스킬을 생성한다
6. 그 이후에 구현을 시작한다
7. MVP 또는 첫 구현 baseline 완료 후 `06_review.md` → `07_guideline_update.md`를 수행한다

---

## 4. 언제 지침을 업데이트하는가

구현 중에는 사실 문서만 즉시 갱신한다.

- 설계 결정 추가 → `docs/DECISIONS.md`
- 임시 제약/우회 추가 → `docs/KNOWN_ISSUES.md`
- 외부 사용 방식 변경 → 필요 시 `README.md`

프로젝트 전용 지침 보강은 MVP 또는 첫 구현 baseline 완료 후에만 수행한다.
미구현, 부분구현, 임시 공백은 지침 수정 근거가 아니다.
단, 지침 자체가 잘못되었거나 충돌하거나 구현을 막는 경우는 예외다.

---

## 5. 삭제 시점

이 문서는 05단계 완료 직후 삭제한다.

삭제 기준:

- 프로젝트 전용 지침이 생성되었다
- `docs/SPEC.md`, `docs/PROJECT_CONTEXT.md`, `docs/DECISIONS.md`, `docs/ARCHITECTURE.md`가 준비되었다
- 이후 판단 기준이 이 문서가 아니라 프로젝트 산출물로 전환되었다

이 조건이 충족되면 이 문서는 남겨두지 않는다.
