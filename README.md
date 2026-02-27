# Sweepmine.TM

A fast Minesweeper AI with success rate near frontier research models. The solver abstracts the Minesweeper grid into a constraint satisfaction problem (CSP), which is solved using logical deduction, Gaussian-elimination, and recursive backtracking. The solutions to the CSP are used to determine a garunteed safe move (if any exists) or a probabilistically optimal move otherwise. 

The solver also supports toroidal maps (wrap-around) and weighted mines. This project was originally intended as a problem for a contest setting (see `statement.pdf`). 

## Directory

| Folder | Contents |
|---------|-----------|
| `/build` | Executables |
| `/data` | Input/output files for solver |
| `/draft` | Previous iteration |
| `/run` | Scripts to benchmark and visualise |
| `/src` | Underlying C++ |

## Installation
Requirements for usage:

- g++ with C++20
- make
- Python 3.6+

First, clone the repository:

``` bash
git clone https://github.com/SlappyPenguin/Sweepmine.TM.git
cd Sweepmine.TM
```

Compile all programs using the top-level Makefile:

``` bash
cd run
make
```

To run a benchmark on the solver:

``` bash
cd run
python simple_benchmarker.py
# Example
Enter level (easy/medium/hard): hard
Enter number of games to play: 1000
```

A benchmarker with more custom parameters (`run/benchmarker.py`) is also available. After benchmarking, visualise the final game:

``` bash
cd run
python visualiser.py
```

Note that individual game spots can also be solved using the ungraded programs (see `/build`).


## Technical Details

### Map Generation

When `sweepmine` is not in debug mode (i.e. provided a grid), pseudo-adaptive automatic map generation kicks into play. The first cell revealed by the algorithm will always be a non-mine. However, it is **not** guaranteed that the map is solvable from there using pure logic.

Mines are placed via picking a set of random non-

### (1) Logical Reduction

This is only perfomed when mines are non-weighted.

TODO

### (2) Gaussian Elimination

This is only performed when mines are non-weighted.

TODO

### (3) Probabilistic Backtrack

TODO