Sound Tuner Twin

A minimal dual-system extension of the OBA Audio sound tuner, designed for controlled observation of post-model discontinuity behavior.


Overview
Sound Tuner Twin is an extension of the original OBA Audio sound tuner experiment.
While the original sound tuner focuses on how a single OBA-based auditory system produces intermediate perceptual states under energy-aware dynamics, Sound Tuner Twin introduces a second system (OBA2) that:

passively observes the first system (OBA1),
records its internal state trajectory,
and later runs independently under the same physical input conditions.

The goal of this repository is to provide a clean, reproducible implementation of this dual-system setup for further analysis.

Relationship to the Original OBA Sound Tuner
Original Sound Tuner (OBA1)

Single perceptual system
Energy-aware auditory pipeline
Produces intermediate states (e.g. BR / WA, Tone / Noise, Energy)
Designed to study the emergence and structure of intermediate representations

Sound Tuner Twin (OBA1 + OBA2)
In addition to the original sound tuner, this version adds:


OBA2 (Observer / Twin System)
A second system with:

identical input modality (audio),
identical processing pipeline,
but no access to OBA1’s internal computations.



Passive Observation Phase

OBA2 records OBA1’s intermediate states and energy values
No intervention, no feedback, no control



Independent Run Phase

OBA1 is considered inactive
OBA2 runs independently on the same audio input
Energy and state variables are recorded but do not modulate behavior



Crucially, OBA2 does not introduce new objectives, losses, or decision logic beyond what already exists in the original sound tuner.

What Is Not Added
To avoid confounding factors, the following are explicitly excluded:

No additional learning rules
No external supervision signals
No energy-based stopping or gating in OBA2
No parameter tuning specific to the twin setup
No requirement for hardware deployment

This repository focuses strictly on structural observation, not optimization.

Repository Structure (Typical)
sound_tuner_twin/
├── sound_tuner_v2/        # Original OBA Audio sound tuner (baseline)
├── sound_tuner_twin.ipynb # Dual-system (OBA1–OBA2) experiment notebook
├── README.md
└── requirements.txt


Running the Experiment

Open sound_tuner_twin.ipynb
Run cells in order:

OBA sound tuner definition
OBA2 observer definition
Passive observation phase
Independent run phase
Manifold analysis (unchanged from original OBA tools)


No special configuration or hardware is required.

The notebook is designed so that restarting the kernel and re-running top-to-bottom reproduces the same behavior.

Notes on Scope
This repository intentionally limits interpretation.

The code is meant to provide a transparent experimental scaffold.
The notebook records intermediate states for later inspection.
Any theoretical interpretation is left to downstream analysis.


License / Attribution
This project builds directly on the OBA Audio sound tuner series.
Please cite accordingly if reused or extended.
