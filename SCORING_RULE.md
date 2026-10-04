# Scoring rule (fixed 4 October 2026, before argument)

1. **Cases.** Every case argued in a sitting that we file is filed in full — all nine Justices — before its argument. We do not select cases after the fact. If a sitting is not filed, it is not scored; the record says which sittings were filed.
2. **Outcome.** A case is scored "correct" if the filed outcome (Affirm or Reverse) matches the Court's judgment as to the party that prevails. Vacate-and-remand counts as Reverse; a dismissal that leaves the judgment below in place counts as Affirm. A case dismissed as improvidently granted, or decided without a majority judgment for either side, is unscored.
3. **Justice votes.** Each filed per-Justice entry is scored against that Justice's actual vote on the judgment (majority or dissent on the disposition, not on reasoning). A Justice who took no part is unscored. A Justice recorded as recused on FantasySCOTUS at filing has no entry and is unscored.
4. **Probabilities.** The twin's probability that the petitioner prevails is scored by the Brier score against the Justice's actual vote; reported alongside accuracy.
5. **Comparison.** The FantasySCOTUS crowd prediction as displayed at the time of filing is recorded for each case (see `outcomes_*.csv`) and scored by the same rule.
6. **No edits.** A filed entry is never changed after argument. Corrections of clerical errors before argument are recorded in this repository's history.
7. **Release.** When the Court decides a case, the sealed inputs and outputs for that case (see `sealed/`) are published, and the published files must hash to the values recorded here.
