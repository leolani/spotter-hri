# SPOTTER HRI Data
This repository contains data from Human-Robot Interaction experiments using the SPOTTER Framework (Kruijt et al. 2024). The data contains human-robot task-based dialogue about a game in which the goals is for the human and chatbot to verbally identify the positions of characters in a picture, without seeing each other's picture. The game is made up of 15 rounds, with each round containing 5 characters which must be identified. The data can be used to study convention formation, common ground, referring expressions, and coreference resolution. For more information on the framework, see the paper.

## Data structure

Each folder inside the folder `experiments` contains the dialogue of one set of human-robot interactions, divided into three human-robot interaction sessions. Folders are ordered by participant number (1-35). Inside the folder are three sessions, which are separate interactions between the same human-robot pair. A .csv and .json version is available of each data file.

_The data is structured as follows:_

Each entry contains one utterance. The utterance is annotated with the following annotations:
- **start**: The start time of the utterance in seconds measuring from the beginning of the dialogue
- **end**: The end time of the utterance in seconds
- **text**: The text representation of the utterance
- **speaker**: The source of the utterance, either `robot` or `human`
- **robot-guess**: The character ID of the character that the robot guessed as the referent of the human's description: character ID between 1-40
- **certainty**: The certainty between 0-1 that the robot has about its guess
- **status**: The output status representing the result of the robot's reference resolution attempt: either `SUCCESS_HIGH`, `SUCCESS_LOW`, `MATCH_PREVIOUS`, `NO_MATCH`, or `MATCH_MULTIPLE`
- **round**: The current round of the game: number between 1-6
- **transaction unit**: Index number of the current transaction unit, a unit representing the set of utterances required to identify and locate one character
- **position**: The position of the character that is currently being discussed in the human's picture
- **gold character**: The correct ID of the character that is currently being discussed
- **final guess**: The chatbot's final guess for a character
- **circle**: The circle that the character currently being discussed belongs to. Either `inner` or `outer`, respectively representing whether the character appears in multiple rounds or not
- **robot_correct**: The veracity of the robot's final guess, comparing `final guess` to `gold character`. Either `correct` or `incorrect`
- **tu_relation**: The relation between two subsequent utterances in a transaction unit, representing the dialogue act of the utterance
- **hum-selection**: The position in the robot's scene that the human selected after completing a transaction unit to identify the position of a character

## Citation
When using the data, please cite the following PhD thesis:

`@article{kruijt2025impact,
  title={The Impact of Common Ground on Referring Expressions in Human-Robot interaction},
  author={Kruijt, Jaap Matthijs},
  year={2025}
}`

Additionally, when using the SPOTTER framework, please cite the following paper:
`@inproceedings{kruijt2024spotter,
  title={SPOTTER: A Framework for Investigating Convention Formation in a Visually Grounded Human-Robot Reference Task},
  author={Kruijt, Jaap and van Minkelen, Peggy and Donatelli, Lucia and Vossen, Piek TJM and Konijn, Elly and Baier, Thomas},
  booktitle={Proceedings of the 2024 Joint International Conference on Computational Linguistics, Language Resources and Evaluation (LREC-COLING 2024)},
  pages={15202--15215},
  year={2024}
}`
