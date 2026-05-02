# Isopach Thinning Analysis & Tephra Volume Estimation

A browser-based tool for fitting isopach thinning curves and estimating tephra-fall deposit volumes

---

## Overview

Tephra deposits thin systematically with distance from the vent. Plotting $\sqrt{A}$ (km) against thickness $T$ (cm) on a semi-log axis reveals this thinning structure, and integrating the curve yields the total erupted volume. This tool fits four models simultaneously, reporting fitted equations, $R^2$, and volume in km³ or m³.

---

## Background

The x-axis uses $\sqrt{A}$ — the square root of the area enclosed by each isopach contour — rather than distance, so no assumption about isopach shape (circular, elliptical, irregular) is required (Fierstein & Nathenson 1992). The volume integral is:

$$V = \int_0^{\infty} T \, dA$$

| Model | Equation | Volume |
|---|---|---|
| **Exponential (1-seg)** | $T = T_0 \exp(-k\sqrt{A})$ | $V = \dfrac{2T_0}{k^2}$ |
| **Exponential (2-seg)** proximal | $T = T_0 \exp(-k_1\sqrt{A}), \quad \sqrt{A} \le \sqrt{A_{\rm ip}}$ | $V_{\rm prox} = \dfrac{2T_0}{k_1^2}\left[1 - (k_1\sqrt{A_{\rm ip}}+1)\exp(-k_1\sqrt{A_{\rm ip}})\right]$ |
| **Exponential (2-seg)** distal | $T = T_1 \exp(-k_2\sqrt{A}), \quad \sqrt{A} > \sqrt{A_{\rm ip}}$ | $V_{\rm total} = \dfrac{2T_0}{k_1^2} + 2T_0\left[\dfrac{k_2\sqrt{A_{\rm ip}}+1}{k_2^2} - \dfrac{k_1\sqrt{A_{\rm ip}}+1}{k_1^2}\right]\exp(-k_1\sqrt{A_{\rm ip}})$ |
| **Power law** | $T = T_{\rm pl}\,(\sqrt{A})^{-m}$ | $V = \dfrac{2T_{\rm pl}}{2-m}\left[C^{2-m}-B^{2-m}\right]$ |
| **Weibull** | $T = \theta\exp\left[-(\sqrt{A}/\lambda)^n\right]$ | $V = \dfrac{2\theta\lambda^2}{n}\,\Gamma\left(\dfrac{2}{n}\right)$ |

$R^2$ is computed on $\ln T$ residuals. Power-law integration requires finite limits $B$ (proximal, default 0.3 km) and $C$ (distal, default 1 000 km).

### Symbol glossary

| Symbol | Description |
|---|---|
| $T$ | Deposit thickness (cm) |
| $A$ | Area enclosed by an isopach contour (km²) |
| $\sqrt{A}$ | Square root of isopach area; used as the distance proxy (km) |
| $T_0$ | Extrapolated thickness at $\sqrt{A} = 0$ for the proximal segment (cm) |
| $k$ | Exponential decay rate of the 1-segment fit (km⁻¹); steeper $k$ = faster thinning |
| $k_1$ | Exponential decay rate of the proximal segment in the 2-segment fit (km⁻¹) |
| $k_2$ | Exponential decay rate of the distal segment in the 2-segment fit (km⁻¹); typically $k_2 < k_1$ |
| $T_1$ | Extrapolated thickness at $\sqrt{A} = 0$ for the distal segment (cm) |
| $\sqrt{A_{\rm ip}}$ | Break-in-slope: value of $\sqrt{A}$ where the two exponential segments intersect (km) |
| $V_{\rm prox}$ | Volume contributed by the proximal segment alone, from $\sqrt{A} = 0$ to $\sqrt{A_{\rm ip}}$ (km³) |
| $V_{\rm total}$ | Total deposit volume integrating both proximal and distal segments (km³) |
| $T_{\rm pl}$ | Power-law scaling coefficient (cm) |
| $m$ | Power-law exponent (dimensionless); controls rate of thinning with $\sqrt{A}$ |
| $B$ | Proximal integration limit for the power-law model (km); approximates vent radius |
| $C$ | Distal integration limit for the power-law model (km); approximates maximum dispersal |
| $\theta$ | Weibull thickness scale; maximum thickness extrapolated to $\sqrt{A} = 0$ (cm) |
| $\lambda$ | Weibull characteristic dispersal length (km); distance at which thickness drops to $\theta/e$ when $n = 1$ |
| $n$ | Weibull shape parameter (dimensionless); $n = 1$ recovers the exponential, $n < 1$ gives a heavier distal tail |
| $\Gamma$ | Gamma function: $\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}\,dt$ |
| $R^2$ | Coefficient of determination computed on $\ln T$ residuals; measures goodness of fit on the log scale |

---

## Entering your data

Up to 10 isopach pairs can be entered manually:

| Field | Unit | Requirement |
|---|---|---|
| T | cm | > 0 |
| A | km² | > 0 |

Row order does not matter — data are sorted by $\sqrt{A}$ internally. Four presets are available for immediate exploration: **Mt. St. Helens 1980**, **Ruapehu 1996**, **Hatepe 186 A.D.**, and **Quizapu 1932**.

---

## References

Bonadonna, C. & Costa, A. (2012). Estimating the volume of tephra deposits: A new simple strategy. *Geology*, 40, 415–418. https://doi.org/10.1130/G32769.1

Bonadonna, C. & Houghton, B. F. (2005). Total grain-size distribution and volume of tephra-fall deposits. *Bulletin of Volcanology*, 67, 441–456. https://doi.org/10.1007/s00445-004-0386-2

Fierstein, J. & Nathenson, M. (1992). Another look at the calculation of fallout tephra volumes. *Bulletin of Volcanology*, 54, 156–167. https://doi.org/10.1007/BF00278005

Pyle, D. M. (1990). New estimates for the volume of the Minoan eruption. Thera and the Aegean world III, 2, 113-121.

Pyle, D. M. (1989). The thickness, volume and grainsize of tephra fall deposits. *Bulletin of Volcanology*, 51, 1–15. https://doi.org/10.1007/BF01439773

---

## License

Released under the [MIT License](LICENSE). Free to use, modify, and redistribute with attribution.

*Made with ❤️ for the volcanology community*
