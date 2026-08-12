# 치환값 표 — 악기 3D 아이콘 세트 (변주값)

12개 아이콘을 생성할 때 마스터 프롬프트에서 **바꾸는 값만** 정리한 문서입니다.
스타일 규칙(고정값)은 `style/instrument-icon-style.md` 참고.

---

## 사용법

1. `style/instrument-icon-style.md`의 마스터 프롬프트를 복사
2. 아래 표에서 해당 번호의 값을 찾아 `[OBJECT]`와 `[SILHOUETTE]` 두 곳을 치환
3. 네거티브 프롬프트는 12장 전부 동일하게 사용
4. **1번 기타 기준 컷 이미지를 매번 레퍼런스로 첨부** — 각도와 유광 하이라이트 톤은 문장으로 재현되지 않음

치환 대상은 두 개뿐입니다.

```
A stylized 3D product render of a [OBJECT].
Silhouette: [SILHOUETTE].
```

---

## 12개 치환값

| # | `[OBJECT]` | `[SILHOUETTE]` |
| --- | --- | --- |
| 1 | electric guitar | rounded double-cutaway body with soft horns |
| 2 | bass guitar | same body family as the guitar, longer neck |
| 3 | snare drum | plain cylinder with rounded rim |
| 4 | synthesizer keyboard | rounded rectangular slab, 2 octaves |
| 5 | guitar amplifier cabinet | rounded-corner box cabinet |
| 6 | guitar effect pedal | compact chamfered box |
| 7 | studio headphones | oval ear cups, smooth arc headband |
| 8 | condenser microphone | capsule cylinder, rounded grille top |
| 9 | guitar pick | teardrop with softly rounded tip |
| 10 | vinyl record | flat disc |
| 11 | coiled audio cable with jack plug | smooth coil, cylindrical jack housing |
| 12 | concert ticket | rounded rectangle with perforated edge |

---

## 예외 처리

고정값을 그대로 적용하면 깨지는 대상이 3개 있습니다. 해당 번호에만 아래 한 줄을 추가하거나 교체하세요.

| # | 대상 | 처리 |
| --- | --- | --- |
| 10 | vinyl record | 추가: `white vinyl pressing, not black vinyl` |
| 12 | concert ticket | SHELL 문장 교체: `semi-gloss card stock instead of lacquer` |
| 10, 12 | 평면물 | 33도 대각이 어색할 경우 `long axis` 대신 `the object's front face tilted 33 degrees clockwise`로 표현 조정 |

---

## 생성 순서

**6 → 5 → 3 → 8 → 4 → 2 → 1 → 7 → 12 → 10 → 9 → 11**

박스형 오브제로 스타일을 먼저 굳히고, 곡선물과 평면물을 마지막에 배치합니다.
가장 어려운 대상은 11번(코일 케이블)이므로 스타일이 완전히 안정된 뒤에 시도합니다.

---

## 난이도 메모

생성 전 예상 실패 지점입니다. 결과 확인 시 이 항목부터 점검하세요.

| # | 대상 | 예상 문제 |
| --- | --- | --- |
| 3 | snare drum | 드럼 킷 전체가 생성됨 → 네거티브의 `group of items` 확인 |
| 4 | synthesizer keyboard | 건반 수가 과다해짐 → `2 octaves` 명시 유지 |
| 9 | guitar pick | 프레임 점유율 85% 규칙이 무시되기 쉬움 |
| 10 | vinyl record | 검정 비닐로 생성됨 → 예외 처리 문장 필수 |
| 11 | coiled cable | 곡선이 챔퍼 규칙과 충돌, 형태가 뭉개짐 |
| 12 | concert ticket | 유광 래커가 적용되어 종이로 안 읽힘 |

---

## 변경 이력

이 파일을 수정할 때는 커밋 메시지에 이유를 함께 남깁니다.

- 초안: 12개 대상 확정, 실루엣을 가변값으로 분리
- 그래픽 존 항목 제거 — 무늬 밀도 통제가 어려워 GRAPHIC 층 자체를 폐기
