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
![image](https://github.com/user-attachments/assets/011d5d46-236d-4339-90e8-ca71f55ffe68)



Sigma in a regex means any single number in sigma
Sigma* = 0 or more of any a [epsilon] [sigma]

![image](https://github.com/user-attachments/assets/2cadd85d-ef96-4fb9-ab93-3999b1630453)

Regular Expression Sigma*1Sigma* 

Case 1:photo
![image](https://github.com/user-attachments/assets/1b574bab-63cf-497a-8dea-c2b95cf25d56)

case 2 & 3: photo
![image](https://github.com/user-attachments/assets/d8f25702-5b49-44d1-b660-a152149379b1)
case 4,5,6
![image](https://github.com/user-attachments/assets/92a8979f-ee8a-40a0-ad40-5e1a30f69fd7)




A concat B: we have two machines, and epsilon tranisiton from the accepting state of a to the start point of b. we are going to do something similar to the set assemblies
![image](https://github.com/user-attachments/assets/2494a194-25e3-4688-b464-d804b1c16546)



AB: 
![image](https://github.com/user-attachments/assets/3f17487e-09f1-41bb-a221-f3f20766580b)


AB U A
![image](https://github.com/user-attachments/assets/af2ef684-b08b-40d2-9d95-db630b7f9abd)


(AB U a)*
![image](https://github.com/user-attachments/assets/2c887966-87dc-49cb-b18f-25478262c9d9)

![image](https://github.com/user-attachments/assets/814fc1bc-c7c5-4d27-898c-88446fe1e499)


*equivalency betwen regular expressions & finitie automata: RegEx --> NFA --> (--> DFA)
claim: regexs and finite automata are equal: proof
![image](https://github.com/user-attachments/assets/31a660f6-6f67-443f-bffa-cf5a3404b0aa)


DFA: definite finite automata
NFA: non finite automata
New GNFA --> "generalized" NFA, labels are an expression
Goal: given an arbitrary NFA, recover an equivalent regular expression 
*Rough outline: step one: construct a GNFA (what!). Step 2:recursively eliminate states, and as we do so we should alter the labels on transitions so that we preserve the language, and step 3: when only start and end states remain, the transmission label between them is the recovered regular expression 
proof:![image](https://github.com/user-attachments/assets/10c415aa-d537-4419-bb51-b111ef834d23)

step one: produce a GNFA
step two: "rip through a state" --> [explanation] rip Q1 --> take into account the flow from q1 to q2, start state to q1, q1 a to q2, and q1b to q3: we need a state (using our new labels) tale out ("rip") q1, and so start a to Q2 and start b to Q3 is the new model.
![image](https://github.com/user-attachments/assets/19a3e9b0-e70a-4e19-9706-ee27491cd74f)

SCRIBING 02/06/2025

A regular expression can be equated to a regular expression
*Regex --> NFA --> DFA
*another method we'll learn about is "state elimination ", where we slowly get rid of states until we only have the start state, the path to the end state, and the final accepting state.

eventually, you end up with a regex with the sequence that satisfies the start to end state. 
here is an example of state elimination figured out by Atticus: ![image](https://github.com/user-attachments/assets/2469317b-2229-43bb-96a4-821686b58998)
1) we start with a finite automaton with three states. it takes an epsilon to get from the start state, so we keep that in mind and get rid of q1, while conferring the now defunct q1 states to the start state. from here, we need to remove another state while retaining the old flow state; each successive iteration of the finite automaton must be equal to the last, less ripped version
2) next, we intend to rip q2. to do this, we take stock of what it is connected to, remove it, and form a new finite automaton. for removing q1, we got that we needed epsilon then a to satisfy the machine, so we add that [we can disregard the epsilon] b must be nextm but we also add a star because once in q3, the sigma means that any b after will let the finite automaton remain in the accept state, so we add a b*, to denote that any successive bs would also work. 

