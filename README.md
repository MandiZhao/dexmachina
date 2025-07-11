# DexMachina: Functional Retargeting for Bimanual Dexterous Manipulation 

[Mandi Zhao](https://mandizhao.github.io), [Yifan Hou](https://yifan-hou.github.io), [Dieter Fox](https://homes.cs.washington.edu/~fox), [Yashraj Narang](https://research.nvidia.com/person/yashraj-narang), [Shuran Song*](https://shurans.github.io), [Ajay Mandlekar*](https://ai.stanford.edu/~amandlek)

*Equal Advising

[arXiv](http://arxiv.org/abs/2505.24853) | [Project Website](https://project-dexmachina.github.io) | [Code Documentation](https://mandizhao.github.io/dexmachina-docs) 

![Teaser](dexmachina-teaser-website.png)

## Code Release Status 
- 06/11/2025: 
Released all dexterous hand assets and ARCTIC assets used in our recent [arXiv preprint](http://arxiv.org/abs/2505.24853). Released detailed instructions for processing new hand assets: see code in `dexmachina/hand_proc` and [hand processing doc page](https://mandizhao.github.io/dexmachina-docs/1_process_hands.html). Pushed a new `dexmachina.yaml` file for conda env install. RL training example in `examples/train_rl.sh`
- 06/03/2025: Initial Release


TODOs 
- [ ] Advanced rendering code
- [ ] RL eval code
- [x] Instructions for processing new hands and demonstrations 

## Installation
 
1. We recommend using conda environment with Python=3.10
```
conda create -n dexmachina python=3.10
conda activate dexmachina
```
2. Clone and install the below custom forks of Genesis and rl-games:

```
pip install torch==2.5.1
git clone https://github.com/MandiZhao/Genesis.git
cd Genesis
pip install -e .
pip install libigl==2.5.1 # NOTE: this is a temporary fix specifically for my fork of Genesis

git clone https://github.com/MandiZhao/rl_games.git
cd rl_games
pip install -e .
```
Additional packages needed for RL training:
```
pip install gymnasium ray seaborn wandb trimesh
# an old version of moviepy
pip install moviepy==1.0.3
```

**If you'd like to install the full conda environment that includes all the packages, use the below yaml file:**
```
# this is obtained from: conda export -f dexmachina.yaml
conda env create -f dexmachina.yaml
```
4. Local install the `dexmachina` package:
```
cd dexmachina
pip install -e .
```

See the full [documentation](https://mandizhao.github.io/dexmachina-docs) for additional installation instructions for dexterous hand and demonstration data processing, kinematic retargeting, raytracer rendering, etc. 


## Citation
This codebase is released with the following preprint:

Zhao Mandi, Yifan Hou, Dieter Fox, Yashraj Narang, Ajay Mandlekar*, Shuran Song*. DexMachina: Functional Retargeting for Bimanual Dexterous Manipulation. arXiV, 2025.

*Equal Advising 

If you find this codebase useful, please consider citing:
```
@misc{mandi2025dexmachinafunctionalretargetingbimanual,
      title={DexMachina: Functional Retargeting for Bimanual Dexterous Manipulation}, 
      author={Zhao Mandi and Yifan Hou and Dieter Fox and Yashraj Narang and Ajay Mandlekar and Shuran Song},
      year={2025},
      eprint={2505.24853},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2505.24853}, 
}
```
