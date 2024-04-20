## Conclusion
Overall the solution was well implemented. The code was understandable and well structured. 
Responsibilities were divided between classes without unnecessary complexity.
I found one issue, there was a bug in line 41 in `loan_form.dart`:
```dart
if (tempAmount <= _loanAmount || tempPeriod > _loanPeriod) {
```
which should be 
```
if (tempAmount != _loanAmount || tempPeriod > _loanPeriod) {
```
In cases where the engine would approve a loan amount that is larger than the one requested, 
the interface did not display it correctly. It always displayed the requested amount, even when the 
amount returned by the decision engine was larger.
