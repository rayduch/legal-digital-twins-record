# Legal Digital Twins — prediction record, October 2026 sitting

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

## Batch 2 — run on 11 October, not filed, published after argument, unscored

Beaird v. United States (25-5343, argued 13 October) and Salazar v. Paramount Global (25-459, argued 14 October) were
run on 11 October 2026 (Salazar 03:10–03:15 UTC, Beaird 05:23–05:32 UTC; runs `20261011T031028Z_salazar_opus55_codex`
and `20261011T052308Z_beaird_opus55_codex`, executed by Laurenz Günther, same model, settings, index and template as
batch 1). **They were not filed on FantasySCOTUS before argument**: the filing step scheduled for Sunday 11 October was
not carried out, and the omission was found on 21 October. Under rule 1 of `SCORING_RULE.md` an unfiled sitting is not
scored. The runs are published here on 21 October 2026 for transparency, with the time-stamps and hashes they carry in
the run folders, as `*_2026-10-11.*`; they have no pre-argument public time-stamp and **do not enter the scored record**.
The twins' predictions were Beaird: vacate (petitioner) 9–0; Salazar: reverse (petitioner) 7–2. The Beaird packet
defines the sides by disposition because the United States, the nominal respondent, supports vacatur (see the packet's
Procedural posture). Files: `predictions_2026-10-11.csv`, `outcomes_2026-10-11.csv`, `packets/OT2026_25-5343_Beaird.md`,
`packets/OT2026_25-459_Salazar.md`, `sealed/RUN_RECORD_2026-10-11.json`, `sealed/SEALED_HASHES_2026-10-11.csv`,
`NOTE_2026-10-21_batch2.md`.

(The November sitting's first batch was filed on 31 October 2026; see the next section.)

## Batch 3 — November sitting, filed 31 October 2026 before argument (scored)

Maxwell v. Dinis (25-5930, argued 2 November), Younge v. Fulton Judicial Circuit District Attorney's Office (25-352,
argued 2 November), St. Mary Catholic Parish v. Roy (25-581, argued 3 November) and Guerrero v. Johnson (25-1003, argued
4 November) were run on 30 October 2026 (18:24–18:32 UTC; runs `20261030T182415Z_maxwell_opus55_claude`,
`20261030T182506Z_younge_opus55_claude`, `20261030T182550Z_stmary_opus55_claude`, `20261030T182626Z_guerrero_opus55_claude`,
executed by Laurenz Günther; same model, settings, index and template as batch 1; 36 of 36 responses valid, model identity
consistent) and **filed on FantasySCOTUS by Raymond Duch on 31 October 2026, approximately 05:13–05:17 UTC**, one case at a
time, each saved once and verified by reload, two days before the first argument. No Justice was listed as recused.
Twins and filed entries: Maxwell Reverse 7–2 (Thomas and Alito affirm); Younge Reverse 9–0; St. Mary Reverse 6–3; Guerrero
Reverse 6–3 (Sotomayor, Kagan and Jackson affirm in both). The crowd at filing, read immediately after our entries were
saved and therefore including them: Reverse 8–1, 6–3, 6–3 and 5–4 respectively (`crowd_justices_2026-10-31.csv` has the
per-Justice figures). Files: `predictions_2026-10-31.csv`, `outcomes_2026-10-31.csv`, `crowd_justices_2026-10-31.csv`,
`packets/OT2026_25-5930_Maxwell.md`, `packets/OT2026_25-352_Younge.md`, `packets/OT2026_25-581_StMary.md`,
`packets/OT2026_25-1003_Guerrero.md`, `sealed/RUN_RECORD_2026-10-31.json`, `sealed/SEALED_HASHES_2026-10-31.csv`,
`filing_screenshots/2026-10-31_batch3/`.

Two alignment notes. In Maxwell the United States, the nominal respondent, supports vacatur and the Court appointed an
amicus to defend the judgment; the packet defines petitioner = reverse/vacate and respondent = affirm (as in Beaird). In
Guerrero the State is the petitioner, so a vote for the petitioner is a vote for the State against the capital prisoner.

Two retrieval notes, recorded here because they bear on what the twins were shown and will be visible when the sealed
material is released; neither changes an entry. (1) The harness builds its first retrieval query from the first paragraph
under the packet's question-presented heading. In Maxwell that paragraph was the one-line grant-limitation preamble
rather than the question, so the first of the three queries carried no legal content; the second (doctrinal area and
precedents) and third (the parties' first arguments) were unaffected, and every twin read the full packet including the
question. The same occurred in Beaird (batch 2). From batch 4 the question is the first paragraph of that section.
(2) The harness excludes from retrieval any prior writing whose case title shares a word with the target title; for
St. Mary the word was "Catholic", so prior writings in Catholic Charities Bureau v. Wisconsin (2025) and any other
"Catholic"-titled case were not retrievable for that case. Builder item: exclude by identifier and full title.

Next: batch 4 — Nielsen v. Watanabe (25-417) and Hoffmann v. WBI Energy Transmission (25-159), argued 9 November, and
Department of Labor v. Sun Valley Orchards (25-966), argued 10 November; packets by 5 November, run 7 November, filing
8 November.

---
Content © 2026 Raymond Duch and Laurenz Günther; released under CC BY 4.0. Research commentary, not legal advice.
