---
date: 2017.11.26
title: Working Notes -- Think Bayes
---

To install [Think Bayes][think-bayes] dependencies:

    git clone https://github.com/AllenDowney/ThinkBayes2.git
    brew install pkg-config
    pip install numpy scipy matplotlib pandas
    export PYTHONPATH="${PWD}/ThinkBayes2/code"
    python ThinkBayes2/code/m_and_m.py

From thinkbayes2.py `class Hist`:

    Represents a histogram, which is a map from values to frequencies.

From wikipedia [Histogram][wiki-histogram]:

    A histogram is an accurate graphical representation of the
    distribution of numerical data. It is an estimate of the
    probability distribution of a continuous variable (quantitative
    variable).

    To construct a histogram, the first step is to "bin" the range of
    values—that is, divide the entire range of values into a series of
    intervals—and then count how many values fall into each
    interval. The bins are usually specified as consecutive,
    non-overlapping intervals of a variable. The bins (intervals) must
    be adjacent, and are often (but are not required to be) of equal
    size.

    If the bins are of equal size, a rectangle is erected over the bin
    with height proportional to the frequency...

    However, bins need not be of equal width; in that case, the
    erected rectangle is defined to have its area proportional to the
    frequency of cases in the bin... The vertical axis is then not
    the frequency but frequency density — the number of cases per unit
    of the variable on the horizontal axis.

Notes on `thinkbayes.py`:

* most things inherit from _DictWrapper
* `Hist` can be used to keep state -- `.Total` is useful
* lots of specialized helper methods like `Incr`
* use `.Items` and `.Values` for iterating over hypotheses / state
* `.Update` and `.Likelihood` are key methods


Implemented [cookies-without-replacement.py][cookies-without-replacement].

[think-bayes]: http://greenteapress.com/wp/think-bayes/
[wiki-histogram]: https://en.wikipedia.org/wiki/Histogram
[cookies-without-replacement]: weaver/exercises/think-bayes/cookies-without-replacement.py
---
date: 2017.11.26
title: TIL
---

[ed25519 SSH Keys][ed25519] -- noticed that github invalidated my SSH
key. When I went to update, I saw "ed25519" as an option. What's that?

* `ssh-keygen -o -a 100 -t ed25519`
* Ed25519 keys are very short (public key is ~68 characters)
* EdDSA using Twisted Edward curves
* `ssh-keygen -o` -- RFC4716 key format and bcrypt for key derivation
* `-a <num>` -- <num> amount of rounds


[Tracking Branches][tracking]

* `git push --set-upstream` -- If you already have a local branch and
  want to set it to a remote branch you just pulled down, or want to
  change the upstream branch you’re tracking.

[ed25519]: https://blog.g3rt.nl/upgrade-your-ssh-keys.html
[tracking]: https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches#_tracking_branches

---
date: 2017.11.26
title: Research
---

Edwards Curves, Twisted Edwards Curves -- Elliptic curves are
important in public key cryptography and twisted Edwards curves are at
the heart of an electronic signature scheme called EdDSA that offers
high performance while avoiding security problems that have surfaced
in other digital signature schemes.
