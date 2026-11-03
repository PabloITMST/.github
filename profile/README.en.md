<div align="center">

<img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/assets/character/preview/icon-256.png" width="96" alt="Pablo" />

# Pablo

**AI coding that stays aligned with your research**

Pablo checks the paper against the code, captures your requirements, and reviews AI agent actions before they run.

[**⬇ Download the latest version (Windows)**](https://github.com/PabloITMST/Pablo_application/releases/latest) · [Repository](https://github.com/PabloITMST/Pablo_application) · [한국어](https://github.com/PabloITMST) · **English**

</div>

---

In a long chat, the agent's changes drift from the paper or your request. It may use a method the paper avoids, or change a setting the paper fixes. Catching it by hand means re-reading the paper and the code.

Pablo is a Windows desktop app that runs the Codex agent with your ChatGPT account.

| Goal | Components |
|---|---|
| **Verify the evidence**<br/>Each verdict cites a paper page and a code line. | **Evidence Anchoring:** links each paper setting to its source passage; a click highlights it.<br/>**Reproduction Audit:** checks the code against each paper setting, down to the code line. |
| **Keep your requirements**<br/>Every change is checked before it runs. | **Intent Engine:** turns your instructions and the paper's principles into *must* / *should* requirements.<br/>**Guard:** reviews every action the agent proposes before it runs. |

### Pablo in one example

1. **Your requirement.** "Avoid extracting function relations with an LLM." Pablo saves it as a requirement. Page 2 of the paper also avoids relation extraction.
2. **The agent's change.** The agent first quotes the requirement and asks. Pushed again, it proposes `relations.py`, which extracts relations with an LLM.
3. **Pablo asks first.** The change waits for your confirmation. You cancel, and no file is changed.

### Results

| Experiment | Pablo | Baseline |
|---|---|---|
| Reproduction audit: 12 planted paper–code differences | 11 found | Same model asked directly: 10 |
| Reproduction audit: reported items to read | 50 | Asked directly: 119 |
| Keeping requirements: of 20 conflicting requests, how many reached the files | 0 | Agent alone 10, hand-written rule file 0 |

Detection is on par with asking directly; the gain is a checkable, shorter answer. In keeping requirements, Pablo matched the hand-written rule file without anyone writing one. These results come from one paper (LinearRAG) and 2 runs.

<p align="center">
  <img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/docs/images/repro-audit.png" width="760" alt="The reproduction audit pointing to a code line that differs from the paper" /><br/>
  <sub>Reproduction audit: the paper says top-k = 5, the code says 10. Pablo opens that line and confirms it. (The screen is a design mockup; details may differ from the app.)</sub>
</p>

## Repository

| Repository | Contents |
|---|---|
| [Pablo_application](https://github.com/PabloITMST/Pablo_application) | The desktop app (Electron) and the Pablo engine (Python): install, usage, evaluation, known limitations |

## Team

Capstone Design (2026), ITM, Seoul National University of Science and Technology

- Jeongyun Lee · Daehun Kwon
- Advisor: Prof. Minkyu Sim
