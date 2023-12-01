# IEEE-CEC-2023-Competition
The Platform for CEC 2023 Competition on "Large-scale Continuous Optimization for Non-contact Measurement"

**Please use the PlatEMO v4.0 as the platform for competition**

## Overview & Aim:
***
  Evolutionary algorithms (EAs) have been a popular optimization tool for decades, showing their promising performance in solving various benchmark optimization problems. Nevertheless, using EAs on continuous optimization with over 100 decision variables (large-scale optimization problems, LSOPs) remains challenging due to the "curse of dimensionality". This phenomenon is more significant for those LSOPs in emerging applications, e.g., lightweight vehicle design, industrial power delivery and scheduling, smart grid optimization, and data sensitivity analysis. Specifically, LSOPs in emerging applications are challenging due to the enormous search space, irregularity in variable interactions and objective functions, and the existence of massive local optima. Conventional EAs may cost unbearable function evaluations (FEs) and computation time to obtain acceptably converged/diverse results. In extreme scenarios, most EAs fail to converge to the optima no matter how many FEs are consumed, or may fail to obtain enough diversity information for decision-making. The design of practical EAs for solving LSOPs in real-world applications is urgent and meaningful.
  
  IntelliSense is an emerging topic in recent years, which plays a crucial part in intelligent sensing for modern industry and society, e.g., the Internet of Things (IoT), smart grids, and intelligent robots. Among various IntelliSense scenarios, the non-contact measurement in electronic engineering has shown its great potential and importance. As the most extensive man-made system in the world, the modern electric system requires the measurement of voltages and currents accurately and safely in real-time. How to non-contact measure voltages and currents in a bundle of conductors enclosed in a structure has been an emerging topic in power distribution, power electronics, and power quality evaluation, to mention just a few fields of interest. The use of computational intelligence techniques, especially evolutionary computation, starts a new direction for non-contact measurement. Specifically, the black-box measurement task can be solved by EAs only, and the system can access real-time information with the assistance of effective and efficient EAs. Also, the non-contact measurement can be extended to other areas for intelligent sensing.
  
  This competition has two tracks: large-scale continuous single- and multi-objective optimization in two non-contact measurement cases. We carefully select six LSOPs for each track from two tasks, i.e., non-contact voltage measurement for multiconductor systems (NVM) and non-contact current measurement for multiconductor systems (NIM).

* The NVM takes advantage of the electric field around the conductors for estimating the ground truth voltage values. This NVM problem includes two types of decision variables, i.e., fixed positions of the conductors and time-varying ground truth voltage values. Generally, the variable interactions are complex in the NVM problem. First, the six position variables interact with each other. Second, the voltages in each phase interact with each other sequentially but do not interact with the voltages in other phases. Third, all the voltages are directly interacting with the positions. An illustrative example of the principle for NVM problems is given in Fig. 1.

<img src="https://github.com/ChengHust/IEEE-CEC-2023-Competition/blob/main/NVM.png" /> 
Fig. 1 The principle of the NVM problems. (a) The cross section of three-phase systems and sensors; (b) the distribution of the measured electric field (EF) and the measured and calculated EF intensities around the housing; (c) the three-phase voltages obtained by minimizing the EF intensities in (b).


* In NIM tasks, the magnetic field information around the conductors is used to estimate the ground truth current values. Different from NVM, the variables of NIM can be more complex. First, more position variables are needed for the model building to cope with conductor tilt, as shown in Fig. 2 (a). Second, the magnetic field information around the conductor may contain interference noise, aggravating the difficulty in robustly obtaining the ground truth currents, as shown in Fig. 2 (b). Third, complex numbers are involved in real-time current measurement.

<img src="https://github.com/ChengHust/IEEE-CEC-2023-Competition/blob/main/NIM.png" /> 
Fig. 2 The NIM problems in practice. (a) Three-phase conductors are inclined to each other; (b) The measured magnetic field with interference noise.

## Platform & Parameter settings
Participants are encouraged to develop the algorithm to solve this type of optimization problem, not just a specific one of them. Participants may propose a new optimization algorithm or utilize a hybrid form of previously proposed algorithms. However, it must be restricted in the field of evolutionary computing. Participants are required to submit their own source codes, a brief description of the optimization algorithm, a brief code instruction, and the data generated by the platform. Organizers will assess the quality of your submitted data in all six problems to guarantee its fairness. With the same computational budget, the best solution for each problem obtained by randomly running your algorithm 30 times will be compared directly. 

