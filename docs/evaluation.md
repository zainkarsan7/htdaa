---
layout: default
title: Evaluation
nav_order: 3
---

# Estimating Recoverability:

This part deals with how to determine the "recoverability" of a building and its components. Lots of different names in literature, circularity index, recoverability factor. These are important in formulating a benchmark to compare against. Some are enumerated here but there's lots more:
### Akanbi Recoverability:
$$RF = f \times (1-e^{t-\alpha} - \dfrac{t}{10 \alpha})$$<br>
First part of the service life $$\alpha$$ linearly degrades then as it approaches end of service life, exponentially degrades.<br>

### Arora Cost based Feasibility:
Simple, if the cost of deconstruction is much lower than the cost of buying the component anew and its value as scrap, then worth if to salvage carefully:
$$C_{UM} \ll C_{new} \&  C_{UM} < V_{scrap}$$<br>
$$C_{savings} = C_{UM} - V_{scrap} - C_{new}$$<br>

### O'Grady Circularity Index:

Disassembly index is defined as:<br>
    $$
       DI =  \dfrac{1}{w_{bldg}}\sum_{i=1}^{N} DI_{tool} \times DI_{move} \times w_{component}$$ <br>
The demolition index is defined as:<br>
    $$
        DE = \dfrac{1}{w_{bldg}}\sum_{j=1}^{M} DE_{tool} \times DE_{move} \times w_{component}
    $$ <br>
The resilience index or how many times the component can be reused or its service life <br>
    $$
        R = \dfrac{1}{w_{bldg}}\sum_{k=1}^{P} R \times w_{component}
    $$ <br>
The values $$DI_{tool},DI_{move},DE_{tool},DE_{move},R$$ are constants defined on a Likert scale between 0.2 and 1, which is an abstract measure of circularity.




