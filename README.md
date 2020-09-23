# Aerogel Replay

A ROOT script that extracts data from the beam raw data and exports series of corresponding PMT histograms. Every output ROOT file contains seven Positive and seven negative PMT histograms.
There are two ROOT scripts in the repository. Script "replay.c" uses the TTreeReader interface to iterate the ROOT trees. It works quick but will more likely crash if the input ROOT files are corrupt.
A better ROOT TFile error handling is implemented in the script "replayConv.c" which uses a conventional TTRee::GetEntry() mechanism for reading the tree. The downside of this mechanism is the speed which is about 10 times more slow compared to the TTreeReader.

## How to use

1. Checkout the script "replay.c" or "replayConv.c" to the folder where the output data will be located.
2. Tweak the RegExp input filename pattern on the line 14 of the script to match the desired name of the input files.
2. Run the script with the command:

```
root 'replayConv.c("/path/to/the/root/replay/files")'
```
3. Script will automatically scan the directory for the input files and start processing them.
