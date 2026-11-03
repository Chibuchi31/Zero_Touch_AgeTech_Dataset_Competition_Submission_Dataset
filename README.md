\# **Zero-Touch Hospital Dataset for Assistive Living and Smart Environments**



A synthetic, machine-learning-ready dataset for touchless interaction research

in home and hospital environments for older adults.



\*\*Authors:\*\* Arnuchi-Anele Chibuchi Diligence, Eze Chisom Benedicta, Ogbonnaya Obinna Kingsley

University of Port Harcourt, Nigeria

\*\*Submitted to:\*\* IEEE AgeTech Global Dataset Competition 2026

\*\*License:\*\* CC BY 4.0



\---



\## Overview



This dataset supports research into zero-touch gesture-based control for older

adults in home and hospital settings. It models intentional device commands,

incidental movement, background activity, and emergency-help gestures using

simulated sensor-inspired features.



\*\*Dataset snapshot:\*\*

\- 20,000 event records × 26 columns

\- 160 synthetic participant profiles (OA001–OA160)

\- 12 activity classes

\- Environments: home and hospital

\- Generator version: 2.0.0 | Seed: 42



> This is a synthetic dataset. No real older adults were recruited and no

> physical sensor measurements were collected.



\---



\## Motivation



Many older adults face mobility, reach, or dexterity limitations that make

routine device controls difficult to operate independently. In home settings,

touchless gesture control can reduce dependence on caregivers for simple

appliance operations. In hospitals, it offers a way to reduce hand contact with

frequently touched shared controls.



This dataset provides a reproducible resource for prototyping and benchmarking

classification systems that distinguish intentional commands from incidental

movement and emergency gestures — across both environments.



\---



\## Activity Classes



| Activity Label | Description |

|---|---|

| `intentional\\\_light\\\_on/off` | Gesture to toggle a light |

| `intentional\\\_fan\\\_on/off` | Gesture to toggle a fan |

| `intentional\\\_tap\\\_on` | Gesture to operate a tap |

| `intentional\\\_toilet\\\_flush` | Gesture to flush a toilet |

| `intentional\\\_bed\\\_raise/lower` | Gesture to adjust hospital bed (hospital ward only) |

| `emergency\\\_help` | Simulated emergency-help gesture |

| `unintentional\\\_passing` | Person passing without interacting |

| `unintentional\\\_staff\\\_activity` | Staff movement near a device |

| `background\\\_no\\\_activity` | No significant activity detected |



\---



\## Dataset Structure



\*\*26 columns in release order:\*\*



\- \*\*Identifiers/time:\*\* `event\\\_id`, `timestamp`, `participant\\\_id`

\- \*\*Participant \& environment context:\*\* `age`, `age\\\_band`, `mobility\\\_profile`,

&#x20; `environment`, `setting`, `sensor\\\_modality`, `hour\\\_of\\\_day`, `ambient\\\_light\\\_lux`

\- \*\*Sensor-inspired features:\*\* `distance\\\_cm`, `vertical\\\_travel\\\_cm`,

&#x20; `approach\\\_angle\\\_deg`, `velocity\\\_m\\\_s`, `duration\\\_ms`, `dwell\\\_ms`,

&#x20; `motion\\\_cycles`, `tremor\\\_index`, `hand\\\_detected`, `occlusion\\\_flag`,

&#x20; `signal\\\_quality`, `is\\\_ambiguous`

\- \*\*Targets:\*\* `y\\\_activity` (12-class), `y\\\_is\\\_intentional` (binary),

&#x20; `y\\\_is\\\_emergency` (binary)



Missing values are allowed only in `distance\\\_cm`.



\---



\## Baseline Performance



Grouped 5-fold cross-validation using `HistGradientBoostingClassifier`

(grouped by `participant\\\_id`):



| Metric | Score |

|---|---|

| Accuracy | 0.749 |

| 12-class macro-F1 | 0.666 |

| Emergency precision | 0.904 |

| Emergency recall | 0.867 |

| Emergency PR-AUC | 0.944 |

| Command/emergency/ignore macro-F1 | 0.940 |



\---



\## Reproducing the Dataset



\*\*Requirements:\*\* Python, NumPy, pandas, scikit-learn



\*\*Steps:\*\*

1\. Open the notebook in Google Colab or run `ZeroTouch\\\_Dataset\\\_Generator\\\_v2.py`

2\. Confirm output: 20,000 rows × 26 columns, 160 participants, 12 classes

3\. Preserve seed 42 and default configuration for exact deterministic regeneration



\*\*Google Colab:\*\*

https://colab.research.google.com/drive/1T20B-3NNIswIEp4TmcSHNonU7fgY9mR1?usp=sharing



\---



\## Responsible Use



\- Do not infer real identities from synthetic participant IDs or timestamps.

\- Do not present synthetic records or labels as real observations.

\- Use for research, education, prototyping, and benchmarking only.

\- Do not use for autonomous emergency response, clinical decisions, or

&#x20; safety-critical deployments.



\---



\## Repository Contents



| File | Description |

|---|---|

| `ZeroTouch\\\_Dataset\\\_Submission.csv` | Canonical 20,000 × 26 release CSV |

| `ZeroTouch\\\_Dataset\\\_Generator\\\_v2.py` | Dataset generator script |

| `ZeroTouch\\\_Dataset\\\_Report.docx` | Full dataset report |

| `ZeroTouch\\\_IEEE\\\_AgeTech\\\_2026\\\_Organized.zip` | Full submission package |



\---



\## Citation



If you use this dataset, please cite:



> Arnuchi-Anele, C. D., Eze, C. B., \\\& Ogbonnaya, O. K. (2026).

> Zero-Touch Hospital Dataset for Assistive Living and Smart Environments

> (Version 2.0.0). IEEE AgeTech Global Dataset Competition 2026.

