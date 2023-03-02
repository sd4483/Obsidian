### Exercise 01

$C_0$ coverage doesn't guarantee $C_1$ coverage but $C_1$ coverage can guarantee $C_0$ coverage.

$C_i(k)$ doesn't guarantee $C_0$ or $C_1$ coverages.

Condition coverage doesn't guarantee decision coverage.
Decision coverage doesn't guarantee condition coverage.

Condition/Decision coverage can guarantee condition coverage + decision coverage.

We can say the test suite provides Modified Condition/Decision coverage if it provides C/D + if changing A and not changing B leads to different outcomes + if changing B and not changing A leads to different outcomes.

### Exercise 02

##### Task 01

Conditoin/Decision coverage

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
c.age <= 21 & c.isStudent - T | F
c.isPremiumMember - T | F
c.isPensioner - T | F
