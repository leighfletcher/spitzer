# Spitzer Uranus Chemical Models

In our analysis of Spitzer spectroscopy of Uranus, we undertook a detailed iterative intercomparison between the forward modelled spectra (Orton) and the photochemical model, KINETICS (Moses).  This repository contains a subset of the chemical models used for testing, plus some notes on their applicability.

Full publications:  Orton et al. (2014), Icarus
Part 1:  https://doi.org/10.1016/j.icarus.2014.07.010
Part 2:  https://doi.org/10.1016/j.icarus.2014.07.012

## Noted on Datafiles

* These data files correspond to Fig. 4 of the "chemistry" paper (and Table 2), where we searched for the optimum solution between varying the tropopause methane abundance and varying a vertically-uniform Kzz value (cm^2/s).

* The primary directories have the following naming convention: `ch4_XXppm_kzz_YYYY_ZZZZ`, where `XX` is the tropopause methane abundance in ppm (ranging from 10-70 ppm), `YYYY` is the lower bound for the Kzz tested, and `ZZZZ` is the upper bound for the Kzz.  Note that the Kzz grid is not uniform, as we attempted to narrow in on the optimal solution.  In Table 2 of Orton et al. (2014), the reported best fit for the nominal temperature structure had CH4 = 16 (+2,-1) ppm and Kzz = 2430 (+100,-190) cm2/s.

* We tweaked some of the chemistry in the model to favour high C2H2/C2H6 ratios, which is needed for Uranus.  That chemistry does not work well for the other giant planets, but these models should help reveal how things change with Kzz magnitude, Kzz slope, and CH4 at the tropopause.  This series has a relatively high CH4 abundance and various sloped Kzz.

* Keep in mind that we assumed a fixed tropopause CH4 value at the base of the model (deeper in the troposphere) for convenience, and the actual tropospheric abundance will be much greater. So if you're running forward models that need CH4, make sure you use something sensible for the tropospheric profile.  

* There is also a second directory called `slope_tests`, which varies the slope of the Kzz profile as another means on converging on the best fit (see Table 2 and Fig. 11 of the Orton et al., 2014 paper).

## Notes on the Format

Each file contains the atmospheric pressure grid (bar) at the top, followed by the abundances (as volume mixing ratios, or mole fractions) for each species in the chemical model.  For example, a basic forward model requires H2, He, CH4, C2H2 and C2H6 to start reproducing the spectrum, but additional species may be needed for higher spectral resolutions.
