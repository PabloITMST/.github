<div align="center">

<img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/assets/character/preview/icon-256.png" width="96" alt="Pablo" />

# Pablo

**처음 정한 기준을 지키는 연구 에이전트 작업대**<br/>
*A research-agent workbench that keeps the criteria you set first*

[**⬇ 최신 버전 받기 (Windows)**](https://github.com/PabloITMST/Pablo_application/releases/latest) · [저장소](https://github.com/PabloITMST/Pablo_application) · [English README](https://github.com/PabloITMST/Pablo_application/blob/main/README.en.md)

</div>

---

LLM 에이전트가 추천하는 대로 조금씩 고치다 보면, 처음 생각과 다른 결과물이 나옵니다. 연구 코드에서는 이런 어긋남이 실제 사고가 됩니다. 평가 데이터가 튜닝에 섞이고, 논문 설정이 근거 없이 바뀌고, 결과 수치가 실행 로그가 아닌 곳에서 옵니다.

Pablo는 ChatGPT 계정으로 Codex 에이전트를 쓰는 Windows 데스크톱 앱입니다. 에이전트 위에 세 가지를 얹습니다.

| | |
|---|---|
| **의도를 고정합니다** | 대화에서 말한 기준을 "반드시 / 가능하면"으로 기록합니다. 애매한 말은 사람이 정할 때까지 보류합니다. |
| **행동을 판정합니다** | 에이전트의 쓰기 행동은 모두 Guard를 거칩니다. 허용, 확인 필요, 막음 가운데 하나로 판정합니다. |
| **근거를 원문에 묶습니다** | 논문의 재현 조건과 인용은 원문 쪽에, 코드가 논문에서 벗어난 곳은 파일:줄에 묶습니다. 위치를 확인하지 못한 근거는 남기지 않습니다. |

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
