- Facts about individuals with their names and DOBs 
 dob(john, date(1990, 5, 15)). 
 dob(lisa, date(1985, 10, 20)). 
 dob(mary, date(1995, 2, 8)). 
 dob(david, date(1980, 7, 3)).
- Query to find the DOB of a person get\_dob(Person, Date) :-
-  dob(Person, Date).
- Query to find individuals born after a certain year born\_after(Year, Person)
- :- dob(Person,
- date(Year2, \_, \_)),
-  Year2 > Year.
- Sample query ?- born\_after(1985, Person).


**output**


![image](https://github.com/user-attachments/assets/f05ea554-5995-4563-8bba-986188f26657)



