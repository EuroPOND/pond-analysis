# pond-analysis
A repository for comparative analyses across EuroPOND models.

## Planned analyses
- [Model Staging](#model-staging) using [TADPOLE](http://tadpole.grand-challenge.org) data

## EuroPOND models
|   | Links | Public | Description | Input data type |
| - | ----- | ------ | ----------- | --------------- |
| EBM | [github](https://github.com/ucl-mig/ebm) | Yes | Event-based Model | Scalar biomarker values; cross-sectional |
| pyEBM | [github](https://github.com/88vikram/pyebm) | Yes | Toolbox for event-based models (EBM and dEBM) | Scalar biomarker values; cross-sectional |
| Deformetrica | [gitlab](https://gitlab.icm-institute.org/alexandre_bone/pydeformetrica) <br> [website](http://www.deformetrica.org/) <br > [documentation](https://gitlab.icm-institute.org/alexandre_bone/pydeformetrica/wikis/home)| Yes | Morphometry software. Works with image or mesh data. Can estimate anatomical registrations, regressions, cross-sectional & longitudinal atlases.  |  |
| LeasPy | [gitlab](https://gitlab.icm-institute.org/aramislab/LEASPy) | No | Learns the spatiotemporal patterns from longitudinal scalar measurements. | Scalar biomarker values; longitudinal |
| Clinica | [gitlab](http://gitlab.icm-institute.org:aramislab/clinica) <br> [website](http://clinica.run/) | Yes | Clinica is a software platform for clinical research studies involving patients with neurological and psychiatric diseases and the acquistion of multimodal data (neuroimaging, clinical and cognitive evaluations, genetics...), most often with longitudinal follow-up. |  |
| DEM | TBA | No | Differential Equation Model | Scalar biomarker values; longitudinal |
| SuStaIn | TBA | No | Subtype and Stage Inference | Scalar biomarker values; cross-sectional |
| DIVE | [github](https://github.com/EuroPOND/dive) <br /> (forked from [Raz](https://github.com/mrazvan22/dive)) | Yes | Vertex Clustering Model | Images; longitudinal |
| Gaussian process regression model | [github](https://github.com/EuroPOND/GP_progression_model) <br /> (forked from [Marco](https://github.com/marcolorenzi/GP_progression_model)) | Yes | Gaussian Processes for temporal analysis of clinical data | Scalar biomarker values; cross-sectional or longitudinal |

Additional models of interest:
- Ageing trajectories:
  - Leon's [Multi-Task Learning](https://github.com/LeonAksman/bayes-mtl-traj) trajectory model
  - Eline's mixed (effects) models
- Off-the-shelf machine learning classifiers:
  - SVM, MKL, etc.
  - Point: for comparison of clinical classification (AUC)

## # Model Staging
### Discussion in Paris
- Stratified cross-validation. Sets defined by one person, then shared.
  - Probably don't need to balance/stratify, due to TADPOLE numbers
- Evaluation measures:
  - Appropriate [TADPOLE](http://tadpole.grand-challenge.org) metrics: AUC for clinical classification, too.
  - (Regression) Correlations between model stages
  - Hold-out longitudinal consistency:
    - "Test" data: N (=200?) individuals having 2x2 timepoints (two disease staging opportunities) each
    - Preferably not those having more than 4, so as not to reduce the data for unsupervised spatiotemporal models (Inserm)
    - See [python notebook](prep/TADPOLE-Numbers.ipynb) for details

