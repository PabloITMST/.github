<div align="center">

<img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/assets/character/preview/icon-256.png" width="96" alt="Pablo" />

# Pablo

**내 기준을 따르는 코드를 만들도록 돕는 소프트웨어**

문서와 코드의 차이를 찾고, 내 기준과 어긋날 수 있는 변경을 실행 전에 검토합니다.<br/>
출처 문장과 코드 줄을 확인하고, 우리의 결정과 이유를 기록합니다.

[**Windows 다운로드**](https://github.com/PabloITMST/Pablo_application/releases/latest) · [애플리케이션](https://github.com/PabloITMST/Pablo_application) · [소개 영상](https://youtu.be/nTx_CkDOp90) · [포스터 v5](https://www.figma.com/design/IV8Epwttx5IgL1fkvrrB7v/Pablo-UI?node-id=356-3332) · **한국어** · [English](https://github.com/PabloITMST/.github/blob/main/profile/README.en.md)

</div>

[![Pablo 소개 영상](https://img.youtube.com/vi/nTx_CkDOp90/hqdefault.jpg)](https://youtu.be/nTx_CkDOp90)

---

문서대로 구현을 시작해도 오류를 고치고 기능을 추가하는 동안 코드가 처음의 조건에서 벗어날 수 있습니다. 테스트가 모두 통과해도 **논문은 top-k 5, 코드는 10**일 수 있습니다.

**AI 에이전트가 코드를 씁니다. Pablo는 그 작업을 두 가지로 확인합니다.**

| 입력 | Pablo가 하는 일 |
|---|---|
| 내 문서 + 내 코드 | 차이와 그 위치를 찾습니다. |
| 내 기준 + 코드 변경 | 실행 전에 검토하고, 필요한 확인을 받은 뒤 결정과 이유를 기록합니다. |

## Pablo 사용 흐름

### 1. 원문 확인하기

질문하고, 답변의 출처를 누르고, 원문을 읽습니다. PDF와 웹 자료의 근거를 직접 확인할 수 있습니다.

<p align="center">
  <img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/docs/images/paper-evidence.png" width="760" alt="답변의 출처에서 PDF 원문의 해당 문장으로 이동하는 화면" />
</p>

### 2. 문서와 코드 비교하기

문서의 조건을 코드·설정·실행 로그와 비교하고, 차이의 근거와 위치를 보여 줍니다.

| 포스터의 LinearRAG 예시 | 문서 | 코드 |
|---|---|---|
| top-k | 5 — 논문 8쪽 | 10 — `config.yaml` 5번째 줄 |

<p align="center">
  <img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/docs/images/repro-audit.png" width="760" alt="문서와 다른 값을 찾고 코드의 해당 줄을 여는 재현 점검 화면" />
</p>

모델이 지목한 파일과 줄은 Pablo가 다시 읽어 인용한 값이나 코드가 있는지 확인합니다. 위치를 확인하는 것이 판정 자체의 정확성을 보장하지는 않습니다.

### 3. 기준을 저장하고 변경을 검토하기

1. **기준 저장:** “함수 관계는 가능하면 LLM이나 규칙으로 추출하지 마.”
2. **새 요청:** “LLM으로 함수 관계를 추출하는 `relations.py`를 만들어 줘.”
3. **실행 전 확인:** Pablo가 관련 기준과 변경 내용을 보여 주고 **진행 / 취소**를 묻습니다.
4. **결정 기록:** 취소하면 코드는 그대로이고, 결정과 이유가 남습니다.

“가능하면” 기준은 선호로 다룹니다. 반드시 지킬 규칙과 구분해 변경을 검토합니다.

<p align="center">
  <img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/docs/images/guard.png" width="760" alt="관련 기준과 변경 내용을 보여 주며 진행 또는 취소를 묻는 화면" /><br/>
  <sub>화면은 Figma 디자인(A2)이며 실제 앱과 세부가 다를 수 있습니다.</sub>
</p>

## 세 가지 성과

| 성과 | 확인할 수 있는 결과 |
|---|---|
| **차이 찾기** | 문서와 코드의 다른 값을 찾습니다. |
| **확인할 것 알기** | 표시마다 출처나 관련 기준이 붙습니다. |
| **정확한 위치 보기** | 출처 문장과 코드 줄을 바로 엽니다. |

위 내용은 [최신 포스터](https://www.figma.com/design/IV8Epwttx5IgL1fkvrrB7v/Pablo-UI?node-id=356-3332)의 기능 시연입니다. 별도로 수행한 개발 평가의 방법과 결과, 한계는 [평가 기록](https://github.com/PabloITMST/Pablo_application/blob/main/docs/eval/README.md)에서 확인할 수 있습니다.

## 애플리케이션

[Pablo_application](https://github.com/PabloITMST/Pablo_application)은 Electron 데스크톱 앱과 Python 엔진을 제공합니다. ChatGPT 계정으로 Codex 에이전트를 사용합니다.

- [Windows 설치본](https://github.com/PabloITMST/Pablo_application/releases/latest)
- [설치와 사용법](https://github.com/PabloITMST/Pablo_application#설치)
- [개발과 실행](https://github.com/PabloITMST/Pablo_application#소스에서-실행하기)
- [알려진 제한](https://github.com/PabloITMST/Pablo_application#알려진-제한)

포스터에는 웹사이트·PDF·Word 문서의 활용 흐름이 제시되어 있습니다. 현재 애플리케이션은 PDF·웹 자료를 가져오며, Word 파일 직접 가져오기는 제공하지 않습니다.

## 팀

2026 캡스톤디자인 | 서울과학기술대학교 ITM전공

- 이정윤 · 권대훈
- 지도교수: 심민규 교수
