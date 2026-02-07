# LeaderBoard_using_SkipLists
Efficient leaderboard system implemented using a Skip List, supporting fast player ranking, score updates, and top-N queries for large datasets.

Skip Lists provide probabilistic balancing, enabling performance comparable to balanced trees while
being simpler to implement.

---

## Features

- Efficient leaderboard operations using **Skip List**
- Supports:
  - Adding new players
  - Updating player scores
  - Deleting players
  - Searching player rank
  - Retrieving Top-N players
- Handles **tie-breaking** using join order
- Optimized for **large datasets (hundreds of thousands of players)**
- CSV-based bulk data loading

---

## Data Structures Used

- **Skip List**
  - Multiple forward pointers per node
  - Probabilistic level assignment
  - Span values for efficient rank calculation
- **Hash Map**
  - Stores player name to (score, tie-breaker) mapping for O(1) access

---

## Design Overview

Each player is represented as a node in the skip list, ordered by:
1. Higher score (descending)
2. Tie-breaker (earlier join gets higher rank)

The leaderboard maintains:
- Fast traversal across multiple levels
- Accurate rank calculation using span counters
- Stable ordering even during score updates

---

## Time Complexity

| Operation            | Average Time |
|---------------------|--------------|
| Insert Player       | O(log n)     |
| Delete Player       | O(log n)     |
| Update Score        | O(log n)     |
| Search Rank         | O(log n)     |
| Top-N Retrieval     | O(n)         |

---

## Technologies Used

- Python
- Skip List (custom implementation)
- CSV file handling

---

## Usage

1. Prepare a CSV file with the following format:
   ```csv
   name,score
   player1,1200
   player2,950
