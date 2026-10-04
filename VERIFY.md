# How to verify this record

**That the files have not changed since publication.** `sha256sum -c SHA256SUMS` in this folder.

**That the case descriptions are the ones the twins saw.** `sha256sum packets/*.md` and compare with the `packets` block of `sealed/RUN_RECORD.json`; those hashes are also recorded in the run log inside the sealed run folder.

**That the sealed files, when released, are the originals.** For each row of `sealed/SEALED_HASHES.csv`, the released prompt file must have the `prompt_sha256` listed, the released response the `response_json_sha256`, and so on. The run log and provider results file must hash to the values in `run_files_sha256`.

**That the predictions were fixed before argument.** The repository's first commit and release carry the platform's timestamps; the FantasySCOTUS entries carry the site's; the Projects page on talkingtomachines.org links here. All predate the arguments listed in `outcomes_2026-10-04.csv`.
