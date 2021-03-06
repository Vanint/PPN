# PPN
We provide the original implementation for "Cost-Sensitive Portfolio Selection via Deep Reinforcement Learning (IEEE TKDE 2020)".
The paper is available [[here](https://arxiv.org/pdf/2003.03051.pdf)].\
Note that this library is several versions ahead of the article. The main difference is the decision making module, where we develop a new leverage operation that contributes a lot.


## Dependencies
Python 2.7\
Tensorflow>=1.4.0\
Tflearn>=0.3.2\
pympler>=0.5\
cvxopt>=1.1.9\
seaborn>=0.8.1\
pandas>=0.20.3


## Usage
### Dataset
The attached dataset is the S&P500, whose description can be found in the paper.\
Please download the dataset [[here](https://drive.google.com/file/d/1_HmTwuJky-al7jDQYpBGcPPj3o6F85Yf/view?usp=sharing)], and put the dataset file (databse) in the main directory.

### Training
There are three steps (Please use this code after downloading the dataset):
1. go into train_package/1 file, and modify the net_config.json file for parameter setting (one can also construct train_package/2)
2. vim the main.py file, and set a specific GPU device
3. python main.py --mode=train --process=1\
(logging information: view train_package/1/programlog)

### Backtest
python main.py --mode=backtest --algo=1 \
(--algo could be either the name of traditional method or the index of training folder)

### Save and Restore of the Model
The trained weights of the network are saved at train_package/1 named as netfile (including 3 files)

### Plotting
python main.py --mode=plot --algos=crp,olmar,1 --labels=crp,olmar,ours\
(--algos could be the name of the tdagent algorithms or the index of nnagent)\
(--labels is the name of related algorithm that will be shown in the legend)

### Present backtest results in a table
python main.py --mode=table --algos=1,olmar,ons --labels=nntrader,olmar,ons


## Acknowledgement
This project is constructed based on the open source project:
* [PGPortfolio toolbox(https://github.com/ZhengyaoJiang/PGPortfolio)]

It would not have been finished without using the codes from the following open source projects:
* [Online Portfolio Selection toolbox](https://github.com/OLPS/OLPS)
 
## Risk Disclaimer
There is always risk of loss in trading. **All trading strategies are used at your own risk**.

## Citation:
If you use this code, please cite:
```
@article{zhang2020cost,
  title={Cost-sensitive portfolio selection via deep reinforcement learning},
  author={Zhang, Yifan and Zhao, Peilin and Li, Bin and Wu, Qingyao and Huang, Junzhou and Tan, Mingkui},
  journal={IEEE Transactions on Knowledge and Data Engineering},
  year={2020},
  publisher={IEEE}
}  
```
