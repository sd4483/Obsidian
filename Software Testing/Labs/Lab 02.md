### Exercise 01

Condition coverage doesn't guarantee decision coverage
Decision coverage doesn't guarantee condition coverage

Condition/Decision coverage can guarantee condition coverage + decision coverage

Modified/Condition coverage is C/D + something

### Exercise 02

##### Task 01

Conditoin/Decisoin coverage

##### Task 02

age = 22
student = F
premium = F
pensioner = F

age = 17
student = T
premium = F
pensioner = F

age = 64
student = F
premium = F
pensioner = F

age = 66
student = F
premium = F
pensioner = T

**if (c.age <= 18 | (c.age <= 21 & c.isStudent))**

age = 21
student = T

age = 22
student = F

**if (c.isStudent & c.age > 21)**

student = T
age = 22

student = F
age = 19

**if (c.isPremiumMember & c.age > 18)**

PremiumMember = T
age = 21

PremiumMember = F
age = 17

**if (c.isPensioner | c.age >= 65)**

Pensioner = T
age = 66

Pensioner = F
age = 64

##### Task 03

c.age <= 18  - 18 | 17
c.age <= 21 -  19 | 21
c.isStudent - T | F
c.isPremiumMember - T | F
c.isPensioner - T | F
