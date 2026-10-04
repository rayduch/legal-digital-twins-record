# Legal Digital Twins — prediction record, October 2026 sitting (batch 1)

Nine digital twins of the sitting Justices of the US Supreme Court, each conditioned only on that Justice's own
authored and joined opinions (October Terms 1991–2024), predicted the four cases argued 5–7 October 2026. The
predictions were filed on FantasySCOTUS on 4 October 2026, before argument, and are recorded here with the inputs the
twins saw and the hashes of everything else, so the record can be checked now and the rest verified when it is released.

Project: Raymond Duch (Nuffield College, Oxford) and Laurenz Günther (Toulouse School of Economics), Talking to Machines
initiative. Method essay: talkingtomachines.substack.com. Project page: talkingtomachines.org/projects.

## What is here

| File | What it is |
|---|---|
| `predictions_2026-10-04.csv` | 36 rows: each twin's vote, probability that the petitioner prevails, expected disposition, and the FantasySCOTUS entry filed (Alito in 25-170 recorded but not filed — recused on the site) |
| `outcomes_2026-10-04.csv` | Per case: the twins' outcome and split, the outcome as filed, and the FantasySCOTUS crowd at the moment of filing |
| `packets/` | The four one-page case descriptions the twins were given, byte-identical to the files hashed in the run log. Built on 30 September 2026 from the Court's Questions Presented, the decision below as described in the briefs, and the Summary of Argument sections of the merits briefs. The header's draft-stage "checker" field is left as it was; the Johnson packet was reviewed in the prompt sign-off of 3 October |
| `SCORING_RULE.md` | How the record will be scored, fixed in advance |
| `sealed/RUN_RECORD.json` | Run identity: model as requested and as returned, settings, index and template identifiers, packet hashes, hashes of the run log and provider results file, filing details, and what will be released on decision |
| `sealed/SEALED_HASHES.csv` | Per Justice per case: SHA-256 of the full prompt, the retrieved passage set, the evidence and context blocks, and the model's response, plus the provider's message id |
| `VERIFY.md` | How to check all of the above |
| `SHA256SUMS` | Hashes of every file in this folder |

## How a prediction is made

For each case the twin receives (i) the case packet, (ii) eight passages retrieved from that Justice's own prior
writing by three queries built from the packet — the question presented, the doctrinal area and precedents, and the two
sides' first arguments — subject to quotas (at least two passages from majority opinions and two from separate writings,
at most two from any one prior case), (iii) one-paragraph context for each prior case the passages come from, consisting
of the Reporter's syllabus (labelled as such) and the recorded vote, and (iv) the Justice's Martin–Quinn score for
October Term 2024. It returns a vote, a probability, an expected disposition, three considerations, a rationale naming
the passages it relied on, and self-assessed confidence and speculation.

Nothing from October Term 2025 or later is in the evidence; the case under prediction is excluded from retrieval by
identifier and by title; the packet is read by a person for anything that reveals an outcome before it is used. Model:
`claude-opus-5-5` (Anthropic), the identifier returned by the API on all 36 responses; adaptive thinking at medium effort,
4,000 output tokens including thinking, temperature at the API default; Messages Batch API. Run
`20261003T123540Z_october_opus55_codex`, executed by Laurenz Günther on 3 October 2026, 12:43–12:46 UTC.

## Validation, and why it is not a forecast

On the 58 argued cases of October Term 2025, with the decisions held out as the answer key, the same twins (on the
preceding index version and harness) matched 448 of 512 scorable individual votes (87.5%) and 52 of 57 outcomes;
Brier score 0.112. Those decisions were handed down between November 2025 and June 2026 and may fall inside the
model's training window; an independent screen of the 522 responses found one suggestive sign of recalled opinion
wording and no explicit admissions. We therefore report the figure as recovery of known outcomes, not as forecasting
skill. The cases in this record are the test.

## What is not here, and when it will be

The corpus, index, retrieval code, prompt template and harness are not published. The per-Justice prompts, retrieved
passages and full responses are sealed by hash and will be published case by case as the Court decides. The filing
screenshots are released with them.

## Filing

Entered on FantasySCOTUS by Raymond Duch on 4 October 2026 between approximately 08:35 and 09:05 UTC, one case at a
time, each saved once and not edited after. FantasySCOTUS listed Justice Alito as recused in 25-170, so that case was
filed with eight entries (Affirm 5–3); the nine-twin outcome was also Affirm.

Next: Beaird v. United States (25-5343, argued 13 Oct) and Salazar v. Paramount Global (25-459, argued 14 Oct), to be
filed on 11 October 2026 and added here as `*_2026-10-11.*`.

---
Content © 2026 Raymond Duch and Laurenz Günther; released under CC BY 4.0. Research commentary, not legal advice.
