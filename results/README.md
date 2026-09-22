# Results kept on this branch

`lazylean-2026-09-22.json` is the `_build/results.json` written by `lka.py write-results` after
`lka.py build-test` (all test definitions) and `lka.py run --checker` for six checkers, on one
rented machine (AMD EPYC 7B13, 64 threads, 503 GB), 22 September 2026.

The six are Lean's own kernel through the `official` checker, and the five fastest of the other
twenty-five, picked by building every checker that builds and timing it on `init` and `std`
rather than by reputation: `nanoclo`, `nanoda`, `still-nanoda`, `eink0rn`, and `lazylean`
itself. Four candidates did not build on that machine (`sokonanoda`, `nanoclo-fortran`,
`tenet`, `mathgraph`) and `kiota` timed out on `std`; the remaining checkers in the file carry
only the `init`/`std` measurements used for that selection, or none at all.

`lazylean` runs at version 0.2.0 with `-j 8`, which checks eight declarations at a time in
separate processes over one parse of the export.

Memory (`max_rss`) is zero throughout: the runner could not measure it on that machine.
