## Leveraging Deep Representations of Radiology Reports in Survival Analysis for Predicting Heart Failure Patient Mortality

### Data description

*Note*: All dates are relative days after randomization

#### The subjects table

* `subject_id`: a unique identifier which specifies an individual patient.
* `death_date`: date of death for the given patient as days after randomization.
* `last_followup`: date of the most recent followup as days after randomization.
* `event`: event indicator. True means the subject is decreased.
* `time-to-event`: observable time of a right censored subject. If `event` is True, `time_to_event` is survival days after the last ordering report; otherwise, it is the days between last ordering report and `last_followup`.
* `fold_index`: k-fold for the purpose of cross validation.

#### The reports table

* `subject_id`: a unique identifier which specifies an individual patient.
* `report_id`: a unique identifier which specifies a CT report.
* `ordering_date`: date of the ordering as days after randomization.

#### Reports label sets

* `report_id`: a unique identifier which specifies a CT report.
* `label set 1`: labels generated by ([Pandey et al., 2020]( https://doi.org/10.1371/journal.pone.0236827)).
* `label set 2`: labels generated by [CheXbert](https://github.com/stanfordmlgroup/CheXbert).
* `chexbert hidden`: embeddings by [CheXbert](https://github.com/stanfordmlgroup/CheXbert).
* `biobert hidden`: embeddings by [BioBert](https://github.com/dmis-lab/biobert).
* `bluebert hidden`: embeddings by [BlueBert](https://github.com/ncbi-nlp/bluebert) base.
* `bertbase hidden`: embeddings by Bert base.

### Citation

Lee HG, Schoole E, Al'Aref S, Beecy A, Peng Y. Leveraging Deep Representations of Radiology Reports in SurvivalAnalysis for Predicting Heart Failure Patient Mortality. In NAACL. 2021.

```
@InProceedings{lee2021leveraging,
  author    = {Hyun Gi Lee and Evan Scholle and Subhi Al’Aref and Ashley Beecy and Yifan Peng},
  title     = {Leveraging Deep Representations of Radiology Reports in SurvivalAnalysis for Predicting Heart Failure Patient Mortality},
  booktitle = {NAACL},
  year      = {2021},
}
```


### Acknowledgment

Research reported in this publication was supported by National Library of Medicine - National Institutes of Health (NIH) under award number R00LM013001. It was also supported by National Heart, Lung, and Blood Institute of NIH under award number R01HL1276610. 
This study also received support from NewYork-Presbyterian Hospital (NYPH) and Weill Cornell Medical College (WCMC), including the Clinical and Translational Science Center (CTSC) (UL1TR002384) and Joint Clinical Trials Office (JCTO).
