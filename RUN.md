# PReSto BayGMST run on PReSto2k 0_0_1

This repository runs the PReSto BayGMST reconstruction on the [PReSto2k 0_0_1](https://lipdverse.org/PReSto2k/0_0_1/) compilation, screened against local HadCRUT5 temperature (presto-recipes [`PReSto2k_0_0_1_localfdr10`](https://github.com/paleopresto/presto-recipes/blob/pools-2026-10-15b-r1/pools/config/PReSto2k_0_0_1_localfdr10.yml): temperature-interpreted records with a local correlation of the expected sign, BH FDR < 0.10 over 1850-2000, lag-1 autocorrelation at most 0.98): 230 records.

- Membership comes only from the published compilation, read from the
  LiPDverse whole-database export
  [2026-10-15b](https://lipdverse.org/dev/export/database-2026-10-15b/)
  (`compilations` table) by presto-recipes `pools/compilation_pool.R`.
- `query_params.json` (`mode: bundle`) pins the bundle by URL and sha256:
  presto-recipes release
  [pools-2026-10-15b-r1](https://github.com/paleopresto/presto-recipes/releases/tag/pools-2026-10-15b-r1).
  Its files are the compilation's LiPD files, checked against the export's
  md5 values and trimmed to the member records.
- The code and algorithm config are those of
  [presto-BayGMST-run-2026-10-08b](https://github.com/paleopresto/presto-BayGMST-run-2026-10-08b),
  unchanged, so this run differs from that one only in where its data come
  from.

Committing `query_params.json` triggers the reconstruction workflow.
