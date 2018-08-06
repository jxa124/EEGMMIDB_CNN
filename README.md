# EEGMMIDB_CNN
## Data
实验采用的是网上的开源数据，数据的地址为：https://www.physionet.org/pn4/eegmmidb/

实验采用的是Subject1-Subject9的想象运动的数据集：

```
# subject=1-9, run=04,06,08,10,12,14
S00[subject]R[run]
```
说明：
* 每次run持续2min, 采样频率160Hz, 采样点大概有20000左右
* run 04 08 12 是想象左右手的运动：rest(10080)、left(5328)、right(4592)
* run 06 10 14 是想象上下双拳和双脚的运动：rest(10080)、fists(5328)、feet(4592)
* 数据是采用的64个电极采集的，故有64维（数据的列）
* 数据的行是时间，每一个时间点一个sample，每个sample最后一维（64）维是label [0:64]
* 原始数据中，label为1，2，3：1代表休息，2代表（左手运动/双拳运动），3代表（右手运动/双脚运动）* 

实验数据：
* 每一个subject都有一份整合好的数据：S1_data 为subject 1的数据
* 每一个subject数据的shape为(29920,65),最后一列为label
* 从run04,06,08,10,12,14中的rest选择1800，然后组成最后的rest(10080),label为1;
* 从04,08,12中的left,right各选择1776,1531，然后组成最后的left(5328),right(4592),label为2,3;
* 从06,10,14中的fists,feet各选择1776,1531，然后组成最后的fists(5328),feet(4592),label为4,5;

## CNN网络结构
![CNN_STRUCTURE](https://github.com/jxa124/EEGMMIDB_CNN/blob/master/cnn-8-shape.png)

## 结果比较
| Subject  | SUB1   |  SUB2  |  SUB3  |  SUB4  |  SUB5  |  SUB6  |  SUB7  |  SUB8  |  SUB9  |
|  :----:  | :----: | :----: | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| 准确率   | 0.9274 |0.8901 |0.9140 |0.8722 |0.8671 |0.8864 |0.9274 |0.9034 |0.9311 |0.9263 |
