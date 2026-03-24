# BNCI 2015-008 Center Speller P300 dataset

BNCI 2015-008 Center Speller P300 dataset.

## Dataset Overview

- **Code**: BNCI2015-008
- **Paradigm**: p300
- **DOI**: 10.1088/1741-2560/8/6/066003
- **Subjects**: 13
- **Sessions per subject**: 1
- **Events**: Target=1, NonTarget=2
- **Trial interval**: [0, 1.0] s
- **Runs per session**: 2
- **File format**: gdf
- **Data preprocessed**: True

## Acquisition

- **Sampling rate**: 250.0 Hz
- **Number of channels**: 63
- **Channel types**: eeg=63
- **Channel names**: Fp2, AF3, AF4, Fz, F1, F2, F3, F4, F5, F6, F7, F8, F9, F10, FCz, FC1, FC2, FC3, FC4, FC5, FC6, T7, T8, Cz, C1, C2, C3, C4, C5, C6, TP7, TP8, CPz, CP1, CP2, CP3, CP4, CP5, CP6, Pz, P1, P2, P3, P4, P5, P6, P7, P8, P9, P10, POz, PO3, PO4, PO7, PO8, PO9, PO10, Oz, O1, O2, Iz, I1, I2
- **Montage**: 10-10
- **Hardware**: Brain Products actiCAP
- **Reference**: left mastoid
- **Ground**: forehead
- **Sensor type**: active electrode
- **Line frequency**: 50.0 Hz
- **Online filters**: 0.016-250 Hz bandpass
- **Impedance threshold**: 20.0 kOhm
- **Cap manufacturer**: Brain Products

## Participants

- **Number of subjects**: 13
- **Health status**: patients
- **Clinical population**: Healthy
- **Age**: mean=27.0, min=16.0, max=45.0
- **Gender distribution**: male=8, female=5
- **Handedness**: {'right': 12, 'left': 1}
- **BCI experience**: naive
- **Species**: human

## Experimental Protocol

- **Paradigm**: p300
- **Number of classes**: 2
- **Class labels**: Target, NonTarget
- **Trial duration**: 30.0 s
- **Study design**: Two-stage visual speller using covert spatial attention and non-spatial feature attention (color and form). Three speller variants tested: Hex-o-Spell (6 discs with size enhancement and unique colors), Cake Speller (6 triangular faces with unique colors), Center Speller (sequential presentation of 6 geometric shapes with unique colors and forms).
- **Feedback type**: none
- **Stimulus type**: visual_flash
- **Stimulus modalities**: visual
- **Primary modality**: visual
- **Synchronicity**: synchronous
- **Mode**: online
- **Training/test split**: True
- **Instructions**: Participants had to strictly fixate the center of the screen and covertly attend to the target symbol. They were instructed to silently count the number of intensifications of the target symbol.

## HED Event Annotations

Schema: HED 8.4.0 | Browse: https://www.hedtags.org/hed-schema-browser

```
  Target
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Target

  NonTarget
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Non-target

```
## Paradigm-Specific Parameters

- **Detected paradigm**: p300
- **Number of targets**: 30
- **Number of repetitions**: 10
- **Stimulus onset asynchrony**: 200.0 ms

## Data Structure

- **Trials**: 60 intensifications per stage (10 sequences × 6 elements)
- **Trials context**: per_stage

## Preprocessing

- **Data state**: filtered
- **Preprocessing applied**: True
- **Steps**: downsampling, lowpass filter, baseline correction
- **Highpass filter**: 0.016 Hz
- **Lowpass filter**: 49.0 Hz
- **Bandpass filter**: {'low_cutoff_hz': 0.016, 'high_cutoff_hz': 250.0}
- **Filter type**: Chebyshev
- **Re-reference**: linked mastoids
- **Downsampled to**: 250.0 Hz
- **Epoch window**: [-200.0, 800.0]
- **Notes**: For offline ERP analysis: downsampled to 250 Hz, lowpass filtered below 49 Hz using Chebyshev filter (passbands/stopbands: 42/49 Hz). For online classification: downsampled to 100 Hz, no software filter applied. Baseline correction using -200 ms prestimulus interval.

## Signal Processing

- **Classifiers**: LDA, SLDA
- **Feature extraction**: ERP components, P300, P3
- **Spatial filters**: shrinkage covariance

## Cross-Validation

- **Method**: calibration-test split
- **Evaluation type**: within_session

## Performance (Original Study)

- **Accuracy**: 92.0%
- **Hex O Spell Accuracy**: 88.0
- **Cake Speller Accuracy**: 90.0
- **Center Speller Accuracy**: 97.0
- **Communication Rate Symbols Per Min**: 2.3

## BCI Application

- **Applications**: speller, communication
- **Environment**: laboratory
- **Online feedback**: True

## Tags

- **Pathology**: Healthy
- **Modality**: Visual
- **Type**: ERP, P300

## Documentation

- **DOI**: 10.1088/1741-2560/8/6/066003
- **License**: CC-BY-NC-ND-4.0
- **Investigators**: M S Treder, N M Schmidt, B Blankertz
- **Institution**: Berlin Institute of Technology
- **Department**: Machine Learning Laboratory
- **Country**: Germany
- **Repository**: GitHub
- **Data URL**: https://github.com/bbci/bbci_public/blob/master/doc/index.markdown
- **Publication year**: 2011
- **Keywords**: P300, ERP, BCI, speller, covert attention, feature attention, gaze-independent

## References

Treder, M. S., Schmidt, N. M., & Blankertz, B. (2011). Gaze-independent brain-computer interfaces based on covert attention and feature attention. Journal of Neural Engineering, 8(6), 066003. https://doi.org/10.1088/1741-2560/8/6/066003

Notes

.. versionadded:: 1.2.0
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Hochenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

---
Generated by MOABB 1.5.0 (Mother of All BCI Benchmarks)
https://github.com/NeuroTechX/moabb
