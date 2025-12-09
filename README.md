# FIFO-instance

This repository provides all instance data used for *Optimizing metro timetabling and capacity decisions considering feeder buses*.
It contains input parameters and passenger demand data for both:

- **Model MO** 

- **Model FF**

All files are organized into four folders, described below.
```
FIFO-instance/
├── instances_MO/
├── instances_FF/
├── passenger_data_MO/
└── passenger_data_FF/
```
## 1. `instances_MO/` — JSON Input for Model MO

This folder contains **32 JSON instance files** for **Model MO**:

- File names: &nbsp; `instance_1.json  …  instance_32.json`

Each JSON file stores the complete model input parameters required for solving **Model MO**, including sets, capacities, headways, and other operational parameters.

## 2. `instances_FF/` — JSON Input for Model FF

This folder contains **96 JSON instance files** for **Model FF**:

They are grouped by the number of feeder lines:
- Three Feeder Lines (32 instances): &nbsp; `tra_instance_1.json   …   tra_instance_32.json`
- Two Feeder Lines (32 instances): &nbsp; `tra_instance_41.json   …   tra_instance_72.json`
- One Feeder Line (32 instances): &nbsp; `tra_instance_81.json   …   tra_instance_112.json`

Each JSON file includes detailed operational parameters for metro lines and feeder lines, transfer station configuration, and planned arrival times of feeder buses.

## 3. `passenger_data_MO/` — Passenger Demand for MO (32 Excel Files)

This folder contains the metro passenger demand `p_{ijt}` associated with the 32 MO instances.

- File names: &nbsp; `1_p_arr.xlsx  …  32_p_arr.xlsx`
- Data format:
<div align="center">

| i   | j   | t   | value |
| --- | --- | --- | ----- |
| 0   | 1   | 0   | 0     |
| 0   | 1   | 1   | 2     |
| 0   | 1   | 2   | 6     |
| ... | ... | ... | ...   |

</div>

`i`: passenger boarding station; `j`: passenger alighting station; `t`: passenger arrival time step; `value`: number of arriving passengers

## 4. `passenger_data_FF/` — Feeder Passenger Demand for FF (96 Excel Files)

This folder contains the feeder passenger demand `q_{ijf}^l` associated with the 96 FF instances.

- File names:
    - Three Feeder Lines (32 instances): &nbsp; `1_transfer_p_arr.xlsx  …  32_transfer_p_arr.xlsx`
    - Two Feeder Lines (32 instances): &nbsp; `41_transfer_p_arr.xlsx … 72_transfer_p_arr.xlsx`
    - One Feeder Line (32 instances): &nbsp; `81_transfer_p_arr.xlsx … 112_transfer_p_arr.xlsx`

- Data format:
<div align="center">

| l   | i   | j   | f   | value |
| --- | --- | --- | --- | ----- |
| 0   | 1   | 2   | 0   | 60    |
| 0   | 1   | 2   | 1   | 60    |
| 0   | 1   | 3   | 0   | 43    |
| 0   | 1   | 3   | 1   | 38    |
| ... | ... | ... | ... | ...   |

</div>

`l`: feeder line index; `i`: passenger boarding station (transfer station); `j`: passenger alighting station; `f`: feeder bus index; `value`: number of feeder passengers
