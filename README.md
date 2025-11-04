


 Hangman AI Agent — Hybrid HMM + Reinforcement Learning

This project implements a hybrid system that combines a Hidden Markov Model (HMM) with Reinforcement Learning (RL) to play the Hangman word-guessing game intelligently. The system learns letter patterns from a text corpus and optimizes guessing strategies to minimize errors and maximize success rate.
 Project Overview

The Hangman AI integrates two main components:

1. Hidden Markov Model (HMM):
   Learns probabilistic patterns of letters and predicts likely letters based on masked word states.

2. Reinforcement Learning (RL):
   Trains an agent through trial and error to select the most effective letter guesses by maximizing rewards over multiple games.

 Components
 Hidden Markov Model (HMM)

* Analyzes a given corpus (corpus.txt) to learn letter dependencies and positional frequencies.
* Implements a multi-level approach including:

  * Bigrams and trigrams.
  * Vowel-consonant transitions.
  * Position-based probabilities (start, middle, end of words).
* Incorporates special handling for common English patterns such as "qu" and double letters.
* Generates letter probability distributions used by the RL agent during exploration and exploitation.

Reinforcement Learning Agent

* State: Includes the masked word, guessed letters, number of wrong guesses, and remaining lives.
* Actions: Letters that have not yet been guessed.
* Reward Function:

  * Correct guess: +10
  * Wrong guess: -5
  * Repeated guess: -10
  * Win: +100
  * Loss: -50
* Uses an epsilon-greedy strategy with decay to balance exploration and exploitation.
* Integrates HMM probabilities into the Q-learning decision process for guided exploration.

 Training and Evaluation

* The agent is trained over multiple episodes, gradually improving its decision-making.
* Performance metrics include:

  * Success rate
  * Average number of wrong guesses
  * Average number of repeated guesses
* Evaluation plots track the learning curve (reward per episode).

 Results Summary

* Final success rate: approximately 31.8%
* Average wrong guesses: 4.56
* Repeated guesses: 0 (effectively handled by logic)
* Stronger performance observed for longer words (length ≥ 10).
* The combination of HMM and RL shows potential but requires further optimization of state representation and reward structure.

Future Improvements

* Enhance HMM with richer linguistic features or contextual embeddings.
* Refine the RL state representation to include positional and structural information.
* Implement advanced methods such as Deep Q-Networks (DQN) or Prioritized Experience Replay.
* Use curriculum learning to train from easier to harder words.
* Conduct systematic hyperparameter tuning to improve stability and performance.

 Files Included

* final_test.ipynb: Jupyter notebook containing model construction, training, and evaluation.
* corpus.txt: Text corpus used for HMM training.
* Analysis_Report.pdf: Detailed report discussing observations, design choices, and insights.
* README.md: Project documentation file.

 How to Run

1. Clone the repository to your local system:
   git clone [https://github.com/yourusername/HangmanAI.git](https://github.com/yourusername/HangmanAI.git)

2. Navigate to the project directory:
   cd HangmanAI

3. Install required dependencies:
   pip install -r requirements.txt

4. Open and run the notebook:
   jupyter notebook final_test.ipynb


Would you like me to also create a short “requirements.txt” list for it (so your repo runs smoothly)?
