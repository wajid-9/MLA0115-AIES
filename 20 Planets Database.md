orbits(mercury, sun). 
 
 
 orbits(venus, sun).
 
 
 orbits(earth, 

orbits(moon, earth).

orbits(phobos, mars). 

orbits(deimos, mars).

planet(P) <= orbits(P, sun). 

satellite(S) <= orbits(S, P) and planet(P). 


input: orbit(moon,neptune).

ouput:false

sun). orbits(mars, sun).



**Output**



![image](https://github.com/user-attachments/assets/c3ade283-f3e1-40ea-aa5c-87c95ce44d89)

