# IBM_Decision_Optimization
1. Go to https://www.ibm.com/cloud/garage/dte/tutorial/create-and-run-optimization-model-python
2. Enter full email address and password to login.
3. Right corner: Before you start: Country ==> United States and try it for ==> 4 hours.
4. Click on the link sent from email and use temporaray password given in email (dont add extra spaces).
5. Double click and open jupyter-notebook.
6. Make the window large and go right top corner to create new python3 notebook.

# Example  of decision optimization
https://www.ibm.com/developerworks/community/forums/html/topic?id=a8580237-639a-411b-b1df-f390a24da06c&ps=25
```python
# bus A: 30 seats $400
# bus B: 40 seats $500
# number of kids to travel 300
# Find the minimum number of buses to minimize the cost.

from docplex.mp.model import Model

mdl = Model(name=‘b’)

b40 = mdl.integer_var(name=‘b40’)
b30 = mdl.integer_var(name=‘340’)

mdl.add_constraint(b40*40 + b30*30 >= 300, ‘kids’)

mdl.minimize(b40*500 + b30 * 400)
mdl.solve()

b40.solution_value, b30.solution_value  # gives 6,2
```
