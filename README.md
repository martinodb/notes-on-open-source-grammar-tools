Notes on open source grammar tools

======

# Construction Grammars

## FCG (Fluid Construction Grammar)
* [My fork of Babel2](https://github.com/martinodb/Babel2)
* [My mirror plus documentation of Babel-core](https://github.com/martinodb/babel-core)

## SBSG (Sign-based Construction Grammar)
* [RuiPChaves-SBCG (needs SICStus Prolog)](https://github.com/RuiPChaves/SBCG)
* [I forked RuiPChaves-SBCG, trying to make it run on SWI-Prolog, but it doesn't work as of yet](https://github.com/martinodb/SBCG)


# HPSG (Head-driven Phrase Structure Grammar)
## Delph-in tools
> Deep Linguistic Processing with HPSG (DELPH-IN)
> The DELPH-IN Consortium is a collaboration among computational linguists from research sites world-wide working on ‘deep’ linguistic processing of human language. The goal is the combination of linguistic and statistical processing methods for getting at the meaning of texts and utterances. The partners have adopted Head-Driven Phrase Structure Grammar (HPSG) and Minimal Recursion Semantics (MRS), two advanced models of formal linguistic analysis. They have also committed themselves to a shared format for grammatical representation and to a rigid scheme of evaluation, as well as to the general use of open-source licensing and transparency.

* [Main DELPH-IN website](http://moin.delph-in.net/wiki/FrontPage)
* [LkbFos (FOSS edition of LKB)](http://moin.delph-in.net/wiki/LkbFos)
* [ACE ("Answer Constraint Engine", parsing and generation with DELPH-IN grammars. Do not confuse with Attempto ACE)](http://moin.delph-in.net/wiki/AceTop)
* [pyDelphin (requires ACE installed)](https://github.com/delph-in/pydelphin)

## Menard
* [Menard github repo](https://github.com/ekoontz/menard)
   * "A Clojure library for generation and parsing expressions from grammars and lexicons."
   * For now, it seems a toy to translate from a small subset of Dutch to English
   * But it's actively maintained and it's pure Clojure, no need to use external tools. That's interesting.
   * Not very documented, but good response to issues by the author.



# OpenCCG (CCG: Combinatory Categorial Grammar)
* [Github repo](https://github.com/OpenCCG/openccg)
* [SourceForge repo (it's needed)](https://sourceforge.net/projects/openccg/files/openccg/)
* Documentation
  * [Installation](https://davehowcroft.com/post/installing-openccg/)
  * [Gettting started](https://davehowcroft.com/post/getting-started-with-openccg/) 
