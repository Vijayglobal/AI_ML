Datasheet for BBO Capstone Project Dataset :

1) Motivation
This dataset was created to support a black-box optimisation (BBO) task under a strict evaluation budget.
It records the full query history and corresponding function evaluations across multiple rounds for eight unknown synthetic objective functions.  
The dataset enables analysis of how optimisation strategies evolve over time as more information becomes available and supports experimentation with surrogate models, acquisition strategies and interpretability mechanisms.

3) Composition
- Inputs (X): Continuous vectors in the range [0, 1], with dimensionality varying from 2D to 8D depending on the function.
- Outputs (y): Scalar objective values returned by the black-box functions.
- Size: Each function starts with an initial dataset and is augmented by one query per round.  
  At the current stage, each function contains approximately 19 data points.
- Gaps: The dataset is sparse by design and does not represent uniform coverage of the input space.

4) Collection Process
Data was collected iteratively through the BBO capstone project portal.  
At each round:
1. A surrogate model was trained using all previously observed data.
2. A candidate set was generated (grid-based in low dimensions, Sobol sampling in higher dimensions).
3. A single query point per function was selected using an acquisition strategy balancing exploration and exploitation.
4. The black-box function was evaluated and the result appended to the dataset.
The collection process spans ten rounds and reflects a gradual shift from exploration to refinement.

5) Preprocessing and Intended Use
- Preprocessing:
  - Inputs were standardised using `StandardScaler`.
  - Outputs were optionally transformed using the Yeo–Johnson transform to stabilise learning for near-zero or skewed targets.
- Intended Use:
  - Studying surrogate-based optimisation strategies.
  - Analysing decision-making under limited data.
  - Demonstrating transparency and interpretability in optimisation.
- Inappropriate Use:
  - Any real-world decision-making or deployment beyond synthetic benchmarking.
    
6) Distribution and Maintenance
The dataset is stored in a public GitHub repository as part of the BBO capstone project.  
Each round’s data is versioned, and updates are logged explicitly.  
The repository owner is responsible for maintenance, corrections and documentation updates.
