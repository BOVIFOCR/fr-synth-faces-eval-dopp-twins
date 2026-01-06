<div align="center">

## Are Synthetic Data As Good As Real Data For <br> Recognizing Doppelgängers and Twins Faces?

[Bernardo BIesseck](https://scholar.google.com.br/citations?user=kuk1sSgAAAAJ)<sup>1,2</sup> &emsp; [Pedro Vidal](https://scholar.google.com/citations?user=VopZ0M8AAAAJ)<sup>1</sup> &emsp; [Luiz Coelho](https://www.researchgate.net/profile/Luiz-Coelho-18)<sup>3</sup>   

[Roger Granada](https://scholar.google.com/citations?user=CMM8xHUAAAAJ)<sup>4</sup> &emsp; [Ruben Tolosana](https://scholar.google.com/citations?user=UHT4WGAAAAAJ)<sup>5</sup> &emsp; [David Menotti](https://scholar.google.com.br/citations?user=Ipu5_-gAAAAJ)<sup>1</sup>  

<sup>1</sup>Depart. of Informatics, Federal University of Paraná, Curitiba, PR, Brazil (e-mail: {bjgbiesseck, pbqv20, menotti}@inf.ufpr.br) <br>
<sup>2</sup>Federal Institute of Mato Grosso (IFMT), Pontes e Lacerda, MT, Brazil (e-mail: bernardo.biesseck@ifmt.edu.br) <br>
<sup>3</sup>Federal University of Minas Gerais (UFMG), Brazil (e-mail: luizcoelho@dcc.ufmg.br) <br>
<sup>4</sup>Unico IDTech, Brazil (e-mail: roger.granada@unico.io) <br>
<sup>5</sup>Biometrics and Data Pattern Analytics Laboratory — BiDA-Lab, Universidad Autónoma de Madrid, Madrid, Spain (e-mail: ruben.tolosana@uam.es) <br>

</div>

---

ABSTRACT: <br>
Synthetic face datasets for training Face Recognition (FR) models have gained significant
interest in recent years due to privacy concerns associated with real facial data. Recent advances in generative
techniques, based mainly on Generative Adversarial Networks (GANs) and Diffusion Models, have led to the
proliferation of various synthetic datasets. Although the performance of FR models trained on synthetic data
is becoming similar to those of models trained on real data when evaluated on standard benchmarks such as
LFW, CFP-FP, AgeDB, and CALFW, little is known about their effectiveness in more challenging scenarios
involving individuals with high facial similarity, such as doppelgängers (lookalikes) and identical twins. This
work addresses this gap by evaluating state-of-the-art FR models trained on real or synthetic datasets across
four testing datasets that feature high facial similarity: HDA Doppelgänger, DoppelVer, 3D-TEC, and ND-
Twins-2009-2010. We analyze verification performances, including subgroup analysis by ethnicity, gender,
and age, to better understand demographic disparities. Our results show that the gap between synthetic and
real face datasets is larger in these challenging scenarios than on typical benchmarks. We also observe similar
biases in FR models trained on synthetic or real data, suggesting that current synthetic datasets may inherit
biases through the use of real data at some stage in their pipeline
