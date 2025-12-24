DCIN 제안 포맷 (사람 주민번호와 확실히 다르게)

DCIN-V1-KR-YYYYMMDD-XXXXXX-CCCC

DCIN : 고정 프리픽스 (사람 신분번호와 구분)

V1 : 버전

KR : 국가/스키마 코드(원하면 PZ(Perzeam) 같은 네임스페이스로 바꿔도 됨)

YYYYMMDD : “발급일” (출생일처럼 오해될 수 있어 발급일로 고정)

XXXXXX : 랜덤(또는 시퀀스) 6자리 Base32/hex 축약값

CCCC : 체크섬(오타 검출용)

추가로 “캐릭터 본체”를 묶는 핵심은 번호가 아니라 Manifest 해시야.

Identity Manifest (캐릭터 개체 정의 파일)

manifest.json에 아래를 넣고,

portrait_hash (이미지 SHA-256)

canonical_prompt (원본 프롬프트/제작조건)

creator (너)

universe (19번방 세계관 등)

notes (식별 특징: 헤어, 눈, 분위기 등)

그리고 전체 manifest.json을 SHA-256 해시로 고정 → 그 해시가 “칩” 역할.
