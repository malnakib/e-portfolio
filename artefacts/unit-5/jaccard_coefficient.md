# Jaccard Coefficient Calculations — Unit 5

## Data

| Name | Gender | Fever | Cough | Test-1 | Test-2 | Test-3 | Test-4 |
|------|--------|-------|-------|--------|--------|--------|--------|
| Jack | M      | Y     | N     | P      | N      | N      | A      |
| Mary | F      | Y     | N     | P      | A      | P      | N      |
| Jim  | M      | Y     | P     | N      | N      | N      | A      |

## Binary Conversion (Y/P = 1, N/A = 0, Gender ignored)

| Name | Fever | Cough | Test-1 | Test-2 | Test-3 | Test-4 |
|------|-------|-------|--------|--------|--------|--------|
| Jack | 1     | 0     | 1      | 0      | 0      | 0      |
| Mary | 1     | 0     | 1      | 0      | 1      | 0      |
| Jim  | 1     | 1     | 0      | 0      | 0      | 0      |

## Jaccard Coefficient Formula

J(A, B) = matching positive pairs / (total - matching negative pairs)

## Results

### (Jack, Mary)
- Both positive: 2 (Fever, Test-1)
- One or both positive: 3 (Fever, Test-1, Test-3)
- **J = 2/3 = 0.67**

### (Jack, Jim)
- Both positive: 1 (Fever)
- One or both positive: 3 (Fever, Cough, Test-1)
- **J = 1/3 = 0.33**

### (Jim, Mary)
- Both positive: 1 (Fever)
- One or both positive: 4 (Fever, Cough, Test-1, Test-3)
- **J = 1/4 = 0.25**

## Observation

Jack and Mary are the most similar pair (0.67), sharing both fever and a positive Test-1 result. Jim and Mary are the least similar (0.25) since they only share the fever symptom while differing on most other tests. This exercise showed how the Jaccard coefficient works for binary data and why it ignores matching negatives — two patients not having a symptom does not make them similar.
