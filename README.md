# dataset-ssvep-exoskeleton

## Introduction

This dataset gathers SSVEP-based BCI recordings of 12 subjects operating an upper limb exoskeleton during a shared control task. The exoskeleton is either controlled with a touchless interface detecting hand poses or with SSVEP-based BCI.


## Related publications:

This dataset is used in the following publications:

-  Emmanuel K. Kalunga, Sylvain Chevallier, Olivier Rabreau, Eric Monacelli. _Hybrid interface : Integrating BCI in Multimodal Human-Machine Interfaces_. IEEE/ASME International Conference on Advanced Intelligent Mechatronics (AIM), 2014, Besancon, France.
-  Emmanuel Kalunga, Sylvain Chevallier, , Quentin Barthelemy. _Data augmentation in Riemannian space for Brain-Computer Interfaces_, STAMLINS (ICML workshop), 2015, Lille, France.
-  Emmanuel K. Kalunga, Sylvain Chevallier, Quentin Barthelemy. _Online SSVEP-based BCI using Riemannian Geometry_. arXiv preprint arXiv:1501.03227, 2015.


## Experimental setup

1. *Arm exoskeleton:* The exoskeleton used here is the ESTA robotic arm [1]. ESTA is designed to compensate for muscular dystrophy in the shoulder and elbow muscles occurring in several degenerative diseases, which affect the large muscles but spare the wrists and hands motor capacities.

2. *Touchless interface:* Our touchless interface embeds 5 IR-sensors which could set up in different spatial positions, according to the user requirements. The control system relies on a iterative kNN scheme to learn hand poses of each user. The details of the algorithm is provided in [2].

3. *Steady-state visually evoked potentials:* The g.Mobilab+ device is used for recording EEG at 256 Hz on 8 channels. For SSVEP stimulation, flash stimulus technique has been chosen. To avoid limitation imposed by refresh rate of computer screens, a microcontroller is set up to  flash stimuli with light emitting diodes (LED) at frequencies F ={13, 17, 21} Hz. The device has been controlled and the LED blinking is precise up to the millisecond. The eight electrodes are placed according to the 10/20 system on Oz, O1, O2, POz, PO3, PO4, PO7 and PO8.  The ground was placed on Fz and the reference was located on the right (or left) hear mastoid.

## Data description

The datasets contains 12 directories, containing recording from 12 male and female subjects aged between 20 and 26 years. Informed consent was obtained from all subjects, each one has signed a form attesting this consent. The subjects sits in the ...


## Bibliography

[1] M. Baklouti, P. A. Guyot, E. Monacelli, and S. Couvet. _Force controlled upper-limb powered exoskeleton for rehabilitation,_ in Intelligent Robots and Systems (IROS), 2008, p. 4202.

[2] H. Martin, S. Chevallier, and E. Monacelli, _Fast calibration of hand movement-based interface for arm exoskeleton control,_ in European Symposium on Artificial Neural Networks (ESANN), 2012, pp. 573– 578.
