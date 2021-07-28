# kklgb
- This package is wrapper package for lightgbm( https://github.com/microsoft/LightGBM ).
- You can do training with some useful functions. 

## Installation
```
pip install git+https://github.com/kazukingh01/kklgb.git
```

## Training examples with using Model Zoo
code samples is in "https://github.com/kazukingh01/kktorch/tree/main/tests"

### Run test code
```
# change working directory.
mkdir work
cd ./work
git clone https://github.com/kazukingh01/kktorch.git
cd ./kktorch/tests/
python train_ffn.py
```

## Simple Usage
```
python
>>> import torch
>>> from kktorch.nn import ConfigModule
>>> network = ConfigModule({"name": "test", "network": [{"class": "Linear", "args": [128, 8]}, {"class": "ReLU"}]})
>>> network
ConfigModule(
    (test): ModuleList(
        (0): Linear(in_features=128, out_features=8, bias=True)
        (1): ReLU()
    )
)
>>> network(torch.rand(2, 128))
tensor([[0.0000, 0.0621, 0.0000, 0.4308, 0.0000, 0.0000, 0.0000, 0.0000],
        [0.0000, 0.0377, 0.0000, 0.1924, 0.0000, 0.0000, 0.0788, 0.0000]],
        grad_fn=<ReluBackward0>)
```