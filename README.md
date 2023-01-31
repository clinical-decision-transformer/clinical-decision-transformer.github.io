<center><font size="10"><b>Clinical Decision Transformer</b> </font></center>
<center><font size="5">: Intended Treatment Recommendation through Goal Prompting</font></center>
<br>
<center> <u><b>Code:</b></u> soon be available </center>

<br>

<span style="color: #2d6885"><font size="5"><b>Summary</b></font></span>
- <div style="text-align: justify">We propose Clinical Decision Transformer, a clinical recommender system that generates a sequence of medications to reach a desired clinical state given as a goal prompt.</div>

![cdt_overview](https://user-images.githubusercontent.com/119850923/215435040-0a80bbac-671f-42c2-8e22-2904d1311fcc.gif)

<br>

- <div style="text-align: justify">We extracted a diabetes dataset from an electronic health record elec(EHR) system and used it to train two models; the proposed Clinical Decision Transformer and Counterfactual Recurrent Network [1] as an evaluation model for estimating recommendation effects.</div>
- <div style="text-align: justify">We find that recommended medications by the Clinical Decision Transformer shift patients' clinical states (e.g. hemoglobin A1c) in the intended directions (e.g. the normal range of hemoglobin A1c: 4--5.6% [2]) compared to those of factual prescriptions and behavior cloning.</div>

![goal_prompting](https://user-images.githubusercontent.com/119850923/215706750-0ebdd228-bd20-4af6-ae9e-f67625780f96.png)

<br><br>

<span style="color: #2d6885"><font size="5"><b>Contextual Embedding</b></font></span>
- <div style="text-align: justify">It is necessary to contextualize inter-admission and intra-admission information to fully utilize large-scale EHR data characterized by heterogeneity and high missing rates (for laboratory test columns in our dataset; mean 44.39%, median 22.37%).</div>
- <div style="text-align: justify">In a t-SNE analysis, we observe that the output embeddings for each admission point are clustered with respect to prescriptions, while the input admissions are entangled before contextualized.</div>
- <div style="text-align: justify">In this study, the cold start corresponds to the case where the input admission length is one without previous admission history.</div>

![contextual_embedding](https://user-images.githubusercontent.com/119850923/215558959-79e21b1b-89f3-4792-b4c9-f43ad2ac4884.png)

<br><br>

<span style="color: #2d6885"><font size="5"><b>Attention Pattern</b></font></span>
- <div style="text-align: justify">We visualized representative cases of attention patterns to analyze how the Clinical Decision Transformer recommends medications and contextually embeds sequential EHR data.</div>
- <div style="text-align: justify">We find that the model tends to utilize recent inter-admission information to contextualize the clinical states of the current admission, while when previous information is insufficient, intra-admission contextualization becomes more active.</div>

![attn_pattern](https://user-images.githubusercontent.com/119850923/215553247-4daf4c72-14bd-40a7-a0e1-f2a7c0322d39.png)

<br><br>

<span style="color: #2d6885"><font size="5"><b>Abstract</b></font></span>

<div style="text-align: justify"> With recent achievements in tasks requiring context awareness, foundation models have been adopted to treat large-scale data from electronic health record (EHR) systems. However, previous clinical recommender systems based on foundation models have a limited purpose of imitating clinicians’ behavior and do not directly consider a problem of missing values. In this paper, we propose a Clinical Decision Transformer (CDT), a generative foundation model that recommends intended medications conditioned on a desired goal prompt. For this, we conducted goal-conditioned sequencing, which generated a subsequence of treatment history with prepended future goal state, and trained the CDT to model sequential medications required to reach that goal state. For contextual embedding over intra-admission and inter-admissions, we adopted a GPT-based architecture with an admission-wise attention mask and column embedding. In an experiment, we extracted a diabetes dataset from an EHR system, which contained treatment histories of 4788 patients. We observed that the CDT achieved the intended treatment effect according to goal prompt ranges (e.g., NormalA1c, LowerA1c, and HigherA1c), contrary to the case with  behavior cloning. To the best of our knowledge, this is the first study to explore clinical recommendations from the perspective of goal prompting</div>
<br>
**Keywords:** Clinical Recommender System, Electronic Health Records, Foundation Model, Causal Inference

<br><br>

<span style="color: #2d6885"><font size="5"><b>References</b></font></span>

[1] Bica, I., Alaa, A. M., Jordon, J., and van der Schaar, M.
[Estimating counterfactual treatment outcomes over time
through adversarially balanced representations](https://arxiv.org/abs/2002.04083). arXiv
preprint arXiv:2002.04083, 2020  
[2] American Diabetes Association. [Understanding A1c](https://diabetes.org/diabetes/a1c).  

\* The data extraction process from the EHR system was approved by an official review committee.

