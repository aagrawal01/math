# HorizonMath `box_integral_b6_1` — executable symbolic candidate

File: `horizonmath_b6_proposed_solution.py`

This standalone Python file exports `proposed_solution()` and embeds the complete finite coefficient tables from the manuscript *Hyperclosure of the Odd Six-Dimensional Box Integrals*. Only `mpmath` is required. It uses finite arithmetic, algebraic numbers, logarithms, inverse trigonometric functions, and classical dilogarithms/trilogarithms. It does not perform numerical quadrature, explicitly sum an infinite series, call root-finding, or hard-code the benchmark decimal answer.

Run with:

```
python horizonmath_b6_proposed_solution.py
```

The computed result at 100-digit display precision is:

```
1.388574084457347842530254073030788815910945088782207029758933139762637896937682885791843577864515748
```

The digits match HorizonMath's published reference string to its full displayed precision. The function uses extra guard digits internally because the construction involves algebraic removable singularities and substantial cancellation. A straightforward evaluation can take several minutes.

## Mathematical formulation

The code implements the formula

`B6(1) = B6(-5)/112 - 67 B6(-7)/168 - 133 D/42 + 5 L + (60/7) theta - 15 pi/7 + sqrt(6)/7`

where `B6(-5)` is the manuscript's 3,115-term finite classical-polylogarithmic certificate, `B6(-7)` and `D` are finite dilogarithmic expressions, and the logarithmic/polylogarithmic branches are continued along the manuscript's specified physical curve arc. The embedded integer monodromy data encode that continuation; they are not a numerical integral.

## Validation status and limitation

- Exact arithmetic has been used separately to check the printed 13,824-coordinate tensor identity.
- A numerical regularized audit of all 1,677 rational maps' prescribed `1`-fibers passed after treating removable singularities correctly.
- This standalone code returned the published numerical benchmark digits at 100-digit precision.
- These checks do **not** replace independent specialist validation of the manuscript's proof and algebraic geometric identities. HorizonMath's own compliance-review step has not been run here; compatibility with every procedural check in its current grading environment cannot be guaranteed.

Suggested contribution: share the Python file together with the complete manuscript PDF, and clearly characterize the evaluation as a proposed solution pending independent proof review.
