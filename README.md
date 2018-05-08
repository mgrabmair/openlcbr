# openlcbr

This is an open reimplementation of the IBP algorithm [1] as per the assumptions made in [2]. It is still fairly rough and subject to many revisions but the code should be readable and the algorithm understandable.

## Requirements

Python 3

## How to use:

``python3 lcbr.py data/trade-secret-cases.yaml``

... should produce this:

``` 
== open ibp test ==
loading: data/trade-secret-cases.yaml
Analyzing case KG
predicting trade_secret_misappropriation
predicting info_trade_secret
predicting info_valuable
factors in KG for info_valuable: {'F15', 'F16'}
retrieved cases sharing {'F15', 'F16'}
AMERICAN-CAN {'F15', 'F18', 'F4', 'F6', 'F16'} won by p
HENRY-HOPE {'F4', 'F6', 'F16', 'F15'} won by p
ILG-INDUSTRIES {'F15', 'F21', 'F12', 'F16', 'F7', 'F10'} won by p
KAMIN {'F15', 'F1', 'F18', 'F16', 'F10'} won by p
KUBIK {'F15', 'F21', 'F18', 'F16', 'F7'} won by p
MASON {'F15', 'F21', 'F1', 'F6', 'F16'} won by p
TELEVATION {'F15', 'F18', 'F21', 'F12', 'F6', 'F16', 'F10'} won by p
NATIONAL-REJECTORS {'F19', 'F15', 'F27', 'F18', 'F16', 'F7', 'F10'} won by d
cases not unanimous, trying to explain away
trying to explain away NATIONAL-REJECTORS
NATIONAL-REJECTORS can be explained away by unshared KO factors {'F19', 'F27'}
all counterexamples can be explained away
predicting maintain_secrecy
factors in KG for maintain_secrecy: {'F6'}
all factors unanimously favor p
predicting info_misappropriated
predicting breach_confidentiality
predicting info_used
factors in KG for info_used: {'F14', 'F18', 'F25'}
no cases retrieved in theory testing, broadening query
each of {'F14', 'F18'} is dropped for new theory testing
retrieved cases sharing ['F18']
MINERAL-DEPOSITS {'F1', 'F18', 'F16', 'F25'} won by p
AMERICAN-CAN {'F15', 'F18', 'F4', 'F6', 'F16'} won by p
KAMIN {'F15', 'F1', 'F18', 'F16', 'F10'} won by p
KUBIK {'F15', 'F21', 'F18', 'F16', 'F7'} won by p
TELEVATION {'F15', 'F18', 'F21', 'F12', 'F6', 'F16', 'F10'} won by p
NATIONAL-REJECTORS {'F19', 'F15', 'F27', 'F18', 'F16', 'F7', 'F10'} won by d
cases not unanimous, trying to explain away
trying to explain away NATIONAL-REJECTORS
NATIONAL-REJECTORS can be explained away by unshared KO factors {'F19', 'F27'}
all counterexamples can be explained away
prediction for this broadened query: p
retrieved cases sharing ['F14']
TECHNICON {'F14', 'F21', 'F12', 'F6', 'F16', 'F25', 'F10'} won by p
cases unanimously favor p
prediction for this broadened query: p
all broadened queries favor plaintiff
predicting confidential_relationship
factors in KG for confidential_relationship: {'F21'}
all factors unanimously favor p
predicting improper_means
factors in KG for improper_means: {'F14', 'F25'}
retrieved cases sharing {'F14', 'F25'}
TECHNICON {'F14', 'F21', 'F12', 'F6', 'F16', 'F25', 'F10'} won by p
cases unanimously favor p
prediction for KG: p
which is CORRECT
```

## Future Work

* lots of debugging, refactoring and adaptation
* add implementations of HYPO and possibly CATO and VJAP

## References

[1] Brüninghaus, Stefanie, and Kevin D. Ashley. "Combining case-based and model-based reasoning for predicting the outcome of legal cases." In International Conference on Case-Based Reasoning, pp. 65-79. Springer, Berlin, Heidelberg, 2003.

[2] M. Grabmair, Modeling Purposive Legal Argumentation and Case Outcome Prediction using Argument Schemes in the Value Judgment Formalism. Doctoral Dissertation, University of Pittsburgh (2016).
