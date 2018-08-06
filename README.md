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
* run 04 08 12 是想象左右手的运动
* run 06 10 14 是想象上下双拳和双脚的运动
* 数据是采用的64个电极采集的，故有64维（数据的列）
* 数据的行是时间，每一个时间点一个sample，每个sample最后一维（64）维是label [0:64]
* 原始数据中，label为1，2，3：1代表休息，2代表（左手运动/双拳运动），3代表（右手运动/双脚运动）* 
