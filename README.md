# DNA Pattern Matching: KMP, Boyer-Moore, and Rabin-Karp
# DNA Pattern Matching: KMP, Boyer-Moore, and Rabin-Karp

A comparative analysis of three classical string-matching algorithms applied to DNA sequence alignment.

## Overview

This repository contains the implementation and evaluation of three fundamental pattern-matching algorithms:
- **Knuth-Morris-Pratt (KMP)**
- **Boyer-Moore (BM)**
- **Rabin-Karp (RK)**

These algorithms are analyzed in the context of DNA sequence alignment, evaluating their performance on genomic data with a small alphabet size {A, C, G, T}.

## Research Paper

📄 [String matching for DNA matching.pdf](String%20matching%20for%20DNA%20matching.pdf)

**Authors:** Arnav Khajuria, Jagmohan Sharma, Arnav Nargotra  
**Department:** Computer Science & Engineering, MIET  
**Date:** November 29, 2025

### Key Findings

- **KMP** provides the most stable and predictable performance with linear execution time
- **Boyer-Moore** performs competitively but offers limited advantages in repetitive DNA sequences
- **Rabin-Karp** exhibits the lowest memory footprint but suffers from increased execution time due to hashing overhead

## Repository Structure

```
dna-pattern-matching/
│
├── String matching for DNA matching.pdf    # Research paper
├── TC.ipynb                                 # Time Complexity Analysis
├── SC.ipynb                                 # Space Complexity Analysis
├── README.md                                # This file
└── requirements.txt                         # Python dependencies (optional)
```

## Implementation

### Algorithms Implemented

#### 1. Knuth-Morris-Pratt (KMP)
- Uses LPS (Longest Prefix Suffix) preprocessing
- Time Complexity: O(n + m)
- Space Complexity: O(m)

#### 2. Boyer-Moore (BM)
- Implements bad-character and good-suffix heuristics
- Best Case: O(n/m)
- Average Case: O(n)
- Space Complexity: O(σ + m)

#### 3. Rabin-Karp (RK)
- Uses rolling hash functions
- Average Case: O(n + m)
- Space Complexity: O(1)

### Code Files

**TC.ipynb** - Time Complexity Benchmarking
- DNA sequence generation
- Algorithm implementations
- Performance measurement (1,000 to 50,000 characters)
- Time complexity visualization

**SC.ipynb** - Space Complexity Benchmarking
- Memory usage tracking using `tracemalloc`
- Space complexity comparison
- Memory footprint visualization

## Getting Started

### Prerequisites

```bash
pip install matplotlib numpy jupyter
```

### Running the Notebooks

1. **Time Complexity Analysis:**
   ```bash
   jupyter notebook TC.ipynb
   ```

2. **Space Complexity Analysis:**
   ```bash
   jupyter notebook SC.ipynb
   ```

### Usage Example

```python
from TC import kmp, boyer_moore, rabin_karp, generate_dna

# Generate DNA sequence
text = generate_dna(10000)
pattern = "ACGTACGTACGT"

# Run algorithms
kmp(text, pattern)
boyer_moore(text, pattern)
rabin_karp(text, pattern)
```

## Results

### Time Complexity
- KMP maintains consistent O(n + m) performance across all input sizes
- Boyer-Moore converges with KMP for larger sequences
- Rabin-Karp shows higher execution times due to hash computation overhead

### Space Complexity
- Rabin-Karp: Lowest memory usage (O(1) auxiliary space)
- KMP: Moderate memory usage (O(m) for LPS table)
- Boyer-Moore: Comparable to KMP with occasional spikes

## Visualizations

The repository includes two main graphs:

1. **Time Complexity Comparison** - Shows execution time vs. DNA sequence length
2. **Space Complexity Comparison** - Displays memory usage across different input sizes

## Applications

- Gene identification
- Motif discovery
- High-throughput sequencing analysis
- Genomic pattern matching
- Bioinformatics research

## Theoretical Complexity

| Algorithm | Time (Best) | Time (Avg) | Time (Worst) | Space |
|-----------|-------------|------------|--------------|-------|
| KMP | O(n + m) | O(n + m) | O(n + m) | O(m) |
| Boyer-Moore | O(n/m) | O(n) | O(n·m) | O(σ + m) |
| Rabin-Karp | O(n + m) | O(n + m) | O(n·m) | O(1) |

Where:
- n = text length
- m = pattern length
- σ = alphabet size (4 for DNA)

## Citation

If you use this code or findings in your research, please cite:

```bibtex
@article{khajuria2025dna,
  title={Optimizing DNA Sequence Alignment Using the KMP Algorithm, Boyer-Moore, and Rabin-Karp},
  author={Khajuria, Arnav and Sharma, Jagmohan and Nargotra, Arnav},
  journal={MIET CSE Department},
  year={2025}
}
```

## References

1. Knuth, D. E., Morris, J. H., & Pratt, V. R. (1977). Fast pattern matching in strings. *SIAM Journal on Computing*, 6(2), 323-350.

2. Boyer, R. S., & Moore, J. S. (1977). A fast string searching algorithm. *Communications of the ACM*, 20(10), 762-772.

3. Karp, R. M., & Rabin, M. O. (1987). Efficient randomized pattern-matching algorithms. *IBM Journal of Research and Development*, 31(2), 249-260.

4. Gusfield, D. (1997). *Algorithms on Strings, Trees, and Sequences: Computer Science and Computational Biology*. Cambridge University Press.

## License

This project is available for academic and research purposes.

## Contact

For questions or collaboration:
- Arnav Khajuria
- Jagmohan Sharma
- Arnav Nargotra

Department of Computer Science & Engineering, MIET

---

**Note:** This research demonstrates that KMP is the most practical algorithm for large-scale DNA sequence alignment due to its predictable linear performance and modest space requirements.
