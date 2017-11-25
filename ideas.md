---
date: 2017.11.26
title: Random Ideas
---

Context-aware Doodles App -- I have a notebook and a pen sitting next
to my laptop as I work. It's the easiest way to jot ideas down --
especially drawings. Is there a way to make quick drawings with an
iPad that can be droped into markdown documents, JIRA tickets, etc
(e.g. whatever I happen to be doing)? Next steps: explore drawing /
sync apps with phone and airdrop -- learn if there's a convenient way
to copy/paste pictures bi-directionally between iOS and Mac OS.

Structured Editing -- I like paredit; is a structured editor like it
it available for code editors like Visual Studio? Do newer editors
like Visual Studio and Atom already have the content of buffers
tokenized in a way that would be convenient for a plugin to manipulate
structurally? Next steps: look for structured editor plugins in Atom
and Visual Studio, research plugin APIs for interacting with buffer
content.

Parallel Contains -- I was folding laundry today and used this
algorithm for sorting socks: clear an empty space, pull sock from
pile, if match in space fold with matched sock, else place in empty
space. Many algorithms have this shape: keep a `seen` set and react
conditionally in a loop depending on whether an item has been
seen. How can these be parallelized? (1) The pile of socks could be
divided and then leftovers combined into a final round -- even
distribution of work with little coordination, needs an extra
round. (2) The sock-space could be partitioned by property (striped,
grey, ...) with one person to route and the others to fold -- uneven
distribution of work, but doesn't need an extra round. (3) Share the
temporary space -- even distribution of work, possible
contention. Another question: how does a person look at the temporary
space to find a match? Computers would search incrementally through
the list / tree / set or rely on hashing. Do people use incremental
search or "visual hashing"? Next Steps: make a simple algorithm for
various matching approaches outlined, research how people match
visually when looking at socks in a temporary space.
