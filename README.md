<center><font size="10"><b>Clinical Decision Transformer</b> </font></center>
<center><font size="5">: Intended Treatment Recommendation through Goal Prompting</font></center>

<center> <u><b>Code:</b></u> soon be available </center>

<span style="color: #2d6885"><font size="5">Summary</font></span>
- We propose Clinical Decision Transformer, a clinical recommender system that generates a sequence of medications to reach a desired state given as a goal prompt.
![cdt_overview](https://user-images.githubusercontent.com/119850923/215435040-0a80bbac-671f-42c2-8e22-2904d1311fcc.gif)

</br></br>

- We extracted a diabetes dataset from an EHR system and used it to train two models; the proposed Clinical Decision Transformer and Counterfactual Recurrent Network [1] as a recommendation evaluation model.
- We find that recommended medications by the Clinical Decision Transformer shift patients' clinical states (e.g. hemoglobin A1c) in the intended directions (e.g. the normal range of hemoglobin A1c: 4--5.6% [2]) compared to those of factual prescriptions and behavior cloning.

![site_prompting](https://user-images.githubusercontent.com/119850923/215435046-0135fa9e-7929-42dc-9290-578419afde63.png)  


</br></br>

<span style="color: #2d6885"><font size="5">Attention Pattern</font></span>

</br>

<span style="color: #2d6885"><font size="5">Contextual Embedding</font></span>

</br>


<span style="color: #2d6885"><font size="5">Abstract</font></span>

With recent achievements in tasks requiring context awareness, foundation models have been adopted to treat large-scale data from electronic health record (EHR) systems. However, previous clinical recommender systems based on foundation models have a limited purpose of imitating clinicians’ behavior and do not directly consider a problem of missing values. In this paper, we propose a Clinical Decision Transformer (CDT), a generative foundation model that recommends intended medications conditioned on a desired goal prompt. For this, we conducted goal-conditioned sequencing, which generated a subsequence of treatment history with prepended future goal state, and trained the CDT to model sequential medications required to reach that goal state. For contextual embedding over intra-admission and inter-admissions, we adopted a GPT-based architecture with an admission-wise attention mask and column embedding. In an experiment, we extracted a diabetes dataset from an EHR system, which contained treatment histories of 4788 patients. We observed that the CDT achieved the intended treatment effect according to goal prompt ranges (e.g., NormalA1c, LowerA1c, and HigherA1c), contrary to the case with  behavior cloning. To the best of our knowledge, this is the first study to explore clinical recommendations from the perspective of goal prompting.

</br>

<span style="color: #2d6885"><font size="5">References</font></span>

[1] Bica, I., Alaa, A. M., Jordon, J., and van der Schaar, M.
[Estimating counterfactual treatment outcomes over time
through adversarially balanced representations](https://arxiv.org/abs/2002.04083). arXiv
preprint arXiv:2002.04083, 2020  
[2] American Diabetes Association [Understanding A1c](https://diabetes.org/diabetes/a1c). 