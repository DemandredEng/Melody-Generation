# Melody-Generation
An autonomous melody generation LSTM model.

Uses publicly available datasets at http://www.esac-data.org/ as input to train and generate an LSTM model, which is then saved in model.h5. To generate a melody, run the melody_generator file, which is output as a midi file (generated_melody.mid).  

The composition is represented as a sequence of symbols, where each symbol corresponds to a note or a rest in the melody. The values used in the composition are as follows:

* Notes: The integer MIDI value of the note. For example, if a note corresponds to C4, its MIDI value (60) will be used as the symbol.
* Rests: The value 'r' is used to represent rests in the composition. A rest indicates a period of silence in the melody.
* Underscore (_): An underscore character is used to represent the continuation of a note. Since the model operates on fixed-length sequences, a note with a longer duration is split into multiple time steps. Each time step is represented by an underscore, and the same MIDI value of the original note is repeated in each of these time steps.

The 'mapping.json' file contains the mapping of symbols to MIDI values. To obtain variations in the composition, modify the seed in the 'melody_generator' file (consider looking in the mapping.json file for seed value ideas).
