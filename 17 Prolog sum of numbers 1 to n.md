sum_to_n(0,0).
sum_to_n(N,Sum):-
    N>0,
    N1 is N-1,
    sum_to_n(N1,Sum1),
    Sum is N+Sum1.

**output**



![image](https://github.com/user-attachments/assets/45ba5b64-2d0f-48b7-a8fd-a7844a3acf65)

