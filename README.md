# TOPSIS - Text Sentence Similarity

## Overview
This repository contains a Python implementation of the TOPSIS method, a multi-criteria decision analysis technique. The script evaluates multiple models or alternatives based on various metrics, assigns a performance score to each, and ranks them according to their closeness to the ideal solution.

---

## Features
- Normalize data for comparison across metrics.
- Weight metrics and account for their positive/negative impacts.
- Calculate distances from ideal best and worst solutions.
- Rank models or alternatives based on performance scores.

---

## Requirements
The script requires the following Python libraries:
- numpy
- pandas

Clone the repository:
   ```bash
   git clone https://github.com/tanveer-code26/Topsis-Text-Similarity-Tanveer-Singh-102216133
   ```
   
To install the dependencies, use:
```bash
pip install numpy pandas
```

## Usage
Run the script using the command line with the following format:
```bash
python topsis.py <input_file> <weights> <impacts> <output_file>
```

### Arguments
1. **input_file**: Path to the input CSV file. This file must contain columns for the metrics:
   - Cosine Similarity
   - Jaccard Similarity
   - Euclidean Distance
   - Manhattan Distance
   - BLEU Score
   - ROUGE Score
   - Perplexity
   
   Additionally, it must contain columns labeled `Text` and `Models`.

2. **weights**: A comma-separated list of weights for the seven metrics (e.g., `1,1,1,1,1,1,1`). The weights must sum up to 1 after normalization.

3. **impacts**: A comma-separated list of impacts for the seven metrics (`+` for positive impact, `-` for negative impact). For example: `+, +, -, -, +, +, -`.

4. **output_file**: Path to the output CSV file where results will be saved.

### Example
```bash
python text_similarity.py data.csv 0.3,0.2,0.1,0.1,0.1,0.1,0.1 +,+,-,-,+,+,- results.csv
```

---

## Input File Format
The input CSV file should have the following structure:

| Text       | Models  | Cosine Similarity | Jaccard Similarity | Euclidean Distance | Manhattan Distance | BLEU Score | ROUGE Score | Perplexity |
|------------|---------|-------------------|---------------------|---------------------|---------------------|------------|-------------|------------|
| Text A     | Model 1 | 0.8               | 0.7                 | 0.6                 | 0.5                 | 0.9        | 0.85        | 10         |
| Text A     | Model 2 | 0.75              | 0.68                | 0.63                | 0.48                | 0.88       | 0.82        | 12         |
| Text B     | Model 1 | 0.7               | 0.72                | 0.65                | 0.55                | 0.85       | 0.80        | 11         |
| ...        | ...     | ...               | ...                 | ...                 | ...                 | ...        | ...         | ...        |

---

## Output File Format
The output CSV file will have the following structure:

| Text       | Models  | Cosine Similarity | Jaccard Similarity | Euclidean Distance | Manhattan Distance | BLEU Score | ROUGE Score | Perplexity | Performance_Score | Rank |
|------------|---------|-------------------|---------------------|---------------------|---------------------|------------|-------------|------------|-------------------|------|
| Text A     | Model 1 | 0.8               | 0.7                 | 0.6                 | 0.5                 | 0.9        | 0.85        | 10         | 0.78              | 1    |
| Text A     | Model 2 | 0.75              | 0.68                | 0.63                | 0.48                | 0.88       | 0.82        | 12         | 0.72              | 2    |
| Text B     | Model 1 | 0.7               | 0.72                | 0.65                | 0.55                | 0.85       | 0.80        | 11         | 0.76              | 1    |
| ...        | ...     | ...               | ...                 | ...                 | ...                 | ...        | ...         | ...        | ...               | ...  |

---

## Error Handling
- The script validates input for the correct number of weights and impacts.
- Raises errors for missing or improperly formatted files.
- Displays clear messages for invalid usage or unexpected issues.

---

## Notes
- Ensure the weights and impacts are specified in the correct order matching the metrics.
- Normalization of weights is handled automatically by the script.
- Missing values in the input file may result in errors.

---

## License
This project is licensed under the MIT License.

---

## Contributors
[Tanveer Singh] - [https://github.com/tanveer-code26]
