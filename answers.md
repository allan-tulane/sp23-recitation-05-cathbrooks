# CMPS 2200 Reciation 5
## Answers

**Name:** Catherine Brooks
**Name:** David Webster



Place all written answers from `recitation-06.md` here for easier grading.







- **1b.**
- Quick sort and selection sort are both bound by their worst case run time of O(n^2), although quick sort has an average of O(n*log(n)). 
- 
for qsort-fixed-pivot ssort on an already sorted list:

|    n |   qsort-fixed-pivot |    ssort |
|------|---------------------|----------|
|   10 |               0.026 |    0.012 |
|   50 |               0.267 |    0.078 |
|  100 |               2.037 |    0.267 |
|  200 |               5.289 |    1.246 |
|  500 |              26.633 |   48.697 |
| 1000 |             159.784 |   69.473 |
| 1500 |             479.580 |  127.724 |
| 2000 |             806.111 |  174.838 |
| 3000 |            1787.795 |  495.983 |
| 5000 |            4898.241 | 1427.336 |


for qsort-fixed-pivot and ssort on a randomized list:

|    n |   qsort-fixed-pivot |    ssort |
|------|---------------------|----------|
|   10 |               0.021 |    0.017 |
|   50 |               0.115 |    0.119 |
|  100 |               0.258 |    0.415 |
|  200 |               0.565 |    1.426 |
|  500 |               1.374 |    7.657 |
| 1000 |               2.921 |   80.155 |
| 1500 |               4.835 |  124.976 |
| 2000 |               6.416 |  303.520 |
| 3000 |              10.586 |  611.107 |
| 5000 |              17.824 | 1784.224 |

Ssort shows exponential growth as n increases, as expected. It performed slightly slower on randomized lists.

Qsort-fixed-pivot ran much faster on input of random permutations rather than sorted permutations, notably closer to its average O(n * log(n)). This is because a sorted list is a worst case scenario for qsort-fixed-python, giving it O(n^2) in that instance.




for Qsort-random-pivot v ssort on a sorted list

|    n |   qsort-random-pivot |    ssort |
|------|----------------------|----------|
|   10 |                0.030 |    0.013 |
|   50 |                0.188 |    0.115 |
|  100 |                0.251 |    0.263 |
|  200 |                0.520 |    1.082 |
|  500 |                1.756 |   22.708 |
| 1000 |                3.507 |   30.839 |
| 1500 |                6.604 |  100.021 |
| 2000 |               50.921 |  217.451 |
| 3000 |               11.789 |  517.559 |
| 5000 |               59.158 | 1545.841 |


for qsort-random-pivot v ssort on a randomized list

|    n |   qsort-random-pivot |    ssort |
|------|----------------------|----------|
|   10 |                0.032 |    0.019 |
|   50 |                0.139 |    0.093 |
|  100 |                0.233 |    0.325 |
|  200 |                0.579 |    1.302 |
|  500 |                1.674 |    7.103 |
| 1000 |                3.678 |   80.601 |
| 1500 |                6.058 |  126.751 |
| 2000 |               57.320 |  229.105 |
| 3000 |               12.620 |  656.583 |
| 5000 |               19.673 | 1685.771 |


Since the pivot is now random for qsort, it does not matter whether the input list is already sorted or not, the runtimes are basically the same and bounded by O(n*log(n)). This is a better choice than selection sort in both input scenarios, and better than qsort-fixed-pivot on an already sorted list. Notably, qsort-fixed-pivot and qsort-random-pivot have similar runtimes the case of a randomized input list.




- **1c.**


the worst case for Timsort is O(nlogn) compared to the worst case of qsort-random-pivot of O(n^2).



for quicksort-random-pivot v Timsort on an already sortes list

|    n |   qsort-random-pivot |   Timsort |
|------|---------------------|-----------|
|   10 |               0.036 |     0.004 |
|   50 |               0.155 |     0.002 |
|  100 |               0.296 |     0.003 |
|  200 |               0.660 |     0.005 |
|  500 |               1.763 |     0.010 |
| 1000 |               7.983 |     0.039 |
| 1500 |               6.209 |     0.026 |
| 2000 |              22.767 |     0.035 |
| 3000 |              25.949 |     0.057 |
| 5000 |              24.832 |     0.071 |




for qsort-fixed-pivot and Timsort on a shuffled list

|    n |   qsort-fixed-pivot |   Timsort |
|------|---------------------|-----------|
|   10 |               0.021 |     0.002 |
|   50 |               0.107 |     0.005 |
|  100 |               0.211 |     0.010 |
|  200 |               0.472 |     0.020 |
|  500 |               5.306 |     0.058 |
| 1000 |               2.828 |     0.120 |
| 1500 |               4.558 |     0.188 |
| 2000 |               6.369 |     0.258 |
| 3000 |              15.654 |     0.452 |
| 5000 |              19.528 |     0.755 |



Timsort went zooming.
It is unsurprising that Timsort ran magnitudes upon magnitudes faster than qsort, since python is notoriously slow for programs in it. Timsort has the benefit of being able to be optimized in the interpreter and compiler. We were also unable to use multithreading in replit. Timsort also performed significantly better on sortesd lists and near sorted lists since it uses a combination of mergesort and insertion sort.