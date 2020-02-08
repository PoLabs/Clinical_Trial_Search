# **Clinical_Trial_Search**
NLP powered trial search using ClinTrials.gov database



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Clin trial search algorithm was designed to address umet needs in patient recruitment. Over 85% of clinical trials finish late due to recruitment issues costing an average of 1 million dolalr sper day extra. This notebook preesents a novel search algorithm for pateints and physicians to use to find potential clinical trials, faciliting recruitment and enrollment. The priamry benefits of this algorithm over traidtional keyword matching is that it accoiunts for the latent relationships wbetween medical terminjologyu and avoids over filtering of similar trials. 


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As a general overview, we first download the latestest datas set from clinical trial.gov (located at LINK). We then extract the trial long names, inclusion, 4exclusion, itnervention and condition fields. We then parse these fields agaisnt a medical onotology (such as the ULMS, MEDRA, WHO or SNOMED-CT) yeilding a list of medical codes for a given trial. To determine how closely the search trerms and the trial terms are we use a set of clinical term embeddings genertated from a massive amount of clinical note, medical jopurnal articles and claims data. The result is a set of codes merged with their associated embeddings attached. When a user enters search vterms, they're parsed into codes and then merged with their associated emebeddings. We measure the association betweene search and trial codes via a distance metric (such as cosine similarity) and compute a weighted average of all search-to-trial code similarity scores. The resulting scores are used to rank clinical trrialsby how simialr they are to the users input. 
