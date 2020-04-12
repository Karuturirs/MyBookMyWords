# 						Algorithms 

|      Name      |     Time complexity      | Space complexity |                            Notes                             |
| :------------: | :----------------------: | :--------------: | :----------------------------------------------------------: |
| Insertion Sort |          $n^2$           |        1         |              cards sorted right to left in hand              |
|   Merge Sort   |        $n*log n $        |       $n$        | DIvide and conquer, two sorted piles shown up. create new pile which ever is small |
|  Bubble sort   |          $n^2$           |        1         | comparing to insertion sort is much faster even if though they are $n^2$ |
|  Horners rule  |           $n$            |                  | y = a0 + x * a1 + x^2 * a2 + x^3 * a3 + ....... + x^(n) * a(n) |
|  Boyer–Moore   |                          |                  |                                                              |
|   Strassens    | $n^(log7)$  = $n^(2.81)$ |                  |             square matrix multiplication($n^3$)              |
|                |                          |                  |                                                              |

## notes

* Insertion sort picking a card from the desk one after other and filling in sorting order from right to left

* Merge sort is whne you have two sorted pile facing up, pick the smallest of both pile and place it in new third pile. but do it recursive.

* Binery search:

  > observe that if the sequence A is sorted, we can check the midpoint of the sequence against  and eliminate half of the sequence from further consideration. The binary search algorithm repeats this procedure, halving the size of the remaining portion of the sequence each time. Write pseudocode, either iterative or recursive, for binary search. Argue that the worst-case running time of binary search is $log n$

































