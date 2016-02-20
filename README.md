# dataset-ssvep-exoskeleton

## Introduction

This dataset gathers SSVEP-based BCI recordings of 12 subjects operating an upper limb exoskeleton during a shared control task. The exoskeleton is either controlled with a touchless interface detecting hand poses or with SSVEP-based BCI.


## Related publications:

This dataset is used in the following publications:

-  Emmanuel K. Kalunga, Sylvain Chevallier, Olivier Rabreau, Eric Monacelli. _Hybrid interface : Integrating BCI in Multimodal Human-Machine Interfaces_. IEEE/ASME International Conference on Advanced Intelligent Mechatronics (AIM), 2014, Besancon, France.
-  Emmanuel Kalunga, Sylvain Chevallier, Quentin Barthelemy. _Data augmentation in Riemannian space for Brain-Computer Interfaces_, STAMLINS (ICML workshop), 2015, Lille, France.
-  Emmanuel K. Kalunga, Sylvain Chevallier, Quentin Barthelemy. _Online SSVEP-based BCI using Riemannian Geometry_. arXiv preprint arXiv:1501.03227, 2015.


## Experimental setup

1. *Arm exoskeleton:* The exoskeleton used here is the ESTA robotic arm [1]. ESTA is designed to compensate for muscular dystrophy in the shoulder and elbow muscles occurring in several degenerative diseases, which affect the large muscles but spare the wrists and hands motor capacities.

2. *Touchless interface:* Our touchless interface embeds 5 IR-sensors which could set up in different spatial positions, according to the user requirements. The control system relies on a iterative kNN scheme to learn hand poses of each user. The details of the algorithm is provided in [2].

3. *Steady-state visually evoked potentials:* The g.Mobilab+ device is used for recording EEG at 256 Hz on 8 channels. For SSVEP stimulation, flash stimulus technique has been chosen. To avoid limitation imposed by refresh rate of computer screens, a microcontroller is set up to  flash stimuli with light emitting diodes (LED) at frequencies F ={13, 17, 21} Hz. The device has been controlled and the LED blinking is precise up to the millisecond. The eight electrodes are placed according to the 10/20 system on Oz, O1, O2, POz, PO3, PO4, PO7 and PO8.  The ground was placed on Fz and the reference was located on the right (or left) hear mastoid.

## Data description

The datasets contains 12 directories, containing recording from 12 male and female subjects aged between 20 and 28 years. Informed consent was obtained from all subjects, each one has signed a form attesting her or his consent. The subject sits in an electric wheelchair, his right upper limb is resting on the exoskeleton. The exoskeleton is functional but is not used during the recording of this experiment.

A panel of size 20x30 cm is attached on the left side of the chair, with 3 groups of 4 LEDs blinking at different frequencies. Even if the panel is on the left side, the user could see it without moving its head. The subjects were asked to sit comfortably in the wheelchair and to follow the auditory instructions, they could move and blink freely.

A sequence of trials is proposed to the user. A trial begin by an audio cue indicating which LED to focus on, or to focus on a fixation point set at an equal distance from all LEDs for the reject class. A trial lasts 5 seconds and there is a 3 second pause between each trial. The evaluation is conducted during a session consisting of 32 trials, with 8 trials for each frequency (13Hz, 17Hz and 21Hz) and 8 trials for the reject class, i.e. when the subject is not focusing on any specific blinking LED.

The recording are saved in GDF format [3], the stimulations code for each class are available as time events. There is between 2 and 5 sessions for each user, recorded on different days, by the same operators, on the same hardware and in the same conditions.

The stimulation code used in GDF file are those defined by OpenVibe:
- ExperimentStart: 32769, 0x00008001,
- ExperimentStop: 32770, 0x00008002
- VisualStimulationStart: 32779, 0x0000800b
- VisualStimulationStop: 32780, 0x0000800c
- Label_00: 33024, 0x00008100
- Label_01: 33025, 0x00008101
- Label_02: 33026, 0x00008102
- Label_03: 33027, 0x00008103

The stimulation code are used as follows: *ExperimentStart* and *ExperimentStop* indicate the begining and the end of the session. A trial start with a *Label_XX* stimulation code indicating the class of the example, there is a 3s pause before the audio cue indicating the stimulus to focus. The audio cue onset is indicated by *VisualStimulationStart*, this is the start of the trial. The end of the trial take place 5s after and is indicated by *VisualStimulationStop*. *Label_00* is for resting class, *Label_01* is for 13Hz stimulation, *Label_02* is for 21Hz stimulation and *Label_03* is for 17Hz stimulation.

## Bibliography

[1] M. Baklouti, P. A. Guyot, E. Monacelli, and S. Couvet. _Force controlled upper-limb powered exoskeleton for rehabilitation,_ in Intelligent Robots and Systems (IROS), 2008, p. 4202.

[2] H. Martin, S. Chevallier, and E. Monacelli, _Fast calibration of hand movement-based interface for arm exoskeleton control,_ in European Symposium on Artificial Neural Networks (ESANN), 2012, pp. 573– 578.

[3] A. Schlogl, _GDF - A general dataformat for biosignals_, http://arxiv.org/abs/cs/0608052
