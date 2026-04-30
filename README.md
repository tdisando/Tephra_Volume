# Isopach Thinning Analysis & Tephra Volume Estimation
Understanding semi-log curves of root-square area ($\sqrt{A}$; $km^2$) vs. thickness ($cm$).

## About the model
Welcome to the Tephra Volume project! This repository aims to provide a comprehensive understanding of tephra deposition and volume calculations, which are crucial in volcanic studies. We believe that knowledge sharing is vital for advancing research and fostering collaboration in the field. Our goal is to enhance educational resources for students, researchers, and enthusiasts alike.

- Deposition probability per distance step
- Particles of a given size have a fixed terminal velocity → they land within a characteristic radius
- The plume spreads laterally by diffusion → mass per unit area decreases outward
- The integral of all size classes produces the bulk thinning curve
- Estimate tephra volume

Inspired by the sustained Plinian columns characterised by single dominant transport pathways in Pyle (1989; https://doi.org/10.1007/BF01439773), the complex long‑duration behaviour expressed as two‑segment or broken‑exponential thinning in Fierstein & Nathenson (1992; https://doi.org/10.1007/BF00278005), the continuous proximal‑to‑distal range phenomena described by Bonadonna & Houghton (2005; https://doi.org/10.1007/s00445-004-0386-2), and the characteristic transport length with variable spread proposed by Bonadonna & Costa (2012; https://doi.org/10.1130/G32769.1).

## The Scientific Model
The models presented in this repository utilize various scientific principles to estimate the volume of tephra deposits based on several parameters. The methodology is grounded in peer-reviewed research and aims to provide reliable estimates that can be adapted to diverse scenarios. Our approach ensures clarity and usability for individuals exploring these concepts.


| Thinning model                 | Key behaviour                                   | Classic reference                | Essential interpretation                                      |
|-------------------------------|--------------------------------------------------|----------------------------------|---------------------------------------------------------------|
| **Exponential**               | Single‑segment decay                             | Pyle (1989)                      | Works for simple sustained Plinian columns; fails for complex or long‑duration eruptions. |
| **Broken exponential**        | Steep proximal + shallow distal segments         | Fierstein & Nathenson (1992)     | Captures coarse‑to‑fine transition; isopach analogue of bimodal TGSD. |
| **Power‑law**                 | Smooth curvature across full range               | Bonadonna & Houghton (2005)      | Fits gradual regime transitions; mirrors truncated power‑law TGSD behaviour. |
| **Weibull**                   | Flexible form (includes exponential & power‑law) | Bonadonna & Costa (2012)         | λ = dispersal distance; k = deposit spread (sorting analogue). |


### Input Parameters
Users can input thickness and area parameters through the provided interfaces. Make sure to:
1. **Thickness:** Enter the measured thickness of tephra in centimeters (cm).
2. **Area:** Specify the area over which the tephra has been deposited in square meters (m² or km²).

### Selecting Curves
Once the parameters are entered, users can select appropriate curves from the displayed options. Each curve corresponds to different models and can be analyzed to draw conclusions based on the inputs provided.
