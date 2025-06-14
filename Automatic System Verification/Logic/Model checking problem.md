Given a system S and a specification $\varphi$ we want to check if all possible executions of the system satisfy the properties of the specification. If yes, we denote $S\models\varphi$.
When the formula contains boolean quantifiers the model checking is performed recursevely by evaluating the formula for each possible value of the quantified variable:
- for existential quantifiers ($\exists$) the formula is true if at least one value of the variable makes it true.
- for universal quantifiers ($\forall$) every possible value of the quantified variable needs to make the formula true.
