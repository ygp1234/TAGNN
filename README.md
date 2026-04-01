TAGNN
===============================================================================


Code for paper [**TAGNN: Topology-aware Graph Neural Network Framework for Link Prediction**](comming soon...)

This implementation of PairRE for [**Open Graph Benchmak**](https://arxiv.org/abs/2005.00687) datasets (ogbl-wikikg and ogbl-biokg) is based on [**OGB**](https://github.com/snap-stanford/ogb). Thanks for their contributions.

Requirements
------------

Install [PyTorch](https://pytorch.org/)

Install [PyTorch\_Geometric](https://rusty1s.github.io/pytorch_geometric/build/html/notes/installation.html)

Install [Networkx](https://networkx.org/documentation/stable/install.html)

Install [OGB](https://ogb.stanford.edu/docs/home/)

Other required python libraries include: numpy, scipy, tqdm etc.


Usages
------

### ogbl-vessel

```
    python3 train.py --hidden_channels 128 --max_nodes_per_hop 100 --grpe_cross --device 0 --num_heads 8 --dataset ogbl-vessel --use_feature --use_feature_GT --use_edge_weight --epochs 20 --train_percent 100 --val_percent 100 --test_percent 100 --model DGCNNGraphormer_noNeigFeat --runs 10 --batch_size 256 --lr 0.0001 --num_workers 24 --dynamic_train --dynamic_val --dynamic_test --use_len_spd --use_num_spd --use_cnb_jac
```
or
```
    sh train_vessel.sh
```

### ogbl-citation2

```
    python3 train.py --ngnn_code --grpe_cross --device 0 --num_heads 8 --dataset ogbl-citation2 --use_feature --use_feature_GT --use_edge_weight --epochs 15 --train_percent 8 --val_percent 4 --test_percent 0.2 --model NGNNDGCNNGraphormer_noNeigFeat --runs 10 --batch_size 64 --lr 2e-05 --num_workers 24 --dynamic_train --dynamic_val --dynamic_test --use_len_spd --use_num_spd --use_cnb_jac --use_cnb_aa
```
or
```
    sh train_citation2.sh
```

### ogbl-ppa

```
    python3 train.py --eval_hits_K 45 60 75 100 --device 0 --ngnn_code --grpe_cross --num_heads 8 --ngnn_type input --num_ngnn_layers 1 --hidden_channels 96 --dataset ogbl-ppa --use_feature --use_feature_GT --epochs 4 --train_percent 60 --val_percent 40 --test_percent 1 --model NGNNDGCNNGraphormer_noNeigFeat --runs 10 --batch_size 128 --lr 0.00015 --num_workers 48 --dynamic_train --dynamic_val --dynamic_test --use_len_spd --use_num_spd --use_cnb_jac --use_cnb_aa --use_cnb_ra
```
or
```
    sh train_ppa.sh
```
### Note!

Due to the institutional intellectual property rights (IPR) and confidentiality agreements, the trained model weights are not publicly available at this stage. However, all analysis scripts, preprocessing codes, and implementation details required to reproduce the experimental results have been deposited in a public repository.