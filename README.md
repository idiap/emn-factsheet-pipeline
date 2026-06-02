<!--
# SPDX-FileCopyrightText: © 2026 Idiap Research Institute <contact@idiap.ch>
# SPDX-License-Identifier: GPL-3.0-only
-->
# The EMN Country Factsheets Structured Dataset

Authors: David Alonso del Barrio and Daniel Gatica-Perez

## 1. Overview

This repository provides a representative code pipeline illustrating the extraction and harmonization methodology used to generate the EMN Country Factsheets Structured Dataset. The notebooks in this repository demonstrate our automated extraction pipeline using a small sample of 5 PDF files in 2022 and 2018. The emn_22_cleaned.csv and emn_18_cleaned.csv files included here represent the cleaned output for these 5 samples after the manual cleaning.

**Full Dataset: The final harmonized dataset (2012–2024) is available via Zenodo: <https://doi.org/10.34777/fxzr-nc56>.**

## 2. Reference Paper

David Alonso del Barrio and Daniel Gatica-Perez, The EMN Country Factsheets Structured Dataset, Proceedings of the 35th ACM International Conference on Information and Knowledge Management, 2026. https://doi.org/10.1145/3799682.3840177

## 3. Repository Structure

```
.
├── data
│   ├── 2018
│   │   ├── final
│   │   └── sample
│   └── 2022
│       ├── final
│       └── sample
├── LICENSES
│   ├── CC-BY-4.0.txt
│   └── GPL-3.0-only.txt
├── 01_standard_extraction_2022.ipynb
├── 02_ocr_extraction_2018.ipynb
├── 03_harmonization_pipeline.ipynb
├── environment.yml
├── README.md
└── REUSE.toml
```

## 4. Methodology: Handling Data Heterogeneity

In this repository, we present two examples of pipeline extraction. The first one is from 2022 `01_standard_extraction_2022.ipynb`, which is the most common scenario, where text can be extracted directly from PDFs. The second one is from 2018 `02_ocr_extraction_2018.ipynb`, where the PDF text was an image and required the implementation of an OCR layer. We've included a couple of pdfs examples to illustrate the text extraction process, but a significant amount of manual work followed, reviewing the extraction and curating the text. The dataset was checked case by case three times to eliminate any typos. Finally,in `03_harmonization_pipeline.ipynb` we show how the integration and harmonization of data from different years (in this case 2022 and 2018) is done to arrive at the final version of our dataset.

## 5. Getting Started

To replicate the extraction pipeline on your local machine:

1. Clone the repository.
2. Setup the environment:

    ```bash
    conda env create -f environment.yml
    conda activate emn_processing
    python -m ipykernel install --user --name=emn_processing --display-name "Python (emn_processing)"
    ```

3. Run the notebooks and select "Python (emn_processing)" from the Kernel menu in Jupyter.

    ```bash
    jupyter notebook
    ```

## 6. Acknowledgment (ELIAS)

This work was supported by the ELIAS project, funded by the European Commission (Grant 101120237). We would like to thank the European Migration Network (EMN) for providing us with factsheets from previous years that are no longer publicly available.

## 7. License and Copyright

This project adheres to the [REUSE Specification](https://reuse.software/).

- **Code:** All source code and notebooks are licensed under the **GNU General Public License v3.0 (GPL-3.0-only)**. You can find the full license text in the `LICENSES/GPL-3.0-only.txt` file.
- **Data:** The datasets and sample factsheets are licensed under the **Creative Commons Attribution 4.0 International (CC-BY-4.0)** license.

For detailed copyright information on specific files, please refer to the `REUSE.toml` file in the root directory.
