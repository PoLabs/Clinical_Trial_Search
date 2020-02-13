# **Clinical_Trial_Search**
NLP powered trial search using ClinTrials.gov database



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Clinical_trial_search algorithm was designed to address unmet needs in patient recruitment. Over 85% of clinical trials finish late due to recruitment issues and each extra day is extremely costly. This notebook presents a novel search algorithm for patients and physicians to use to find potential clinical trials, facilitating recruitment and enrollment. The primary benefits of this algorithm over traditional keyword matching is that it accounts for the latent relationships between medical terminology and avoids over filtering of similar trials.  


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As a general overview, we first download the latest dataset from clinicaltrials.gov (LINK). We then extract the trial long names, inclusion, 4exclusion, intervention and condition fields. We then parse these fields against a medical ontology (such as the UMLS, MEDRA, WHO or SNOMED-CT) yielding a list of medical codes for a given trial. To determine how closely the search terms and the trial terms are we use a set of clinical term embeddings generated from a massive amount of clinical note, medical journal articles and claims data. The result is a set of codes merged with their associated embeddings attached. When a user enters search terms, they're parsed into codes and then merged with their associated embeddings. We measure the association between search and trial codes via a distance metric (such as cosine similarity) and compute a weighted average of all search-to-trial code similarity scores. The resulting scores are used to rank clinical trials by how similar they are to the users input.  




<center><img src='unrankedNCTs.png'></img></center>


<center><img src='ULMS.png'></img></center>


<center><img src='ngrams.png'></img></center>


<center><img src='ngramCUIs.png'></img></center>


<center><img src='cosinesim.png'></img></center>


<center><img src='rankedNCTs.png'></img></center>
