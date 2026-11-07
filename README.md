# AO School — Adaptive Optics simulation labs

Hands-on labs for learning adaptive optics (AO) by simulation:

- **Part 1 — `aotools_lab.ipynb`** (entry point of this repo): Fourier optics and image formation, Zernike aberrations and Strehl ratio, turbulence parameters ($r_0$, seeing, $C_n^2$, $\tau_0$, $\theta_0$), phase-screen generation (FFT screens, sub-harmonics, infinite phase screens) validated against the Noll (1976) Zernike sequence, and imaging through turbulence (instantaneous vs long-exposure PSF).
- **Part 2 — `soapy_lab_part2_short.ipynb`**: end-to-end AO loop with [soapy](https://github.com/AOtools/soapy) — telescope, atmosphere, Shack–Hartmann WFS, DM, calibration (interaction matrix), closed loop. See also `assets/ORP_AO_School_How_To.ipynb` and `assets/OOPAO_tutorial.pdf` for the OOPAO alternative.

## Quick start in Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/GillesOrban/ao_school/blob/main/aotools_lab.ipynb)

Then run the notebook's first code cell once (it clones this repo and installs the dependencies — Colab already has numpy/scipy/matplotlib):

```python
!git clone https://github.com/GillesOrban/ao_school.git
%cd ao_school
!pip install -r requirements.txt   # only non-preinstalled deps
```

## Run locally

```bash
conda create -n aosim python=3.12
conda activate aosim
pip install -r requirements.txt matplotlib jupyter
jupyter lab        # then open aotools_lab.ipynb
```

Run the notebook with the **repo root as working directory**: `noll.fits` (Noll 1976 Zernike variances, loaded in section 4) sits next to the notebook.

## Repository contents

| Path | What it is |
|---|---|
| `aotools_lab.ipynb` | Part 1 lab — main entry point |
| `soapy_lab_part2_short.ipynb` | Part 2 lab — end-to-end AO loop with soapy |
| `noll.fits` | Noll (1976) Zernike variance sequence, used in section 4 |
| `requirements.txt` | Python deps: `aotools`, `astropy`, `photutils`, `pyfftw`, `numba` |

## References

- `aotools` docs: https://aotools.readthedocs.io — package: https://github.com/aotools/aotools
- `soapy`: https://github.com/AOtools/soapy — docs: http://soapy.readthedocs.io
- Noll (1976), JOSA 66, 207; Kolmogorov (1941); von Kármán (1948); Fried (1966), JOSA 56, 1372
- Textbooks: Hardy (1998), *Adaptive Optics for Astronomical Telescopes*; Roddier (1999), *Adaptive Optics in Astronomy*
