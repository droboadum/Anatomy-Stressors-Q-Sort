# Anatomy Stressors Q-Sort (HTMLQ Implementation)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17401677.svg)](https://doi.org/10.5281/zenodo.17401677)

This repository contains the full HTMLQ-based Q-sort application developed by **Oheneba Boadum (2025)** for the study:

**"Perceptions of Anatomy-Related Stressors Among First-Year DO Students"**

The tool enables participants to sort **44 anatomy-related stressor statements** into a forced distribution from **–4 (least characteristic)** to **+4 (most characteristic)**.  
It integrates seamlessly with **Qualtrics** for participant identification (PID), demographic linkage, and return flow after sorting.

---

## Features
- Fully browser-based Q-sort (no installation required)
- Customizable `statements.csv` for your own research topics
- Redirects to Qualtrics for pre/post-survey items
- Mobile-responsive interface
- Hosted easily via **GitHub Pages**

---

## Reuse and Adaptation

Researchers may adapt the *technical framework* (HTMLQ structure and Qualtrics integration) for their own Q-sort projects by replacing the study-specific statements with their own.

Please retain the citation below if you use or modify this framework.  
The specific anatomy-related statements and survey text remain the intellectual property of the original author.

---

## Citation

If you use or adapt this repository, please cite:

> **Boadum, O.** (2025). *Anatomy Stressors Q-Sort (HTMLQ implementation)* [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.17401677

---

## About the Study

This project was developed as part of an investigation into **anatomy-related stressors among first-year osteopathic medical students**, employing **Q-methodology** to explore subjective perceptions of learning stressors reported by Boadum et al. (2024).

The web app was built using **HTMLQ**, customized for integration with institutional Qualtrics survey flow, and deployed via GitHub Pages.

---

## ⚠️ Known issue in v1.0 (fixed in v1.1)

**Version 1.0 contains a column-mapping error.** The sorting page draws the columns on screen in the order +1, +2, +3, +4 (upper row) and 0, −1, −2, −3, −4 (lower row), but v1.0 assigned each column's capacity and exported score by its *on-screen position* rather than by its label. As a result:

1. **Column capacities on the positive side were reversed.** Columns +1 to +4 accepted 3, 4, 5, 6 cards instead of 6, 5, 4, 3. The negative side and 0 were correct.
2. **Exported scores did not match the column labels.** Each column exported the following score:

| Column label (as displayed) | +1 | +2 | +3 | +4 | 0 | −1 | −2 | −3 | −4 |
|---|---|---|---|---|---|---|---|---|---|
| Score exported in v1.0 | −4 | −3 | −2 | −1 | 0 | +1 | +2 | +3 | +4 |

**If you collected data with v1.0**, the mapping is one-to-one, so the placements participants chose can be recovered exactly by recoding exported scores:

| Exported score (v1.0) | −4 | −3 | −2 | −1 | 0 | +1 | +2 | +3 | +4 |
|---|---|---|---|---|---|---|---|---|---|
| Column actually chosen | +1 | +2 | +3 | +4 | 0 | −1 | −2 | −3 | −4 |

Note that participants who used v1.0 sorted into the asymmetric grid described in point 1; this cannot be recoded and should be reported.

**v1.1** uses each column's own label index for capacities and exported scores. It was verified in a browser by completing a full sort and confirming that every exported score matches the column label and that each column accepts exactly its intended number of cards.

**Recommendation for anyone adapting this tool:** before collecting data, complete a test sort with known placements and check the exported values against the column labels.

## Changelog

- **v1.1** — Fixed column capacity and score mapping (columns are now indexed by label, not on-screen position). Added this notice.
- **v1.0** — Initial public release (October 2025). Contains the column-mapping error described above.

---

## Contact

**Author:**  
Dr. Oheneba Boadum  
Assistant Professor, Clinical Anatomy & Medical Education  
Sam Houston State University College of Osteopathic Medicine  
droboadum@gmail.com  

---
