# Project Guidelines: Astrostatistics

## Objective
The mini–project is an open–ended assignment where you apply the statistical tools learned during the semester to a **real or simulated astronomical dataset**.  
You may choose your own topic (recommended), or select one from the suggested list below.

The goal is to demonstrate your ability to:
- Formulate a clear astrophysical or data–driven question  
- Apply appropriate statistical and computational techniques  
- Quantify uncertainty and interpret the results in a scientific context  

---

## Deliverables
Each group must submit **one single project**, consisting of:

1. **A report (in PDF format)**  
   - You may export it directly from a Jupyter notebook.  
   - It should include both the **code** and the **results** (figures, tables, discussion).  
   - Recommended length: 4–6 pages.  

2. **An oral presentation**  
   - 10 minutes per person (e.g. 20 min for a group of two).  
   - Present your motivation, dataset, methods, main results, and interpretation.  

3. **Validation deadline:**  
   Each group must **validate the topic and project plan with the instructor by November 18**.

---

## Evaluation (100 points)

| Criterion | Points |
|------------|---------|
| Scientific motivation and formulation | 20 |
| Correct and justified use of statistical methods | 25 |
| Quality of data handling and code reproducibility | 20 |
| Analysis, interpretation, and physical insight | 25 |
| Clarity and presentation (written + oral) | 10 |

---

## Mandatory Components

Each project must include:

1. **Estimation**  
   At least one parameter estimation or inference task (e.g. method of moments, MLE, regression, Bayesian estimation).

2. **Error Treatment**  
   Quantify uncertainties using one or more of the following:  
   - Monte Carlo (MC) simulation  
   - Jackknife resampling  
   - Bootstrap method  

3. **Statistical Framework**  
   Choose **either** a Bayesian or Frequentist approach — and justify your choice.

4. **Data Pre–treatment**  
   Clearly describe any data filtering, cuts, or cleaning steps, and **explain the motivation** for each (e.g. signal–to–noise threshold, redshift range, quality flags, etc.).

5. **Optional Advanced Elements** (choose ≥ 1 if feasible):  
   - Hypothesis testing (e.g. model consistency or significance test)  
   - MCMC or posterior sampling  
   - Model selection or information criteria (AIC, BIC, DIC)  
   - Non-Gaussian likelihoods or correlated errors  
   - Cross-validation or predictive performance analysis  

Clear visualizations (histograms, correlations, likelihood/posterior plots) are strongly encouraged.

---

## Scope
Each project must involve at least one **real or simulated astronomical dataset**,  
for example from **JWST**, **SDSS**, **DESI**, **Gaia**, **TESS**, **LSST simulations**, or a small **FITS** file that you generate.

Typical steps:
1. Define a clear astrophysical or statistical question.  
2. Retrieve and pre-treat the data (apply motivated cuts).  
3. Model the relevant quantity (e.g. luminosity, redshift, photometric relation).  
4. Estimate model parameters.  
5. Quantify uncertainties and discuss robustness.  
6. Compare alternative methods or models when appropriate.

---

## Suggested Topics

You can propose your own idea or adapt one of the examples below.

