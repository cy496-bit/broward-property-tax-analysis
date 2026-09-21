# Broward County Property Tax & Housing Market Analysis

**Question:** Did Florida's 2008 property tax amendment (Amendment 1 — increased homestead exemption + Save Our Homes portability) correlate with a shift in Broward County home price growth, controlling for the national housing market trend?

## Background
This project extends my independent multi-year budget trend analysis of Broward County's finances by testing whether a specific, real property tax policy change left a measurable signature in the local housing market.

## Data
- Broward County home price index: FRED series `ATNHPIUS12011Q` (annual)
- National benchmark: FRED series `USSTHPI` (annual)

## Method
Difference-in-differences regression comparing Broward's year-over-year home price growth to the national trend before and after Florida's Amendment 1 (effective January 2008), testing both a level shift and a change in sensitivity to the national trend. Results were checked against Newey-West (HAC) robust standard errors to rule out autocorrelation as a confound.

## Findings
Controlling for the national housing market trend, this analysis found no statistically significant evidence that Florida's 2008 property tax amendment shifted Broward County's home price growth — neither a level shift (p=0.43, HAC p=0.30) nor a change in sensitivity to the national trend (p=0.74, HAC p=0.80). This null result was consistent across multiple specifications and held under HAC-robust standard errors. The national trend alone was a strong, significant predictor of Broward's growth (coefficient ≈1.75, p<0.05 under both specifications), suggesting Broward behaves as a leveraged version of the broader U.S. housing market rather than showing a distinct, policy-driven signature around 2008.

**Model:** R² = 0.445, N = 50 annual observations.

## Limitations
- Small sample (N=50) and non-normal residuals (Jarque-Bera p<0.001), likely driven by extreme values during the 2008–2011 crash and recovery
- 2008 had many confounding events beyond Amendment 1 (subprime crisis, foreclosure wave, credit freeze) — this analysis identifies correlation, not causation
- A national benchmark is a blunt control; a sharper design would compare Broward/Florida to similar states without a comparable exemption change, or compare homesteaded vs. non-homesteaded properties within Florida directly

## Files
- `broward_property_tax_analysis.ipynb` — main analysis notebook
- `data/` — FRED CSVs (public data)
- `figures/` — exported charts
