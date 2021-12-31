# RTSS-2019-WIP
A brief presentation for RTSS 2019 (first HK, CN, then York, finally cancelled).

Unfortunately, the original codes (resampling and split the raw ECG to 256-dot segments, implementing a pytorch ResNet) were lost in a winter. The server was dead since the author was unaware that the CPU FAN failed to cleave to the CPU. 

This is an updated version of work-in-progress code and it would be part of his dissertation. We assume that the deep learning model assigns small segments of each ECG record to AF or normal and voting strategy provides the prediction of the ECG record. The key finding is that AF/Normal alrogithms using ECG of a small time interval, a extremely low sampling rate (60 Hz) and fewer ECG segments can derive predictive methods that are comparable to those using a large time interval, a high sampling-rate (300 Hz) and many ECG segments, when the clinical outcomes of a good model (e.g. acc 0.85) and a very good model (e.g acc 0.90) are close. The key finding lead to our key conclusion that we can use a lightweight scheme despite we didn't know how to design a light-weight model. Our future work includes designing a lightweight model in more complex heart rhythm classifcation task [2] and designing a lightweight model in sleep apnea detection [3] to validate the robustness of the lightweight pipeline.  

## Pipleline

1. Download and unzip the training set of Physionet challenge 2017.

2. Install necessary python libraries according to [requirement.txt]

3. Click and run SplitData.ipynb to split records into segments. (You can change resample_Fs)

4. Click and run Main.ipynb to verify algorithms.
 
[1]
```
@INPROCEEDINGS{2019Feasibility,  author={Yu, Yunkai and Yang, Zhihong and Li, Peiyao and Yang, Zhicheng and You, Yuyang},  booktitle={2019 IEEE Real-Time Systems Symposium (RTSS)},   title={Work-in-Progress: On the Feasibility of Lightweight Scheme of Real-Time Atrial Fibrillation Detection Using Deep Learning},   year={2019},  volume={},  number={},  pages={552-555},  doi={10.1109/RTSS46320.2019.00062}}
```

[2] Application 1
```
@INPROCEEDINGS{2020hrclf,  author={Yu, Yunkai and Yang, Zhihong and Li, Peiyao and Yang, Zhicheng and You, Yuyang},  booktitle={2020 Computing in Cardiology},   title={A Real-Time ECG Classification Scheme Using Anti-Aliased Blocks With Low Sampling Rate},   year={2020},  volume={},  number={},  pages={1-4},  doi={10.22489/CinC.2020.162}}
```

[3] Application 2
```
@article{2021FASSNet,
  title={FASSNet: fast apnea syndrome screening neural network based on single-lead electrocardiogram for wearable devices},
  author={ Yu, Yunkai  and  Yang, Zhihong  and  You, Yuyang  and  Shan, Wenjing },
  journal={Physiological Measurement},
  volume={42},
  number={8},
  pages={085005 (15pp)},
  year={2021},
}
```

## Todo

Dependencies (requirement.txt).
