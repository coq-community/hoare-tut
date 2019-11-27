# Tutorial on Hoare Logic

[![Contributing][contributing-shield]][contributing-link]
[![Code of Conduct][conduct-shield]][conduct-link]
[![Gitter][gitter-shield]][gitter-link]


[contributing-shield]: https://img.shields.io/badge/contributions-welcome-%23f7931e.svg
[contributing-link]: https://github.com/coq-community/manifesto/blob/master/CONTRIBUTING.md

[conduct-shield]: https://img.shields.io/badge/%E2%9D%A4-code%20of%20conduct-%23f15a24.svg
[conduct-link]: https://github.com/coq-community/manifesto/blob/master/CODE_OF_CONDUCT.md

[gitter-shield]: https://img.shields.io/badge/chat-on%20gitter-%23c1272d.svg
[gitter-link]: https://gitter.im/coq-community/Lobby


Hoare logics are "program logics" suitable for reasoning about
imperative programs.
This work is both an introduction to Hoare logic and a demo
illustrating Coq nice features. It formalizes the generation of PO
(proof obligations) in a Hoare logic for a very basic imperative
programming language. It proves the soundness and the completeness of
the PO generation both in partial and total correctness. At last, it
examplifies on a very simple example (a GCD computation) how the PO
generation can simplify concrete proofs. Coq is indeed able to compute
PO on concrete programs: we say here that the generation of proof
obligations is reflected in Coq. Technically, the PO generation is
here performed through Dijkstra's weakest-precondition calculus.



## Meta

- Author(s):
  - Sylvain Boulmé (initial)
- Coq-community maintainer(s):
  - Kartik Singhal ([**@k4rtik**](https://github.com/k4rtik))
- License: [GNU Lesser General Public License v3.0 or later](LICENSE)
- Compatible Coq versions: 8.10 or later
- Additional Coq dependencies: none

## Build instructions

``` shell
git clone https://github.com/coq-community/hoare-tut
cd hoare-tut
make   # or make -j <number-of-cores-on-your-machine>
```


## Aims of this library


This work is both an introduction to Hoare logic and a demo
illustrating Coq nice features. Indeed, the power of Coq higher order
logic allows to give a very simple description of Hoare
logic. Actually, I find this presentation simpler than those found in
some hand-written books. In particular, because we are in a rich
language, some notions which are not in the "kernel" of the logic
(e.g. the return types of expressions or the assertion language) can
be simply "shallow embedded": we do need to introduce an abstract
syntax for these notions, and we can handle directly their semantics
instead. Furthermore, because Coq is a programming language with
propositions as first class citizens, it is able to compute the PO of
Hoare logic on concrete imperative programs. At last, most of proofs
in this development are discharged by Coq, using only a few hints
given by the user. Most of these hints are simply some key ideas of
the proofs.

In summary, this work aims to illustrate the following ideas:
  - Coq is suitable both for reasoning about program logics and for
    emulating these logics.
  - Reflecting Dijkstra's weakest-precondition calculus is an elegant and powerful
    way to reason about non-functional programs in Coq.

I use this library in some talks presenting Coq. It takes me usually
between 45 minutes and 1 hour to present its different part.


## How to read the sources


The best way to read the sources is to read them through coqide (or your
favorite coq interface): you will be able to replay the (short) proofs
of this development.  In particular, replaying proof of `gcd_partial_proof`
and `gcd_total_proof` in file `exgcd.v` allows to see
how Coq generates PO on a concrete example. To do so, you
may first need to download the sources and then to compile them using `make`.
In case of trouble, please contact me.

To read the sources, you may follow this order:
  - Start by reading `hoarelogicsemantics.v` (the semantics of my Hoare logic)
    and `exgcd.v` (which examplifies how to use this Hoare logic).
    It seems a good idea to read these files more or less in parallel.
  - Then, read `partialhoarelogic.v` the PO generation in partial correctness.
  - At last, read `totalhoarelogic.v` the PO generation in total correctness.
    Indeed, the PO generation in total correctness may be considered as a
    refinement of the PO generation in partial correctness.
  - It seems almost useless to read `hoarelogic.v`.
    Its purpose is only to glue all this stuff together.


 ## Contact


If you have any comment, suggestion, question or trouble about this work,
please send a mail to Sylvain.Boulme@imag.fr

For more information, see my web page at
http://www-verimag.imag.fr/~boulme

