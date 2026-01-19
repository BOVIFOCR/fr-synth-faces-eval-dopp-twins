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

---

#### REQUIREMENTS:
 - Python 3.7
 - CUDA 11.3
 - numpy==1.21.6
 - torch==1.10.1
 - torchvision==0.11.2


#### Clone repository
```
git clone https://github.com/BOVIFOCR/fr-synth-faces-eval-dopp-twins.git
cd fr-synth-faces-eval-dopp-twins/recognition/arcface_torch
```

#### Create env and install dependencies
```
ENV_NAME=fr_synth_faces_eval_dopp_twins
conda create --name $ENV_NAME python=3.7 --yes
conda activate $ENV_NAME

conda install cudatoolkit=11.3.1 -c conda-forge --yes    # install CUDA at env
pip3 install numpy==1.21.6
pip3 install torch==1.10.1 torchvision==0.11.2 --extra-index-url https://download.pytorch.org/whl/cu113
pip3 install -r requirement_ufpr_facerec.txt
```


#### Test simple face recognition

- Download the trained model ResNet100/ArcFace `ms1mv3_arcface_r100_fp16/backbone.pth` from [OneDrive](https://1drv.ms/u/s!AswpsDO2toNKq0lWY69vN58GR6mw?e=p9Ov5d) and save it to subfolder `trained_models/ms1mv3_arcface_r100_fp16`
![Instructions to download ms1mv3_arcface_r100_fp16/backbone.pth](recognition/arcface_torch/examples/download_instructions.png "Download ms1mv3_arcface_r100_fp16/backbone.pth")


- Run `test_UFPR_FaceRec.py`

```
cd recognition/arcface_torch
python test_UFPR_FaceRec.py --network r100 --model trained_models/ms1mv3_arcface_r100_fp16/backbone.pth --img1 examples/Aaron_Eckhart/0.png --img2 examples/Aaron_Eckhart/1.png

OUTPUT:
Loading model r100: 'trained_models/ms1mv3_arcface_r100_fp16/backbone.pth'
Loading img1 'examples/Aaron_Eckhart/0.png'
    img1.shape: torch.Size([3, 112, 112])
Loading img2 'examples/Aaron_Eckhart/1.png'
    img2.shape: torch.Size([3, 112, 112])
Making batch
    batch.shape: torch.Size([2, 3, 112, 112])
Computing embeddings
    embeddings.shape: (2, 512)
Similarity: 0.6534208
Same person!
```

![Verification pipeline](recognition/arcface_torch/examples/verification_pipeline.png "Verification pipeline")

---
