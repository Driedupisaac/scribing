Scribing 2/04/2025 Isaac Wedaman

* Homework 2 due next monday the 10th

* Definition REGULAR EXPRESSION: also known as RegEx or regexs, or RE
* every regualr expresssion describes a [REGULAR] langauge, which is a set of strings, so a regualr expression is a description of all strings in a set, and froom there the problem is pattern matching
* *matcehd strings are in the languague, where those unmatched are not

* {w | w contain substring 111} --> regular expresions offer a new way to describe something

* this implies that every regEx has an equivalent DFA, and because of that an equivalent NFA

* [DEFINITION of a regular expression]: U:union -> (0 U 1)  which means {0} U {1}.
* Kleene Star* means 0 or more appearances of "starred" expression ---> (01* = {null, 01, 0101, 010101}
* ACTUAL DEFINITION = we say that R is a regular expression if R is a for some a EPSILON SIGMA --> SIGMA = {0, 1}, so here zero is a regular expression
* R is [empty set]
* R is [empty language]

* Alternative definition:
* (R1, U R2) where R1, R2, are both regexs, we get a regular expression
* (R1 concat R2) where R1, R2, are both regexs, , we get a regular expression
* (R*), where r is a RegEx

* RE1 concat {1} ---> ![image](https://github.com/user-attachments/assets/41c796c9-f7a5-4248-aa37-2c84639b5099)

*for these next finite automata, {[epsilon], 1, 11}

*DIFFERENCE between epsilon and empty string --> photo two

*R+ = RR+ --> "one or more"
*0*10* = {w | w contains a single one} 
(photo 3)

Sigma in a regex means any single number in sigma
Sigma* = 0 or more of any a [epsilon] [sigma]

*photo
Regular Expression Sigma*1Sigma* 

Case 1:photo
case 2 & 3: photo

case 4,5,6



A concat B: we have two machines, and epsilon tranisiton from the accepting state of a to the start point of b. we are going to do something similar to the set assemblies


AB: 

AB U A

(AB U a)*

*equivalency betwen regular expressions & finitie automata: RegEx --> NFA --> (--> DFA)
claim: regexs and finite automata are equal: proof

DFA: definite finite automata
NFA: non finite automata
New GNFA --> "generalized" NFA, labels are an expression
Goal: given an arbitrary NFA, recover an equivalent regular expression 
*Rough outline: step one: construct a GNFA (what!). Step 2:recursively eliminate states, and as we do so we should alter the labels on transitions so that we preserve the language, and step 3: when only start and end states remain, the transmission label between them is the recovered regular expression 
proof:

step one: produce a GNFA
step two: "rip through a state" --> [explanation] rip Q1 --> take into account the flow from q1 to q2, start state to q1, q1 a to q2, and q1b to q3: we need a state (using our new labels) tale out ("rip") q1, and so start a to Q2 and start b to Q3 is the new model.
