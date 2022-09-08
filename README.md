# Multi-Task-Multi-Expert

This repo provides a benchmark data processing and evaluation for [Multi-task and Multi-expert Learning Challenge] from Noah's Ark Recommendation & Search Lab.

### Data
[AliExpress Dataset](https://tianchi.aliyun.com/dataset/dataDetail?dataId=74690): AliExpress dataset collects user logs from real-world traffic in AliExpress. It contains two tasks -- CTR prediction and CVR prediction.

To process the data, put the original data to ```./data``` and run
```
python process_aliexpress.py --dataset_name NL
```

### Evaluation
AUC score for CTR and CVR respectively.


### Baseline Results
We train baseline models on each of the four datasets (NL, ES, FR, US), early stopping by CVR. We conduct experiments three times and report the results as follows. For details of the baseline implementation, please check [this](https://github.com/easezyc/Multitask-Recommendation-Library) nice multi-task library.

| Model              |        | NL     |        |        | ES     |        |        | FR     |        |
|--------------------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|                    | CTR    | CVR    | CTCVR  | CTR    | CVR    | CTCVR  | CTR    | CVR    | CTCVR  |
| Single model (DNN) | 0.7203 | 0.7815 | 0.8556 | 0.7252 | 0.8141 | 0.8832 | 0.7174 | 0.8071 | 0.8702 |
| MMOE               | 0.7195 | 0.787  | 0.8574 | 0.7269 | 0.8268 | 0.8899 | 0.7226 | 0.8144 | 0.8748 |
| PLE                | 0.7268 | 0.7843 | 0.8571 | 0.7268 | 0.8206 | 0.8861 | 0.7252 | 0.8084 | 0.8679 |
| ESMM               | 0.7202 | 0.7827 | 0.8606 | 0.7263 | 0.8231 | 0.8891 | 0.7222 | 0.8078 | 0.8684 |
| AITM               | 0.7256 | 0.7874 | 0.8586 | 0.727  | 0.8221 | 0.8829 | 0.7216 | 0.8127 | 0.871  |
|                    |        |        |        |        |        |        |        |        |        |
|                    |        |        |        |        |        |        |        |        |        |
|                    |        |        |        |        |        |        |        |        |        |



