# AO School — Adaptive Optics simulation labs

Hands-on labs for learning adaptive optics (AO) by simulation using the `aotools` and the `soapy` Python packages:

- **Part 1 — `aotools_lab.ipynb`** (entry point of this repo): Fourier optics and image formation, Zernike aberrations and Strehl ratio, turbulence parameters ($r_0$, seeing, $C_n^2$, $\tau_0$, $\theta_0$), phase-screen generation (FFT screens, sub-harmonics, infinite phase screens) validated against the Noll (1976) Zernike sequence, and imaging through turbulence (instantaneous vs long-exposure PSF).
- **Part 2 — `soapy_lab.ipynb`**: end-to-end AO loop with [soapy](https://github.com/AOtools/soapy) — telescope, atmosphere, Shack–Hartmann WFS, DM, calibration (interaction matrix), closed loop.

The package and documentation can be found here
- `aotools` package: https://github.com/aotools/ — docs: https://aotools.readthedocs.io aotools
- `soapy` package: https://github.com/AOtools/soapy — docs: http://soapy.readthedocs.io

## Quick start in Colab

For the `aotools_lab.ipynb` notebook:
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/GillesOrban/ao_school/blob/main/aotools_lab.ipynb)

For the `soapy_lab.ipynb` notebook:
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/GillesOrban/ao_school/blob/main/soapy_lab.ipynb)

Then run the notebook's first code cell once (it clones this repo and installs the dependencies — Colab already has numpy/scipy/matplotlib). E.g. for the `aotools_lab.ipynb` notebook
```python
!git clone https://github.com/GillesOrban/ao_school.git
%cd ao_school
!pip install -r requirements.txt   # only non-preinstalled deps
```

## Run locally

To run and work with this notebook, you need a Python environment, which includes `aotools` and `soapy`, as well as their dependencies.

If you don't have a Python environment installed, we recommend a dedicated conda environment (install [Miniconda](https://www.anaconda.com/download) if you don't have it).
Then you can create your environment, e.g. aosim:

```bash
conda create -n aosim python=3.12
conda activate aosim
pip install -r requirements.txt matplotlib jupyter
jupyter lab        # then open aotools_lab.ipynb
```

For the installation of soapy, go to the install webpage:
https://soapy.readthedocs.io/en/latest/install.html


Run the notebooks with the **repo root as working directory**: `noll.fits` (Noll 1976 Zernike variances, loaded in section 4) sits next to the notebook.

## Repository contents

| Path | What it is |
|---|---|
| `aotools_lab.ipynb` | Part 1 lab — main entry point |
| `soapy_lab.ipynb` | Part 2 lab — end-to-end AO loop with soapy |
| `noll.fits` | Noll (1976) Zernike variance sequence, used in section 4 |
| `requirements.txt` | Python deps: `aotools`, `astropy`, `photutils`, `pyfftw`, `numba` |
| `conf/` | Directory containing configuration files for Soapy |
| `videos/` | Directory containing as set of videos generated with the `soapy_lab.ipynb` |


