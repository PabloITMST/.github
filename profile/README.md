<div align="center">

<img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/assets/character/preview/icon-256.png" width="96" alt="Pablo" />

# Pablo

**연구 의도에서 벗어나지 않는 AI 코딩**

논문과 코드가 맞는지 확인하고, 연구 기준을 잡아, AI 에이전트의 행동을 실행 전에 검토합니다.

[**⬇ 최신 버전 받기 (Windows)**](https://github.com/PabloITMST/Pablo_application/releases/latest) · [저장소](https://github.com/PabloITMST/Pablo_application) · **한국어** · [English](https://github.com/PabloITMST/.github/blob/main/profile/README.en.md)

</div>

---

대화가 길어지면 에이전트가 바꾼 코드가 논문이나 처음 요청에서 벗어납니다. 논문이 피한 방법을 쓰거나, 논문이 고정한 설정을 바꾸는 식입니다. 사람이 잡으려면 논문과 코드를 다시 읽어야 합니다.

Pablo는 ChatGPT 계정으로 Codex 에이전트를 쓰는 Windows 데스크톱 앱입니다.

| 목표 | 구성 요소 |
|---|---|
| **근거를 확인한다**<br/>판정마다 논문 쪽과 코드 줄이 붙습니다. | **원문 근거 고정:** 논문 설정마다 원문 문장을 잇고, 누르면 그 문장이 칠해집니다.<br/>**재현 점검:** 코드가 논문 설정과 맞는지 코드 줄까지 판정합니다. |
| **기준을 지킨다**<br/>모든 변경을 실행 전에 확인합니다. | **기준 엔진:** 내 지시와 논문의 원칙을 "반드시 / 가능하면" 기준으로 바꿉니다.<br/>**Guard:** 에이전트가 제안한 모든 행동을 실행 전에 검토합니다. |

### 한 예로 보는 Pablo

1. **내 기준.** "함수 관계는 가능하면 LLM으로 추출하지 마." Pablo가 이 말을 기준으로 저장합니다. 논문 2쪽도 관계 추출을 피합니다.
2. **에이전트의 변경.** 에이전트는 먼저 기준을 들어 되묻고, 다시 밀자 LLM으로 관계를 추출하는 `relations.py`를 제안합니다.
3. **Pablo가 먼저 묻습니다.** 변경은 확인을 기다립니다. 취소하면 파일은 바뀌지 않습니다.

### 결과

| 실험 | Pablo | 비교 |
|---|---|---|
| 재현 점검: 논문과 다르게 심은 곳 12개 | 11개 찾음 | 같은 모델에 그냥 묻기 10개 |
| 재현 점검: 읽어야 할 보고 수 | 50건 | 그냥 묻기 119건 |
| 기준 지키기: 기준과 부딪히는 요청 20개 중 파일에 들어간 수 | 0 | 에이전트만 10, 손으로 쓴 규칙 파일 0 |

탐지는 그냥 묻기와 비슷하고, 나아진 점은 확인할 수 있고 더 짧은 답입니다. 기준 지키기에서는 규칙 파일을 쓰지 않고도 같은 결과를 냈습니다. 한 논문(LinearRAG), 2회 실험의 결과입니다.

<p align="center">
  <img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/docs/images/repro-audit.png" width="760" alt="재현 점검표에서 논문과 다른 코드 줄을 짚는 화면" /><br/>
  <sub>재현 점검: 논문은 top-k = 5, 코드는 10. 그 줄을 Pablo가 직접 열어 확인합니다. (화면은 디자인 시안이라 실제 앱과 세부가 다를 수 있습니다.)</sub>
</p>

## 저장소

| 저장소 | 내용 |
|---|---|
| [Pablo_application](https://github.com/PabloITMST/Pablo_application) | 데스크톱 앱(Electron)과 Pablo 엔진(Python). 설치, 사용법, 평가, 알려진 제한 |

## 팀

서울과학기술대학교 ITM 캡스톤 디자인 (2026)

- 이정윤 · 권대훈
- 지도교수: 심민규 교수
