# Log Explanation

[This log file](./detailed_repro_logs(2.17.20).txt) contains full repro steps, from main README

## Results

|           | Current repo state, running `npm run vti` | After `mv src/components/ComplexComponent4.vue src/components/ComplexComponent4.txt`, then running `npm run vti` |
|-----------|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Failures  | 5                                            | 0                                                                                                                   |
| Successes | 1                                            | 6                                                                                                                   |

