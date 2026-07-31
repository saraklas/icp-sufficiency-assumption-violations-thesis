# Invariant Causal Prediction Under Violations of the Causal Sufficiency Assumption

Code and notebooks accompanying my bachelor's thesis on the behavior of
Invariant Causal Prediction (ICP) when the causal sufficiency assumption is
violated, i.e. when specific nodes of the data-generating graph are hidden
from the observed variable set.

## Overview

Experiments use the **causalAssembly** semisynthetic benchmark
(Göbler et al., 2024), restricted to the causal graph of **Station 5** (G⁵),
decomposed into two subsystems (System 1: response Y = node 84,
environments via node 87; System 2: response Y = node 92, environments via
nodes 85 and 94). Four sufficiency-violation scenarios are studied by hiding
one node at a time: a latent confounder (82), an omitted environment-driven
parent (89), a null control (83), and a benign violation in System 2 (95).
ICP is run with `lmICP` and `rangerICP` from the **tramicp** package
(GCM invariance tests, α = 0.05).

## Notebooks

The analyses were run in Jupyter notebooks; this repository contains their
**HTML exports** (the original `.ipynb` files live on a university JupyterHub
server).

| File | Contents |
|---|---|
| `html/Sufficient_system_sample_from_Station_5_only_using_G5.html` | Data generation: sampling the sufficient system from Station 5 using G⁵ only; replication loop over seeds. |
| `html/ICP_on_the_two_Station_5_systems.html` | ICP analysis on both subsystems (DAG/ADMG graphs, single-sample runs, replication over 20 seeds with selection frequencies). |

GitHub displays HTML files as source code. To view a rendered notebook, either
download the file and open it in a browser, or use
`https://htmlpreview.github.io/?<raw-file-URL>`.

## Dependencies

**Python:** `causalAssembly` (Bosch Research —
https://github.com/boschresearch/causalAssembly), `rpy2`, `pandas`, `numpy`.

**R:** `tramicp` (lmICP, rangerICP); `glip` (used for marginalizing the
ground-truth DAG to an ADMG over the observed variables; Kook & Mogensen, 2026).

The causalAssembly source code is **not** included in this repository; install
it from the upstream repository above.

## References

- J. Peters, P. Bühlmann, and N. Meinshausen. Causal inference by using
  invariant prediction: Identification and confidence intervals. *Journal of
  the Royal Statistical Society: Series B (Statistical Methodology)*,
  78(5):947–1012, 2016. doi: 10.1111/rssb.12167.
- K. Göbler, T. Windisch, M. Drton, T. Pychynski, M. Roth, and S. Sonntag.
  causalAssembly: Generating realistic production data for benchmarking causal
  discovery. In F. Locatello and V. Didelez, editors, *Proceedings of the
  Third Conference on Causal Learning and Reasoning*, volume 236 of
  *Proceedings of Machine Learning Research*, pages 609–642. PMLR, 2024.
  URL: https://proceedings.mlr.press/v236/gobler24a.html.
- L. Kook, S. Saengkyongam, A. R. Lundborg, T. Hothorn, and J. Peters.
  Model-based causal feature selection for general response types. *Journal
  of the American Statistical Association*, 120(550):1090–1101, 2025.
  doi: 10.1080/01621459.2024.2395588.
- L. Kook and S. W. Mogensen. Exact graph learning via integer programming,
  2026. URL: https://arxiv.org/abs/2601.20589.
- N. Pfister, P. Bühlmann, and J. Peters. Invariant causal prediction for
  sequential data. *Journal of the American Statistical Association*,
  114(527):1264–1276, 2019. doi: 10.1080/01621459.2018.1491403.

## Author

Sara Klasová — bachelor's thesis, Wirtschaftsuniversität Wien, 2026.
Supervisor: Dr. Lucas Kook.
