## Leveraging Deep Representations of Radiology Reports in Survival Analysis for Predicting Heart Failure Patient Mortality

### Data Description

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

### Code Description

#### Install Dependencies

The package list is available in requirements.txt. Run the command below to install the packages:

```sh
pip install -r requirements.txt
```

#### Commands
After the dependency installation, train.py can be used to perform the experiments. There are five required arguments for the command:
* ```--timeline```: path to the file containing the subjects table
* ```--mapping```: path to the file containing the reports table
* ```--feature_path```: path to the file containing features
* ```--model```: model specification - coxph, deepsurv, or lstm_cox
* ```--feature_set```: feature specification - label, hidden, or hidden_sequence

```sh
python train.py --timeline {file path} --mapping {file path} --feature_path {file path} \
  --model {coxph, deepsurv, lstm_cox} --feature_set {label, hidden, hidden_sequence}
```

### How to cite this work

Lee HG, Schoole E, Al'Aref S, Beecy A, Peng Y. [Leveraging Deep Representations of Radiology Reports in SurvivalAnalysis for Predicting Heart Failure Patient Mortality](https://www.aclweb.org/anthology/2021.naacl-main.358). In NAACL. 2021;4533-4538.

```
@InProceedings{lee2021leveraging,
    title = "Leveraging Deep Representations of Radiology Reports in Survival Analysis for Predicting Heart Failure Patient Mortality",
    author = "Lee, Hyun Gi  and
      Sholle, Evan  and
      Beecy, Ashley  and
      Al{'}Aref, Subhi  and
      Peng, Yifan",
    booktitle = "Proceedings of the 2021 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies",
    month = jun,
    year = "2021",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2021.naacl-main.358",
    doi = "10.18653/v1/2021.naacl-main.358",
    pages = "4533--4538",
}
```

### Acknowledgment

Research reported in this publication was supported by National Library of Medicine - National Institutes of Health (NIH) under award number R00LM013001. It was also supported by National Heart, Lung, and Blood Institute of NIH under award number R01HL1276610. 
This study also received support from NewYork-Presbyterian Hospital (NYPH) and Weill Cornell Medical College (WCMC), including the Clinical and Translational Science Center (CTSC) (UL1TR002384) and Joint Clinical Trials Office (JCTO).
