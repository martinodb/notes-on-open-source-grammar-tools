Notes on open source grammar tools.
======

# Construction Grammars

## FCG (Fluid Construction Grammar)
* [FCG website](https://www.fcg-net.org/)
  * Problem: There's a Github repo which is well documented but outdated, and a Gitlab repo (which is the one recommended in the FCG website) which is more up-to-date but very poorly documented. So I forked both.
* [My fork of the Babel2 Github repo](https://github.com/martinodb/Babel2)
* [My mirror plus documentation of the Babel-core Gitlab repo](https://github.com/martinodb/babel-core)

## SBSG (Sign-based Construction Grammar)
* [RuiPChaves-SBCG (needs SICStus Prolog)](https://github.com/RuiPChaves/SBCG)
* [I forked RuiPChaves-SBCG, trying to make it run on SWI-Prolog, but it doesn't work as of yet](https://github.com/martinodb/SBCG)


# HPSG (Head-driven Phrase Structure Grammar)
## Delph-in tools
> Deep Linguistic Processing with HPSG (DELPH-IN)
> The DELPH-IN Consortium is a collaboration among computational linguists from research sites world-wide working on ‘deep’ linguistic processing of human language. The goal is the combination of linguistic and statistical processing methods for getting at the meaning of texts and utterances. The partners have adopted Head-Driven Phrase Structure Grammar (HPSG) and Minimal Recursion Semantics (MRS), two advanced models of formal linguistic analysis. They have also committed themselves to a shared format for grammatical representation and to a rigid scheme of evaluation, as well as to the general use of open-source licensing and transparency.

* [Main DELPH-IN website](http://moin.delph-in.net/wiki/FrontPage)
* [LkbFos (FOSS edition of LKB)](http://moin.delph-in.net/wiki/LkbFos)
  * The automatic installation of **LkbFos** includes the often mentioned grammar testing app called **[incr tsdb()]** ("tee es dee bee plus plus").
     * In theory it can be called in **emacs** by typing ```M-x itsdb RET``` but I haven't got that to work.
     * What I did is open the **[incr tsdb()] Podium** in a new window from **LkbFos**.
     * For that, do ```options->expand menu``` , then ```advanced->evaluate lisp expression``` , then pick from the list ```(tsdb:tsdb :podium)```
* [ACE ("Answer Constraint Engine", parsing and generation with DELPH-IN grammars. Do not confuse with Attempto ACE)](http://moin.delph-in.net/wiki/AceTop)
* [DELPH-IN Grammar Matrix](https://matrix.ling.washington.edu/customize/matrix.cgi)
  * See also the [Getting Started](http://moin.delph-in.net/wiki/MatrixGettingStarted)
* [pyDelphin (requires ACE installed)](https://github.com/delph-in/pydelphin)
 > DELPH-IN is an international consortium of researchers committed to producing precise, high-quality language processing tools and resources, primarily in the HPSG syntactic and MRS semantic frameworks, and PyDelphin is a suite of Python libraries for processing data and interacting with tools in the DELPH-IN ecosystem. PyDelphin's goal is to lower the barriers to making use of DELPH-IN resources to help users quickly build applications or perform experiments, and it has been successfully used for research into machine translation (e.g., Goodman, 2018), sentence chunking (Muszyńska, 2016), neural semantic parsing (Buys & Blunsom, 2017), natural language generation (Hajdik et al., 2019), and more.
 > Documentation, including guides and an API reference, is available here: http://pydelphin.readthedocs.io/
 > New to PyDelphin? Want to see examples? Try the walkthrough.

## Menard
* [Menard github repo](https://github.com/ekoontz/menard)
   * "A Clojure library for generation and parsing expressions from grammars and lexicons."
   * For now, it seems a toy to translate from a small subset of Dutch to English
   * But it's actively maintained and it's pure Clojure, no need to use external tools. That's interesting.
   * Not very documented, but quick and good [response to issues](https://github.com/ekoontz/menard/issues/2) by the author.



# OpenCCG (CCG: Combinatory Categorial Grammar)

> OpenCCG is a system for parsing and generating text using [combinatory categorial grammar](https://en.wikipedia.org/wiki/Combinatory_categorial_grammar) for syntax and [hybrid logic dependency semantics](https://www.aclweb.org/anthology/P02-1041/) for, well, the semantic representation.
> If that seems like a mouthful, don't worry too much about the details right now. You can get started installing OpenCCG and working with OpenCCG using the tccg utility right now.
> If, on the other hand, you want to start understanding what that mouthful means, Johanna Moore at the University of Edinburgh has some helpful course notes on NLG in general and OpenCCG in particular.


* [Github repo](https://github.com/OpenCCG/openccg)
* [SourceForge repo (best option to get started quickly, since it includes compiled dependencies)](https://sourceforge.net/projects/openccg/files/openccg/)
* Documentation
  * [Installation](https://davehowcroft.com/post/installing-openccg/)
  * [Gettting started](https://davehowcroft.com/post/getting-started-with-openccg/)
* Possible drawbacks
  * I can't find an editable broad coverage English grammar (like you can get in [the DELPH-IN grammar matrix](https://matrix.ling.washington.edu/customize/matrix.cgi)). Instead, there are trained models from CCGbank. Problems with this:
   * It assumes Standford CoreNLP tools, which are GPL licensed (not LGPL), which can lead to license incompatibilities.
   * Training your own models (as opposed to using the provided trained models) requires a CCGbank license.

## Example interaction with tccg (the main OpenCCG tool)

```
$ tccg
Loading grammar from URL: file:/home/[..]/openCCG/SourceForge/openccg/grammars/tiny/grammar.xml
Grammar 'tiny' loaded.

Enter strings to parse.
Type ':r' to realize selected reading of previous parse.
Type ':h' for help on display options and ':q' to quit.
You can use the tab key for command completion, 
Ctrl-P (prev) and Ctrl-N (next) to access the command history, 
and emacs-style control keys to edit the line.

tccg> she buys it
3 parses found.

Parse 1: s : 
  @w1:action(buy ^ 
             <tense>pres ^ 
             <Actor>(w0:animate-being ^ pro3f ^ 
                     <num>sg) ^ 
             <Patient>(w2:thing ^ pro3n ^ 
                       <num>sg))
tccg> :r
[1,000] she buys it :- s : (@w0:animate-being(pro3f) ^ @w0:animate-being(<num>sg) ^ @w1:action(buy) ^ @w1:action(<tense>pres) ^ @w1:action(<Actor>w0:animate-being) ^ @w1:action(<Patient>w2:thing) ^ @w2:thing(pro3n) ^ @w2:thing(<num>sg))
tccg> :q
Exiting tccg.
```