### 1. Supernova Cosmology
Use the [Pantheon+SH0ES sample](https://github.com/PantheonPlusSH0ES/DataRelease) of Type Ia supernovae:
- Fit the Hubble relation  
  \( \mu(z) = 5\log_{10}[d_L(z;H_0,\Omega_m,w_0,w_a)] + 25 \)  
  under a chosen cosmological model (\(\Lambda\)CDM, wCDM, CPL).  
- Estimate parameters and uncertainties via MLE or Bayesian inference.  
- Assess bias and variance using bootstrap or Monte Carlo.  
- Optionally, combine with **DESI BAO** to test joint cosmological constraints.

### 2. Exoplanet Transit Simulation
Simulate a light curve of a transiting exoplanet:
- Add Gaussian and systematic noise.  
- Fit for depth, period, and mid-transit time using least-squares or MLE.  
- Quantify errors via bootstrap or MCMC.  
- Compare models with and without systematics.

### 3. Stellar Photometry and Color–Magnitude Relations
Using Gaia or SDSS/DESI photometric data:
- Fit a main-sequence relation \( M_G = a(B\!-\!V) + b \).  
- Estimate uncertainties and assess outlier impact via jackknife or bootstrap.  
- Discuss residuals, bias, and the nature of photometric errors.

### 4. Galaxy Scaling Relations
Use a public galaxy catalog (e.g. [SDSS](https://www.sdss.org/dr17/) or [DESI](https://data.desi.lbl.gov/doc/)) to explore:
- The Tully–Fisher or Faber–Jackson relation.  
- Frequentist vs Bayesian regression.  
- Model comparison (AIC/BIC) and uncertainty propagation.

### 5. Power-Law Distributions in Astrophysics
Analyse simulated data drawn from a power-law (e.g. luminosity or mass function):
- Estimate the index via MLE and compare to MoM.  
- Evaluate bias and variance via Monte Carlo.  
- Test model truncation or completeness via hypothesis testing.

### 6. JWST Photometry or Spectroscopy
Retrieve JWST public data (NIRCam or NIRSpec) from [MAST](https://mast.stsci.edu) using `astroquery.mast`:
- Extract photometric fluxes or spectra for a set of galaxies or stars.  
- Apply motivated quality cuts (S/N, wavelength range, target selection).  
- Fit a spectral energy distribution (SED) or emission-line model.  
- Propagate flux uncertainties via bootstrap or MC sampling.  
- Optionally, compare JWST results with SDSS or HST measurements.

### 7. Cosmic Microwave Background (CMB) Fluctuations
Using a small HEALPix map or a 1D simulation:
- Estimate the angular power spectrum $C_\ell $.  
- Quantify uncertainty from finite-sky sampling via bootstrap.  
- Compare frequentist and Bayesian inferences of cosmological parameters.

---

## Possible Data Sources
You may use **any publicly available astronomical data**, or generate simulated data that mimic a real instrument.  
Below are recommended archives and datasets suitable for small–scale projects.

- **JWST (James Webb Space Telescope):**  
  Public data available through the [MAST archive](https://mast.stsci.edu)  
  or via `astroquery.mast`.  
  You can retrieve **imaging** (NIRCam, MIRI) or **spectroscopic** data (NIRSpec, NIRISS).  
  Typical uses: galaxy photometry, emission-line analysis, SED fitting.

- **Pantheon+SH0ES Supernovae:**  
  [https://github.com/PantheonPlusSH0ES/DataRelease](https://github.com/PantheonPlusSH0ES/DataRelease) —  
  distance moduli, redshifts, and covariance matrices for Type Ia SNe.

- **Gaia DR3:**  
  [https://gea.esac.esa.int/archive/](https://gea.esac.esa.int/archive/) —  
  stellar positions, parallaxes, and photometry.

- **SDSS or DESI:**  
  - SDSS: [https://www.sdss.org/dr17/](https://www.sdss.org/dr17/)  
  - DESI: [https://data.desi.lbl.gov/doc/](https://data.desi.lbl.gov/doc/)  
  Galaxy spectra, redshifts, and photometric catalogs.

- **NASA Exoplanet Archive:**  
  [https://exoplanetarchive.ipac.caltech.edu/](https://exoplanetarchive.ipac.caltech.edu/) —  
  stellar, planetary, and orbital parameters.

- **TESS:**  
  Accessible through `astroquery.mast` or [https://mast.stsci.edu](https://mast.stsci.edu) —  
  light curves for transiting exoplanets and variable stars.

- **Simulated data:**  
  Generate your own datasets using `numpy.random`, `scipy.stats`, or simple cosmological or instrumental models.

---

## Proposal (mandatory validation)
If you design your own project, submit a short paragraph (max 200 words) describing:
- The astronomical question you want to address  
- The dataset or simulation you plan to use  
- The statistical methods you will apply  
- The planned data cuts or pre-treatment  

**Each project proposal must be validated with the instructor by November 18.**

---

## Recommended Structure
1. **Introduction:** astrophysical context and motivation  
2. **Data and Methods:** dataset, pre-treatment, and statistical tools  
3. **Results:** main figures and quantitative outcomes  
4. **Error & Uncertainty Analysis:** how uncertainties were estimated and validated  
5. **Discussion:** interpretation, limitations, and robustness  
6. **Conclusion:** summary and perspectives  

---

## Notes
- Work in **groups of two or three** (indicate all names).  
- Collaboration on ideas is encouraged, but **all code and text must be original**.  
- Plagiarism or reuse of others’ notebooks will result in a failing grade.
