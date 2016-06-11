# Reformation
Automatic ontology repair using Reformation algorithm, originally written by Alan Bundy. Written in support of a currently unpublished (WIP) paper `An Algorithm to Repair Faulty Logical Theories by Reforming their Language` by Bundy, Mitrovic (2016). Available on request.

Requires `SWI-Prolog` (http://www.swi-prolog.org/).  See also a reformation algorithm for Multi-sorted logic: https://github.com/BorisMitrovic/sorted-reformation

### Run:
To run a sample `capital_of` ontology, run in SWI-Prolog: 
  > [diagnose,repair,util,reform,revise,utilRevise,capOf]. revise.
  
Replace capOf with another ontology file, to repair another ontology. Ontology file is a collection of `fact` definitions. See `ontology.pl` or `capOf.pl` for an example.

### General structure of the code:
 - `revise.pl`: Revises the ontology to a consistent state. Finds minimal repairs and repairs the ontology.
 - `reform.pl`: Performs a reformation algorithm. Either blocks a successful unification, if failure wanted, or unblocks a failed unification if success wanted.
 - `diagnose.pl`: Finds all possible repairs, which could unblock the unification.
 - `repair.pl`: Applies the repairs to either unification, or ontology repairs to the ontology.
 - `utilRevise.pl`: General utility functions for revise algorithm.
 - `util.pl`: General utility functions.

### Abstract from the paper:
  We describe reformation, a new algorithm for the automated repair of faulty logical theories. A fault is revealed by a reasoning failure: either the proof of a false conjecture or the failure to prove a true conjecture. Repair suggestions are systematically extracted via analysis of (un)successful unifications of formulae in (broken) proofs. These suggestions will either unblock a wanted but unsuccessful unification attempt or block an unwanted but successful unification. In contrast to traditional abduction and belief revision mechanisms, the repairs are to the language of the theory as well as to the axioms. The intention is that the language repairs suggested by reformation complement these axiom deleting and adding repairs, adding to the overall capability of theory repair and evolution. Reformation is self-inverse in that any blocking repair can be undone by an unblocking one, and vice versa. This self-inverse property provides some assurance that reformation repairs are minimal.

### Keywords:
  Automated reasoning, knowledge representation, ontology evolution, unification, belief revision, abduction.
