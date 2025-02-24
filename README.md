<div align="center">
    <img src="https://github.com/ganler/nnsmith-logo/raw/master/nnsmith-logo.svg" align="right" height="240"/>
</div>

# NNSmith

<p align="center">
    <a href="https://github.com/ise-uiuc/nnsmith/actions/workflows/ci.yaml"><img src="https://github.com/ise-uiuc/nnsmith/actions/workflows/ci.yaml/badge.svg">
    <a href="https://pypi.org/project/nnsmith/"><img src="https://img.shields.io/pypi/v/nnsmith?color=g">
    <a href="https://github.com/ise-uiuc/nnsmith/blob/main/LICENSE"><img src="https://img.shields.io/pypi/l/nnsmith"></a>
</p>

NNSmith is a random DNN generator and a fuzzing infrastructure, primiarily designed for automatically validating deep-learning frameworks and compilers.

## Support Table

<center>

| Models | [`tvm`](https://github.com/apache/tvm) | [`onnxruntime`](https://github.com/microsoft/onnxruntime) | [`tensorrt`](https://github.com/NVIDIA/TensorRT) | [`tflite`](https://www.tensorflow.org/lite) | [`xla`](https://www.tensorflow.org/xla) | [`torchjit`](https://pytorch.org/docs/stable/jit.html) |
| ------------ | ------------------------------------ | ----------------------------------------------- | ---------------------------------------------- | ----------------------------------------- | ------------------------------------- | ----------------------------------------------------- |
| ONNX         | ✅                                    | ✅                                               | ✅                                              |                                           |                                       |                                                       |
| TensorFlow   | 🔨                                    |                                                 |                                                | ✅                                         | ✅                                     |                                                       |
| PyTorch      | 🔨                                    | 🔨                                               |                                                |                                           |                                       | ✅                                                     |




✅: Supported; ⚠️: Experimental support; 🔨: Coming soon;

</center>

## Setup

**Install latest code (GitHub HEAD):**

```shell
pip install "git+https://github.com/ise-uiuc/nnsmith@main#egg=nnsmith[torch,onnx]" --upgrade
# [optional] add more front- and back-ends such as [tf] and [tvm,ort,xla,...] in "[...]"
```

<details><summary><b>Install latest stable release: </b> <i>[expand]</i></summary>
<div>

```shell
pip install "nnsmith[torch,onnx]" --upgrade
```

</div>
</details>


## Quick Start

<details><summary><b>Setting up graphviz for debugging</b> <i>[expand]</i></summary>
<div>

Graphviz provides `dot` for visualizing graphs in nice pictures. But it needs to be installed via the following methods:

```shell
sudo apt-get install graphviz graphviz-dev      # Linux
brew install graphviz                           # MacOS
conda install --channel conda-forge pygraphviz  # Conda
choco install graphviz                          # Windows

pip install pygraphviz  # Final step.
```

Also see [pygraphviz install guidance](https://pygraphviz.github.io/documentation/stable/install.html).

</div>
</details>

```shell
# Generate a random model in "nnsmith_outputs/*"
nnsmith.model_gen model.type=onnx debug.viz=true
```

See other commands under [`doc/cli`](doc/cli.md). We use [hydra](https://hydra.cc/) to manage configurations. See `nnsmith/config/main.yaml`.

## Contributing Guide

Please check [doc/CONTRIBUTING.md](doc/CONTRIBUTING.md).

## Papers

<details><summary><b>NNSmith: Generating Diverse and Valid Test Cases for Deep Learning Compilers.</b> <i>[expand citation]</i></summary>
<div>

```bibtex
@inproceedings{liu2023nnsmith,
  title={Nnsmith: Generating diverse and valid test cases for deep learning compilers},
  author={Liu, Jiawei and Lin, Jinkun and Ruffy, Fabian and Tan, Cheng and Li, Jinyang and Panda, Aurojit and Zhang, Lingming},
  booktitle={Proceedings of the 28th ACM International Conference on Architectural Support for Programming Languages and Operating Systems, Volume 2},
  pages={530--543},
  year={2023}
}
```

</div>
</details>

<p align="center">
    <a href="https://dl.acm.org/doi/10.1145/3575693.3575707"><img src="https://img.shields.io/badge/Paper-ASPLOS'23-a55fed.svg"></a>
    <a href="https://arxiv.org/abs/2207.13066"><img src="https://img.shields.io/badge/arXiv-2207.13066-b31b1b.svg"></a>
    <a href="http://nnsmith-asplos.rtfd.io/"><img src="https://img.shields.io/badge/artifact-doc-black.svg"></a>
    <a href="https://github.com/ganler/nnsmith-asplos-artifact"><img src="https://img.shields.io/badge/artifact-git-black.svg"></a>
    <a href="https://doi.org/10.5281/zenodo.7222132"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.7222132.svg"></a>
</p>
