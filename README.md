# IndirectQuestions
Code and Data for my paper "Communication Norms in Earnings Conference Calls: The Role of Indirect Questions"

***Alexander Paulus, LMU Munich School of Management***
---

This repository contains the code and data to identify indirect questions in conference call transcripts and to replicate the in- and out-of-sample testing of Paulus (2022): “Communication Norms in Earnings Conference Calls: The Role of Indirect Questions” (see SSRN). Furthermore, it also includes the online appendix to the paper. 

***Identification of indirect questions:***
As described in the paper, the identification approach is based on regular expressions (RegEx) that match the lexicogrammatical structure of analyst’s questions to determine whether the respective question contains any notion of indirectness or not. For a brief introduction as the syntax of RegEx please refer to [official RegEx website](https://docs.python.org/3/library/re.html). Another valuable source that helped me to program these RegEx is [regex101.com](https://regex101.com/), a live debugger.

The RegEx basically distinguish between four different types of indirect questions: 

   1. Query preparatory phrases (**QueryPrepQ**): e.g., *“could you…?”*
   2. Hedged statements (**HedgedQ**): e.g., *“Just wondering…"*
   3. Want statement (**WantQ**): e.g., *“I wanted to ask…”*
   4. If-clauses (**IfQ**): e.g., *“If you could…”*

The algorithm tags an analyst’s questions as indirect (**Indirectness**) if one of the above-mentioned different types of indirect questions can be identified.

***Requirements:***
**Data (Preprocessing)** - In order to apply the RegEx to analyst’s questions you need to preprocess conference call transcripts in the following manner:
    - Each respective analyst question needs to constitute one observation. Hence, if an analyst is allowed to ask three consecutive questions, this results in three observations.
    - Questions need to be transformed to uppercase.
**Modules (Python packages)** - Please make sure to install the latest version of the following Python modules:
    - [Numpy](https://numpy.org/)
    - [Pandas](https://pandas.pydata.org/)
    - [re](https://docs.python.org/3/library/re.html)
