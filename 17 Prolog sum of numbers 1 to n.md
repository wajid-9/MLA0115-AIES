﻿- Base case: The sum of the first 0 natural numbers is 0 
 - sum(0, 0).
- Recursive case: The sum of the first N natural numbers
-  sum(N, Total)
-  :- N > 0,
- % Ensure N is positive N1 is N - 1,
- % Decrement N sum(N1, Subtotal),
-  % Recursive call to sum(N1, Subtotal)
-   Total is N + Subtotal.
-   % Total is the sum of N and the subtotal


**output**


![image](https://github.com/user-attachments/assets/99c8f714-db7f-43f5-b081-5ee7b3340fb5)
