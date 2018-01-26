Model files from the paper:

F. Zeldenrust, P. Chameau, W. J. Wadman, ‘Spike and Burst Coding in
Thalamocortical Relay Cells’, PLoS Computational Biology, 2018

Questions on how to use this model should be directed to
f.zeldenrust at neurophysiology.nl

Synopsis:
————————————————————————————————————————————————————————————————————————————-

Mammalian thalamocortical relay (TCR) neurons switch their firing
activity between a tonic spiking and a bursting regime. In a combined
experimental and computational study, we investigated the features in
the input signal that single spikes and bursts in the output spike
train represent and how this code is influenced by the membrane
voltage state of the neuron. Identical frozen Gaussian noise current
traces were injected into TCR neurons in rat brain slices to adjust,
fine-tune and validate a three-compartment TCR model cell (Destexhe et
al. 1998, accession number 279). Three currents were added: an
h-current (Destexhe et al. 1993,1996, accession number 3343), a
high-threshold calcium current and a calcium- activated potassium
current (Huguenard & McCormick 1994, accession number 3808). The
information content carried by the various types of events in the
signal as well as by the whole signal was calculated. Bursts
phase-lock to and transfer information at lower frequencies than
single spikes. On depolarization the neuron transits smoothly from the
predominantly bursting regime to a spiking regime, in which it is more
sensitive to high-frequency fluctuations. Finally, the model was used
to in the more realistic “high-conductance state” (Destexhe et
al. 2001, accession number 8115), while being stimulated with a
Poisson input (Brette et al. 2007, Vogels & Abbott 2005, accession
number 83319), where fluctuations are caused by (synaptic) conductance
changes instead of current injection. Under “standard” conditions
bursts are difficult to initiate, given the high degree of
inactivation of the T-type calcium current. Strong and/or precisely
timed inhibitory currents were able to remove this inactivation.

Use:
————————————————————————————————————————————————————————————————————————————-

There are three folders. For each folder: extract the archive, run
nrnivmodl in the channels directory (linux/unix) or mknrndll (mswin or
mac os x) (see
http://senselab.med.yale.edu/ModelDB/NEURON_DwnldGuide.html for more
help) to compile the channels, and run the .hoc file.

1) The ‘current clamp’ folder, simulates the experiments. It will
result in the voltage traces (and resulting spike trains) used in
figures 9-11. The used ‘holding currents’ are set as ‘El1.stim.amp’
(i.e. the amplitude of the current injected via electrode 1). The data
can be saved with procedures ‘fileopen()’ and ‘slaop()’.

2) In the ‘influence_ih_iT’ folder, the current-clamp experiments are
repeated, but now the h-current is reduced by a factor (see figure 12
of the paper), that can be set at the top of the .hoc-file (as well as
the ‘holding potential’ or ‘membrane state’ Vhold). This will then
automatically adjust the mean input current (‘El1.stim.amp’), the
h-current conductivity and change the relevant filenames for saving
(procedures ‘fileopen()’ and ‘slaop()’).

3) In the ‘high_conductance_state’, the experiment as shown in figure
13 of the paper is simulated. A ‘high-conductance-state ion channel’
(fl) is used to either simulate a ‘classic’, no or an inhibitory
high-conductance-state. Moreover, two (exponential) synapses that
receive (the same) Poisson spike trains, ‘Esynapse’ and ‘Esynapse_i’
are added to the dendrite. Again, ‘fileopen()’ and ‘slaop()’ can be
used to save the results.
