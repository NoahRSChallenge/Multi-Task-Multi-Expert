# Multi-Task Multi-Expert Challenge

This repo provides a benchmark data processing and evaluation for [Multi-task and Multi-expert Learning Challenge](https://www.chaspark.net/#/questions/780114430883729408?sub=780117223107399680) from Noah's Ark Recommendation & Search Lab.

### Data
[AliExpress Dataset](https://tianchi.aliyun.com/dataset/dataDetail?dataId=74690): AliExpress dataset collects user logs from real-world traffic in AliExpress. It contains two tasks -- CTR prediction and CVR prediction.

To process the data, download original data, update the corresponding data path, and run
```
python process_aliexpress.py --dataset_name NL
```

### Evaluation
[AUC score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html) for CTR, CVR, and CTCVR.


### Baseline Results
We train baseline models on each of the four datasets (NL, ES, FR, US), early stopping by CVR. We conduct experiments three times and report the results as follows. For details of the baseline implementation, please check [this](https://github.com/easezyc/Multitask-Recommendation-Library) nice multi-task library.
<table>
<thead>
  <tr>
    <th></th>
    <th colspan="3">NL</th>
    <th colspan="3">ES</th>
    <th colspan="3">FR</th>
    <th colspan="3">US</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Model Name</td>
    <td>CTR</td>
    <td>CVR</td>
    <td>CTCVR</td>
    <td>CTR</td>
    <td>CVR</td>
    <td>CTCVR</td>
    <td>CTR</td>
    <td>CVR</td>
    <td>CTCVR</td>
    <td>CTR</td>
    <td>CVR</td>
    <td>CTCVR</td>
  </tr>
  <tr>
    <td>DNN</td>
    <td>0.7203 </td>
    <td>0.7815 </td>
    <td>0.8556 </td>
    <td>0.7252 </td>
    <td>0.8141 </td>
    <td>0.8832 </td>
    <td>0.7174 </td>
    <td>0.8071 </td>
    <td>0.8702 </td>
    <td>0.7058 </td>
    <td>0.8068 </td>
    <td>0.8637 </td>
  </tr>
  <tr>
    <td>MMOE</td>
    <td>0.7195 </td>
    <td>0.7870 </td>
    <td>0.8574 </td>
    <td>0.7269 </td>
    <td>0.8268 </td>
    <td>0.8899 </td>
    <td>0.7226 </td>
    <td>0.8144 </td>
    <td>0.8748 </td>
    <td>0.7053 </td>
    <td>0.8069 </td>
    <td>0.8639 </td>
  </tr>
  <tr>
    <td>PLE</td>
    <td>0.7268 </td>
    <td>0.7843 </td>
    <td>0.8571 </td>
    <td>0.7268 </td>
    <td>0.8206 </td>
    <td>0.8861 </td>
    <td>0.7252 </td>
    <td>0.8084 </td>
    <td>0.8679 </td>
    <td>0.7092 </td>
    <td>0.8175 </td>
    <td>0.8699 </td>
  </tr>
  <tr>
    <td>ESMM</td>
    <td>0.7202 </td>
    <td>0.7827 </td>
    <td>0.8606 </td>
    <td>0.7263 </td>
    <td>0.8231 </td>
    <td>0.8891 </td>
    <td>0.7222 </td>
    <td>0.8078 </td>
    <td>0.8684 </td>
    <td>0.7035 </td>
    <td>0.8179 </td>
    <td>0.8712 </td>
  </tr>
  <tr>
    <td>AITM</td>
    <td>0.7256 </td>
    <td>0.7874 </td>
    <td>0.8586 </td>
    <td>0.7270 </td>
    <td>0.8221 </td>
    <td>0.8829 </td>
    <td>0.7216 </td>
    <td>0.8127 </td>
    <td>0.8710 </td>
    <td>0.7019 </td>
    <td>0.8219 </td>
    <td>0.8655 </td>
  </tr>
  <tr>
    <td>MMOE+MGDA</td>
    <td>0.7225 </td>
    <td>0.7846 </td>
    <td>0.8579 </td>
    <td>0.7264 </td>
    <td>0.8213 </td>
    <td>0.8862 </td>
    <td>0.7218 </td>
    <td>0.8101 </td>
    <td>0.8705 </td>
    <td>0.7051 </td>
    <td>0.8142 </td>
    <td>0.8668 </td>
  </tr>
  <tr>
    <td>MMOE+NashMTL</td>
    <td>0.7229 </td>
    <td>0.7852 </td>
    <td>0.8583 </td>
    <td>0.7267 </td>
    <td>0.8228 </td>
    <td>0.8868 </td>
    <td>0.7227 </td>
    <td>0.8107 </td>
    <td>0.8705 </td>
    <td>0.7050 </td>
    <td>0.8157 </td>
    <td>0.8675 </td>
  </tr>
  <tr>
    <td>PLE+MGDA</td>
    <td>0.7236 </td>
    <td>0.7848 </td>
    <td>0.8585 </td>
    <td>0.7266 </td>
    <td>0.8220 </td>
    <td>0.8862 </td>
    <td>0.7227 </td>
    <td>0.8099 </td>
    <td>0.8697 </td>
    <td>0.7049 </td>
    <td>0.8174 </td>
    <td>0.8682 </td>
  </tr>
  <tr>
    <td>PLE+NashMTL</td>
    <td>0.7230 </td>
    <td>0.7849 </td>
    <td>0.8588 </td>
    <td>0.7266 </td>
    <td>0.8223 </td>
    <td>0.8863 </td>
    <td>0.7222 </td>
    <td>0.8102 </td>
    <td>0.8700 </td>
    <td>0.7041 </td>
    <td>0.8174 </td>
    <td>0.8678 </td>
  </tr>
</tbody>
</table>


*_Participants are encouraged to share the model checkpoints for us to verify the claimed results._
