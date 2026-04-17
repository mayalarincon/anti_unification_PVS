# anti-unification

This repository contains a verification in the iterative proof assistant PVS or a functional algorithm for syntactic anti-unification.

Anti-unification is the problem of detecting commonalities between terms. Anti-unification algorithms are a core tool for detecting regularities in expressions, a crucial mechanism in developing tools to check plagiarism and commonalities in code and data.  Relevant recent applications include the development of parallel compilers and autocorrection of code. The seminal work on anti-unification was launched by John C. Reynolds and Gordon D. Plotkin at the end of the 1960s ([1,2]). Anti-unification was recently surveyed by David Cerna and Temur Kutsia  [3].

This project starts with verifying a syntactic functional algorithm that defines a strategy for applying decomposition, solving, and trivial inference rules.  Although anti-unification has been considered a dual unification problem in several studies, this verification clarifies the different grades of complexity introduced by the necessity of using fresh variables to address anti-unification. 

**Contents**
Files .pvs and .prf are PVS specification and formalization files, respectively. 

_first_order_terms_ files contain the specification and formalization of the data structure for first-order terms.  We follow a simple structure close to the nominal syntax since we aim to enlarge the theory for dealing with nominal anti-unification, adding treatment modulo equational theories as A, C, and AC, among others. The _first_order_terms_ file specifies a series of properties for the structure. 

_first_order_substitution_ files contain the specification and formalization of the algebra of first-order substitution.  Substitutions are specified as finite sequences of basic substitutions (mappings from a variable to a term), giving rise to a constructive and verified sufficient structure able to mimic the action of abstract substitutions (mappings from variables into terms). 

_antiunif_ files contain the specification and verification of a functional algorithm for syntactic anti-unification that defines a simple strategy to apply inference rules for the _decomposition_ of terms according to the commonalities of terms in an anti-unification problem,  a rule _solving_ differences between terms, considering repetitions of occurrences of these different terms in the structure of the problem, and for recording trivial _syntactic_ non-structural commonalities related to occurrences of the same constant, the same variable or the unit symbol.  

These files are accompanied by a _Status_ file that reports the number of Type Correctness Conditions and formulas fully formalized. 

The PVS version used in this development is PVS 8.0. 

**References**

[1] John C. Reynolds. **_Transformational systems and the algebraic structure
of atomic formulas_**. Machine Intell., 5(1):135–151, 1970.

[2] Gordon D. Plotkin. _**A note on inductive generalization**_. Machine Intell.,
5(1):153–163, 1970.

[3] David M. Cerna and Temur Kutsia. _**Anti-unification and generalization:
      A survey**_. In Proceedings of the 32nd Int. Joint Conference on Artificial
      Intelligence, IJCAI, pages 6563–6573. ijcai.org, 2023.
