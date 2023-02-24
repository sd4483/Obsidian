### Exercise 01

Condition coverage doesn't guarantee decision coverage
Decision coverage doesn't guarantee condition coverage

Condition/Decision coverage can guarantee condition coverage + decision coverage

Modified/Condition coverage is C/D + something

### Exercise 02

##### Task 01

Conditoin/Decisoin coverage

##### Task 02

if (c.age <= 18 | (c.age <= 21 & c.isStudent))
age = 17
age = 
if (c.isStudent & c.age > 21)

if (c.isPremiumMember & c.age > 18)

if (c.isPensioner | c.age >= 65)


##### Task 03

c.age <= 18  - 18 | 17
c.age <= 21 -  19 | 21
c.isStudent - T | F
c.isPremiumMember - T | F
c.isPensioner - T | F
