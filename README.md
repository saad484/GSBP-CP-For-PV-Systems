# GSBP-CP: A Real-Hardware Cross-Layer Dataset and Benchmark for Intrusion Detection in Grid-Connected Photovoltaic Systems

**Version 1.0** · **License: CC BY 4.0** · **DOI: [10.5281/zenodo.23198408](https://doi.org/10.5281/zenodo.23198408)**

## Download from Zenodo

**[Download the dataset and accompanying files on Zenodo](https://zenodo.org/records/23198408).**

This GitHub repository is the landing page for GSBP-CP. The dataset is distributed through
Zenodo. Open the record above and download the files listed there, including
`GSBP-CP_v1.0.zip`. Extract the archive and consult its README, datasheet, and data dictionary
before using the data.

Please use Zenodo for dataset downloads and cite the dataset DOI in publications.

## Overview

GSBP-CP was collected on an operational grid-tied photovoltaic installation at the Green & Smart
Building Park of Mohammed VI Polytechnic University (UM6P), Benguerir, Morocco. It synchronises
four observation channels of the same installation:

- **Inverter telemetry:** 23 holding registers from a Huawei SUN2000L-5KTL inverter, polled over Modbus/TCP.
- **Protocol timing:** per-register read latencies and poll-cycle timing.
- **Network traffic:** SCADA-LAN packet captures covering Modbus/TCP, MQTT, and ARP.
- **Independent power measurements:** a Shelly 3EM three-phase meter that cross-checks the inverter's reported power.

The release covers approximately 72.7 hours of normal operation over 15–18 June 2026 and six
attack families, each executed three times on real production hardware. False data were injected
inside a transparent Modbus proxy; no value was written to the inverter.

## Dataset contents

The Zenodo package provides:

- Raw inverter and meter CSV files and packet captures for the seven scenarios below.
- A fused model-ready table with **223,215 records and 66 numeric features**, plus an extended
  table with **78 features** including per-phase meter channels.
- Ground-truth attack logs and evaluation split columns.
- Data-fusion and feature-processing notebooks, split-generation code, and a benchmark-results notebook.
- A datasheet, data dictionary, license, and citation metadata.

| Scenario | Description | Model-ready records |
|---|---|---:|
| S0 | Normal operation | 211,704 |
| S1 | Reconnaissance | 1,537 |
| S2 | Denial of service | 718 |
| S3 | False-data injection: response tampering, physics-consistent inflation, and frequency ramp | 4,622 |
| S4 | Replay | 1,513 |
| S6 | ARP spoofing | 1,575 |
| S7 | MQTT injection | 1,546 |

S5 was reserved in the acquisition schedule and was not executed.


## Citation

Please cite the dataset:

> S. Aiddi, S. A. Sana, I. Ait abdelmoula, M. Jouhari, and A. Motii,
> “GSBP-CP: A Real-Hardware Cross-Layer Dataset and Benchmark for Intrusion Detection in
> Grid-Connected Photovoltaic Systems,” version 1.0, Zenodo, 2026.
> DOI: [10.5281/zenodo.23198408](https://doi.org/10.5281/zenodo.23198408).

```bibtex
@misc{aiddi2026gsbpcp,
  author    = {Aiddi, Saad and Sana, Sidi Ahmadou and Ait abdelmoula, Ibtihal and Jouhari, Mohammed and Motii, Anas},
  title     = {{GSBP-CP}: A Real-Hardware Cross-Layer Dataset and Benchmark for Intrusion Detection in Grid-Connected Photovoltaic Systems},
  year      = {2026},
  version   = {1.0},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.23198408},
  url       = {https://doi.org/10.5281/zenodo.23198408}
}
```



Use the Zenodo record for the published dataset metadata.

## License and responsible use

The data, documentation, and accompanying code are released under the
[Creative Commons Attribution 4.0 International license (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
The license and attribution information are included in the Zenodo package.

The testbed was operated under internal authorisation. Collection credentials were removed
from the captures, and attack and injection scripts are withheld. The dataset represents one
site and one inverter vendor; consult the datasheet before generalising results.

## Authors and contact

**Saad Aiddi · Sidi Ahmadou Sana · Ibtihal Ait abdelmoula · Mohammed Jouhari · Anas Motii**

Corresponding author: **Saad AIDDI**, College of Computing, Mohammed VI Polytechnic University (UM6P).

Questions and reproducibility reports can also be submitted through
[GitHub Issues](https://github.com/saad484/GSBP-CP-For-PV-Systems/issues).

This work was supported by OCP–UM6P through the EESEPS program, Grant No. 154RHPR006,
Project 4, “Photovoltaic energy production and storage (VOLTA).”
