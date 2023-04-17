# MasaCtrl -- Mutual Self-Attention Control

Pytorch implementation of MasaCtrl: Tuning-free Mutual Self-Attention Control for **Consistent Image Synthesis and Editing**

[Mingdeng Cao](https://github.com/ljzycmd), [Xintao Wang](https://xinntao.github.io/), [Zhongang Qi](https://scholar.google.com/citations?user=zJvrrusAAAAJ), [Ying Shan](https://scholar.google.com/citations?user=4oXBp9UAAAAJ), [Xiaohu Qie](), [Yinqiang Zheng](https://scholar.google.com/citations?user=JD-5DKcAAAAJ)

---

[Report (coming soon)] **|** [Project Page](https://ljzycmd.github.io/projects/MasaCtrl/)

<div align="center">
<img src="assets/overview.png">
<i> MasaCtrl enables performing various consistent non-rigid image synthesis and editing without fine-tuning and optimization. </i>
</div>


## Introduction

We propose MasaCtrl, a tuning-free method for non-rigid consistent image synthesis and editing. The key idea is to combine the `contents` from the *source image* and the `layout` synthesized from *text prompt and additional controls* into the desired synthesized or edited image, with **Mutual Self-Attention Control**.


## Main Features

### 1 Consistent Image Synthesis and Editing

MasaCtrl can perform prompt-based image synthesis and editing that changes the layout while maintaining contents of source image.

>*The target layout is synthesized directly from the target prompt.*

<div align="center">
<img src="assets/results_synthetic.png">
<i>Consistent synthesis results</i>

<img src="assets/results_real.png">
<i>Real image editing results</i>
</div>


### 2 Integration to Controllable Diffusion Models

Directly modifying the text prompts often cannot generate target layout of desired image, thus we further integrate our method into existing proposed controllable diffusion pipelines (like T2I-Adapter and ControlNet) to obtain stable synthesis and editing results.

>*The target layout controlled by additional guidance.*

<div align="center">
<img src="assets/results_w_adapter.png">
<i>Synthesis (left part) and editing (right part) results with T2I-Adapter</i>
</div>


### 3 Generalization to Other Models: Anything-V4

Our method also generalize well to other Stable-Diffusion-based models.

<div align="center">
<img src="assets/anythingv4_synthetic.png">
<i>Results on Anything-V4</i>
</div>


## Usage (Under Construction)

### Requirements
We implement our method with [diffusers](https://github.com/huggingface/diffusers) code base with similar code structure to [Prompt-to-Prompt](https://github.com/google/prompt-to-prompt). The code runs on Python 3.8.5 with Pytorch 1.11. Conda environment is highly recommended.

```base
pip install -r requirements.txt
```

### Checkpoints

**Stable Diffusion:**
We mainly conduct expriemnts on Stable Diffusion v1-4, while our method can generalize to other versions (like v1-5).

You can download these checkpoints on their official repository and [Hugging Face](https://huggingface.co/).

**Personalized Models:**
You can download personlized models from [CIVITAI](https://civitai.com/) or train your own customized models.


### Notebook Demo

**The notebook `playground.ipynb` provides the synthesis samples.**


## Acknowledgements

We thank awesome research works [Prompt-to-Prompt](https://github.com/google/prompt-to-prompt), [T2I-Adapter](https://github.com/TencentARC/T2I-Adapter).


## Contact

If your have any comments or questions, please [open a new issue]() or feel free to contact [Mingdeng Cao](https://github.com/ljzycmd) and [Xintao Wang](https://xinntao.github.io/).