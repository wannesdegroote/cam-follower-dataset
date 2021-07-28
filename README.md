# Cam-follower mechanism: Dataset description
 This repository contains an extensive dataset generated by a cam-follower setup. The dataset contains a full-factorial design of 1600 experiments. Each experiment contains timeseries captured for a specific cam design, follower mass and motor voltage. 
#### NOTIFICATION: Scientific research based on this dataset is currently submitted for publication. The dataset is currently not publically available. We will provide the dataset in this repository once the research paper is accepted for publication. 

Contact: \
Wannes.DeGroote@UGent.be \
Guillaume.Crevecoeur@UGent.be \
http://www.ugent.be/m-f/en



## Lab setup 
The trajectory data is sampled at 2000 Hz by means of a rotary encoder (1000 lines) and a linear encoder (resolution=2µm). The setup is driven by a DC motor of 60 W,  which is fed by a (changeable) constant voltage V. The mass m of the follower can be changed by adding additional disks.

![setup](https://raw.githubusercontent.com/wannesdegroote/cam-follower-dataset/main/Figures/setup.JPG)

The setup is equipped with 20 interchangeable cams. Each cam is determined by its maximum displacement H and the skewness angle β.
![cams](https://raw.githubusercontent.com/wannesdegroote/cam-follower-dataset/main/Figures/cams.JPG)

## Data description

We used 20 different cams, 4 different masses and 20 different voltages. This leads to a full-factorial design of 1600 experiments. 
The file parameters.csv describes the parameters used for each experiment.
Experiment number | H |  β | m |V | 
------ | -------------| -------------| -------------| -------------
1 | 0.01 |1/2 π  |0.73 |3.6 |
2 | 0.01 |1/2 π  |0.73| 3.98|
...|... | ...| ...|...| 
1600|0.07 |3/2 π | 1.31|10.8| 

The file expi.csv contains the timeseries collected for the i-th experiment.
Note that some signals are post-processed to eliminate the sensor noise.
Variable |Explanation | 
------|----------|
t | timestamp of the measurement |
θ | angle: directly measured by the rotational encoder |
ω| angular speed: derived from θ via central differencing and some filtering techniques |
α| angular acceleration: derived from ω via central differencing and some filtering techniques  |
y| displacement: directly measured by the linear encoder |
h| cam displacement: directly measured by the linear encoder (=nominal situation without detachment) ||
ϵ| detachment variable: derived via ϵ= y-h and some post-processing to eliminate sensor noise 
