<center><font size="10"><b>Clinical Decision Transformer</b> </font></center>
<center><font size="5">: Intended Treatment Recommendation through Goal Prompting</font></center>
<br/>
<center> <b>Code:</b> soon be available </center>

![녹화_2023_01_30_01_28_50_244](https://user-images.githubusercontent.com/119850923/215343446-a76f7002-c8ef-4fb8-afef-2fea5ff5e1f3.gif)

## TLDR;
We propose a clinical recommender system that generates a sequence of medications to reach a desired clinical state given as a goal prompt.



## Abstract
With recent achievements in tasks requiring context awareness, foundation models have been adopted to treat large-scale data from electronic health record (EHR) systems. However, previous clinical recommender systems based on foundation models have a limited purpose of imitating clinicians’ behavior and do not directly consider a problem of missing values. In this paper, we propose a Clinical Decision Transformer (CDT), a generative foundation model that recommends intended medications conditioned on a desired goal prompt. For this, we conducted goal-conditioned sequencing, which generated a subsequence of treatment history with prepended future goal state, and trained the CDT to model sequential medications required to reach that goal state. For contextual embedding over intra-admission and inter-admissions, we adopted a GPT-based architecture with an admission-wise attention mask and column embedding. In an experiment, we extracted a diabetes dataset from an EHR system, which contained treatment histories of 4788 patients. We observed that the CDT achieved the intended treatment effect according to goal prompt ranges (e.g., NormalA1c, LowerA1c, and HigherA1c), contrary to the case with  behavior cloning. To the best of our knowledge, this is the first study to explore clinical recommendations from the perspective of goal prompting.
