# optimal_GAP_solver

# Optimal Service Placement using Generalized Assignment Problem (GAP)

This project implements an **Optimal Method using Pulp(python library)** for solving the **Resource Allocation in Edge Computing** problem, formulated as a **Generalized Assignment Problem (GAP)**. The objective is to assign users to servers such that:

- Each user is assigned to exactly one server.
- The total utility is maximized.
- Server resource constraints are not violated.

## 📄 Problem Statement

The problem is adapted from:  
**"An efficient approximation for the generalized assignment problem"**  
_Cohen, Reuven, Liran Katzir, and Danny Raz_ (Information Processing Letters, 2006)

- Each dataset contains multiple instances of user-server assignment problems.
- The utility, VM allocation, and server capacity data are provided in OR-Library format.

The full problem description and datasets are available at:  
[https://people.brunel.ac.uk/~mastjjb/jeb/orlib/gapinfo.html](https://people.brunel.ac.uk/~mastjjb/jeb/orlib/gapinfo.html)

## 📌 Approach

- The code uses [PuLP](https://pypi.org/project/PuLP/) to solve each GAP instance optimally.
- Each instance is modeled as a Binary Integer Linear Program (BILP).
- The objective function maximizes total utility.
- Constraints ensure:
  - Each user is assigned to one server.
  - Server resource usage does not exceed capacity.

## 🧠 How it Works

### Dataset Format

Each `.txt` file contains:
1. Number of instances
2. For each instance:
   - Number of servers and users
   - Utility matrix (servers × users)
   - VM allocation matrix (servers × users)
   - Server capacities (list)

### Output

For each instance:
- Task Assignments (user → server)
- Total Optimal Utility

### Example Output

```
Processing Instance 1 from gap1.txt  
Task Assignments: [1, 2, 0, 3, ...]  
Total Optimal Utility: 562.0
```

## 🚀 Getting Started

### 1. Install Dependencies

```bash
pip install pulp
```

### 2. Run the Code

```bash
jupyter notebook optimal_gap_solver.ipynb
```

Make sure your dataset files are stored in the correct folder (e.g., `gap_dataset_files`).
make sure the file path is correct , do modify if needed
### 3. File Structure

```
project/
│
├── optimal_gap_solver.ipynb    # Main Jupyter notebook
├── gap_dataset_files/          # Folder containing gap1.txt, gap2.txt, ...
├── README.md                   # This file
```

## 🧾 References

- Cohen, R., Katzir, L., & Raz, D. (2006).  
  [An efficient approximation for the generalized assignment problem](https://www.sciencedirect.com/science/article/abs/pii/S0020019006001931)
- OR-Library GAP datasets:  
  [https://people.brunel.ac.uk/~mastjjb/jeb/orlib/gapinfo.html](https://people.brunel.ac.uk/~mastjjb/jeb/orlib/gapinfo.html)
