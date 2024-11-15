# Protein-Folding-Prediction-Model
The model simulates protein folding by combining Dynamic Programming (DP) and Reinforcement Learning (RL) to predict realistic, biologically plausible structures. It utilizes physics-based properties such as hydrophobicity, charge, and spatial distance to estimate and optimize energy-efficient folding pathways.
Features
Data Processing:

Loads protein sequences from a UniProt dataset in FASTA format.
Supports compressed datasets (.fasta.gz).
Energy-Based Interactions:

Incorporates hydrophobicity and charge properties for amino acids.
Calculates interaction energies using a physics-inspired energy function.
Dynamic Programming (DP):

Estimates low-energy configurations by analyzing residue interactions within a sliding window.
Provides a baseline for energy-efficient folding.
Reinforcement Learning:

Custom RL environment simulates residue movements in 3D space.
Uses Proximal Policy Optimization (PPO) to train an agent for optimal folding strategies.
Rewards realistic configurations and penalizes steric clashes.
Output:

Predicts the 3D coordinates of the folded protein structure.
Results can be visualized or compared against known structures.
Getting Started
Prerequisites
Python 3.8 or higher
Libraries:
Biopython (pip install biopython)
NumPy (pip install numpy)
Stable-Baselines3 (pip install stable-baselines3)
Shimmy (pip install shimmy>=0.2.1)
Gym (pip install gym)
Dataset
Download the UniProt Swiss-Prot dataset (uniprot_sprot.fasta.gz) and place it in the desired directory.
Running the Model
Step 1: Load Protein Sequence

Update file_path in the script to point to the UniProt dataset location.
The model will load the first protein sequence for folding simulation.
Step 2: Dynamic Programming Initialization

Run the DP module to calculate an approximate low-energy configuration.
This step is optional and primarily provides a reference.
Step 3: Reinforcement Learning Training

The RL environment (ProteinFoldingEnv) initializes the protein in an unfolded state.
PPO learns optimal folding strategies by interacting with the environment.
Step 4: Extract Results

After training, the predicted 3D coordinates of the folded structure are saved or printed.
Key Functions
get_energy(residue1, residue2, distance): Calculates energy between two residues based on hydrophobicity, charge, and distance.
ProteinFoldingEnv: Custom RL environment for simulating folding.
train_rl_model: Trains the RL agent using PPO to learn optimal folding policies.
Example Output
plaintext
Copy code
Number of sequences loaded: 1
Predicted structure coordinates: [[0.0, 0.0, 0.0], [1.5, 0.0, 0.0], ...]
Future Enhancements
Incorporate additional physical constraints, such as torsion angles and secondary structure preferences.
Extend to multi-sequence analysis and comparative folding validation.
Improve RL training efficiency using hierarchical or meta-RL approaches.
Contact
For questions or contributions, please reach out via email jugraunaqsingh@gmail.com or submit a pull request.
