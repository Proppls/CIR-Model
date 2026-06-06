# 📈 Stochastic Interest Rate Modelling and Yield Curve Reconstruction using the CIR Model

A practical, research-oriented implementation of the
**Cox--Ingersoll--Ross (CIR) interest rate model** for yield curve
reconstruction and prediction.

This project explores a common fixed-income challenge:

> Can an entire yield curve be reconstructed from a single observable
> market rate?

Using historical zero-coupon bond yields, the notebook calibrates a CIR
short-rate model, infers the latent short rate from an observed 3‑month
yield, and generates predictions for longer maturities. The project also
investigates a two-factor extension and evaluates where classical
short-rate models succeed---and where they break down in real markets.

------------------------------------------------------------------------

## 🎯 Project Objectives

-   Clean and preprocess historical yield curve data
-   Calibrate a one-factor CIR model using cross-sectional fitting
-   Infer the latent short rate from an observed 3M yield
-   Reconstruct the full yield curve
-   Compare predicted and actual yields
-   Evaluate model performance using out-of-sample testing
-   Explore a two-factor CIR extension
-   Analyze limitations of stochastic short-rate models

------------------------------------------------------------------------

## 🧠 Key Concepts Covered

### Interest Rates & Yield Curves

-   Zero-coupon bond yields
-   Term structure of interest rates
-   Yield curve dynamics
-   Yield curve inversion

### Stochastic Modelling

-   Mean reversion
-   Diffusion processes
-   Short-rate models
-   Risk-neutral pricing

### CIR Model

The short rate evolves according to:

$$
dr_t = \kappa(\theta-r_t)dt+\sigma\sqrt{r_t}\,dW_t
$$

where:

-   **κ (kappa)** → speed of mean reversion
-   **θ (theta)** → long-run equilibrium rate
-   **σ (sigma)** → volatility parameter
-   **Wₜ** → Brownian motion

The model guarantees non-negative interest rates and provides
closed-form bond pricing formulas.

------------------------------------------------------------------------

## 📂 Notebook Structure

  Section                Description
  ---------------------- -------------------------------------------
  Data Loading           Import and organize historical yield data
  Preprocessing          Handle missing values and duplicate dates
  Exploratory Analysis   Visualize yield curve behaviour
  CIR Theory             Mathematical foundation of the model
  Calibration            Estimate model parameters
  Prediction             Infer short rates and reconstruct curves
  Validation             Manual sanity checks and diagnostics
  Two-Factor Extension   Capture additional curve dynamics
  Critical Analysis      Discuss strengths and weaknesses

------------------------------------------------------------------------

## 📊 Model Workflow

1.  Load historical yield data.
2.  Clean missing observations.
3.  Fit CIR parameters using cross-sectional calibration.
4.  Observe only the 3-month yield.
5.  Recover the latent short rate.
6.  Generate yields for longer maturities.
7.  Compare predictions against actual market observations.
8.  Evaluate performance metrics and model bias.

------------------------------------------------------------------------

## 🔬 Main Findings

### What Worked Well

-   Strong reconstruction of smooth yield curves.
-   High explanatory power for cross-sectional yield shapes.
-   Transparent and interpretable parameter estimates.
-   Fast calibration and prediction pipeline.

### Limitations

-   Volatility often collapses toward zero under cross-sectional
    calibration.
-   Difficulties during highly volatile market regimes.
-   One-factor dynamics struggle to capture twists and curvature
    changes.
-   Real-world yield movements are often driven by multiple latent
    factors.

------------------------------------------------------------------------

## 🚀 Future Improvements

-   Full maximum likelihood estimation (MLE)
-   Kalman filtering for latent state estimation
-   Nelson--Siegel and Svensson benchmarks
-   Multi-factor affine term structure models
-   Regime-switching interest rate dynamics
-   Machine learning hybrid approaches

------------------------------------------------------------------------

## 🛠️ Technologies Used

-   Python
-   NumPy
-   Pandas
-   SciPy
-   Matplotlib
-   Jupyter Notebook

------------------------------------------------------------------------

## 📚 Educational Value

This notebook was designed not only as a modelling exercise but also as
a learning resource. Mathematical derivations, intuition, implementation
details, sanity checks, and model diagnostics are explained alongside
the code to make the workflow easier to follow for students and
researchers entering quantitative finance.

------------------------------------------------------------------------

## 📜 Disclaimer

This project is intended for educational and research purposes. It
should not be considered investment advice or a production-grade
interest rate forecasting system.
