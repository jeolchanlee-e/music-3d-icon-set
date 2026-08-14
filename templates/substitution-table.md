치환값 표 — 악기 3D 아이콘 세트 (변주값)
12개 아이콘을 생성할 때 마스터 프롬프트에서 바꾸는 값만 정리한 문서입니다.
스타일 규칙(고정값)은 style/instrument-icon-style.md 참고.
사용법
style/instrument-icon-style.md의 마스터 프롬프트를 복사
아래 표에서 해당 번호의 값을 찾아 {OBJECT} 한 곳만 치환
네거티브 프롬프트([DO NOT])는 12장 전부 동일하게 사용
레퍼런스 이미지는 매번 두 장 첨부
IMAGE 1 (스타일 레퍼런스): 항상 동일한 1번 기타 기준 컷 이미지. 재질·색·조명·배경·카메라 앵글·프레이밍을 정의.
IMAGE 2 (형태 레퍼런스): 해당 번호 오브젝트의 실물 사진. 실루엣과 비율만 정의하며, 그 외 속성(색·재질·배경·조명 등)은 절대 가져오지 않음
두 이미지가 형태 이외의 속성에서 충돌하면 IMAGE 1이 항상 우선
치환 대상은 한 개뿐입니다.
A stylized 3D product render of a {OBJECT}.
​
12개 치환값
#
{OBJECT}
형태 레퍼런스(IMAGE 2)로 사용할 사진
1
electric guitar
기준 기타 실물 사진 (IMAGE 1과 동일 오브젝트)
2
bass guitar
베이스 기타 실물 사진
3
drum
드럼 단독 실물 사진
4
synthesizer keyboard
신디사이저(2옥타브급) 실물 사진
5
guitar amplifier cabinet
기타 앰프 캐비닛 실물 사진
6
guitar effect pedal
이펙트 페달 실물 사진
7
studio headphones
스튜디오 헤드폰 실물 사진
8
condenser microphone
콘덴서 마이크 실물 사진
9
guitar pick
기타 피크 실물 사진
10
vinyl record
바이닐 레코드 실물 사진
11
coiled audio cable with jack plug
코일 케이블(잭 플러그 포함) 실물 사진
12
concert ticket
콘서트 티켓 실물 사진
예외 처리
고정값을 그대로 적용하면 깨지는 대상이 2개 있습니다. 해당 번호에만 아래 문장을 프롬프트에 추가하거나 SHELL 문장을 교체하세요.
#
대상
처리
10
vinyl record
추가: white vinyl pressing, not black vinyl
12
concert ticket
SHELL 문장 교체: semi-gloss card stock instead of lacquer
생성 순서
6 → 5 → 3 → 8 → 4 → 2 → 1 → 7 → 12 → 10 → 9 → 11
박스형 오브제로 스타일을 먼저 굳히고, 곡선물과 평면물을 마지막에 배치합니다.
가장 어려운 대상은 11번(코일 케이블)이므로 스타일이 완전히 안정된 뒤에 시도합니다.
난이도 메모
생성 전 예상 실패 지점입니다. 결과 확인 시 이 항목부터 점검하세요.
#
대상
예상 문제
3
drum
드럼 킷 전체가 생성됨 → 네거티브의 group of items 확인
4
synthesizer keyboard
건반 수가 과다해짐 → IMAGE 2가 2옥타브급 실물인지 확인
9
guitar pick
프레임 점유율 85% 규칙이 무시되기 쉬움
10
vinyl record
검정 비닐로 생성됨 → 예외 처리 문장 필수
11
coiled cable
곡선이 챔퍼 규칙과 충돌, 형태가 뭉개짐
12
concert ticket
유광 래커가 적용되어 종이로 안 읽힘
변경 이력
이 파일을 수정할 때는 커밋 메시지에 이유를 함께 남깁니다.
초안: 12개 대상 확정, 실루엣을 가변값으로 분리
그래픽 존 항목 제거 — 무늬 밀도 통제가 어려워 GRAPHIC 층 자체를 폐기
마스터 프롬프트 개정: 실루엣이 IMAGE 2(형태 레퍼런스)에서 오도록 변경됨에 따라 [SILHOUETTE] 치환값 및 관련 예외(33도 대각 조정) 삭제. 치환 대상을 {OBJECT} 한 개로 축소하고, 레퍼런스 이미지 첨부 규칙(IMAGE 1 스타일 / IMAGE 2 형태)을 사용법에 명시