The PlatEMO v4.0 will be used as the competition platform for fair comparisons (PlatEMO v4.0), with population size (N=100), number of independent runs (run=30), and number of results (20). The code of an example settings is give as 
```
platemo('problem',@SONVM1,'algorithm',@GA,'N',100,'maxFE',100000,'save',20)
```
* For **Single-objective Optimization Track**, the test problems are
  SONVM1 (D=129), SONVM3 (D=1008), SONVM5 (D=1506), 
  SONIM1 (D=1506), SONIM2(D=3006), SONIM3 (D=3006).
  The maximum number of function evaluations (maxFE=***1e6 for SONIM Problems, and maxFE=1e5 for SONVM Problems***).
  <img src="https://github.com/ChengHust/IEEE-CEC-2023-Competition/blob/main/SOP_track.png" /> 
  
* For **Multi-objective Optimization Track**, the test problems are
  MONVM2 (D=4605), MONVM4 (D=22206), MONVM6 (D=54756),
  MONIM1 (D=3006), MONIM2(D=3006), MONIM3 (D=3006).
  The maximum number of function evaluations (***maxFE=1e8 for MONVM and MONIM Problems***).
  <img src="https://github.com/ChengHust/IEEE-CEC-2023-Competition/blob/main/MOP_track.png" /> 
* Participants are allowed to use the parallel execution mode for efficiency.

## Important Dates:
For participants planning to submit a paper to the 2023 IEEE Congress on Evolutionary Computation:
### Paper submission: 13 Jan 2023
  - We have also hosted two special sessions on CEC 2023 ("Large-scale multi-objective optimization in emerging applications" and "EC in Healthcare Industry").
  - Paper reviews: 3 Mar 2023 
  - Paper re-submission: 24 Mar 2023 
  - Paper final notifications: 31 Mar 2023 
Note: You are encouraged to submit your paper to the given at: [CEC 2023](https://2023.ieee-cec.org/)
**Participants for competition** only:
  - Results submission deadline: 28 April 2023 
  - You can submit your related documents and results to Dr. He (chenghe_seee@hust.edu.cn)/ Dr. Wang (hdwang@xidian.edu.cn)/ Dr. Tian (field910921@gmail.com).

## Competition Organizers:
* ***Cheng He***
  School of Electrical and Electronic Engineering, Huazhong University of Science and Technology, Wuhan 430074, China. 
  chenghe_seee@hust.edu.cn
* ***Ye Tian***
  Institutes of Physical Science and Information Technology, Anhui University, Hefei 230601, China
  field910921@gmail.com
* ***Handing Wang***
  School of Artificial Intelligence, Xidian University, Xi'an 710071, China. 
  hdwang@xidian.edu.cn
* ***Hongbin Li***
  School of Electrical and Electronic Engineering, Huazhong University of Science and Technology, Wuhan 430074, China. 
  lihongbin@hust.edu.cn
* ***Yaochu Jin***
  Faculty of Technology, Bielefeld University, D-33615 Bielefeld, Germany
  yaochu.jin@uni-bielefeld.de

## Competition Winners for the Single-objective Optimization Track:
* ***Winner***
  H2IMODE, Chaojun Ma, Yonglin He, You Wu, Lianghao Li, Huazhong University of Science and Technology
* ***1st runner-up***
  CC-CMAES-LAG, Yapei Wu, Tong Liu, Yanan Li, Xingguang Peng, Northwestern Polytechnical University
* ***2nd Runner Up***
  MIDEX, Chauanji Zhang, Cheng Cheng, Huazhong University of Science and Technology

## Competition Winners for the Multi-objective Optimization Track:
* ***Winner***
  SLMEA, Luchen  Wang, Shuai Shao,  Chengming Wu, Shangshang Yang, Anhui University
* ***1st runner-up***
  LMOEA-DS, Shufen Qin, Pengpeng Zhao, Lu Wang, Xinyu Ren, Taiyuan University of Science and Technology
* ***2nd Runner Up***
  MOEA/D-DE-DVA, 	Yongcun Liu, Junfeng Tang, Nan Zheng, Haoran Gu, Xidian University
