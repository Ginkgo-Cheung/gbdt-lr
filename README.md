# gbdt+lr  
参考Facebook论文：http://www.herbrich.me/papers/adclicksfacebook.pdf  
##### 原理：GBDT是一种常用的非线性模型，基于集成学习中boosting的思想，由于GBDT本身可以发现多种有区分性的特征以及特征组合，决策树的路径可以直接作为LR输入特征使用，省去了人工寻找特征、特征组合的步骤。所以可以将GBDT的叶子结点输出，作为LR的输入，如图所示：
![](https://upload-images.jianshu.io/upload_images/4155986-8a4cb50aefba2877.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/508)  

## 数据集  
数据集采用criteo-Display Advertising Challenge比赛的部分数据集，比赛地址： https://www.kaggle.com/c/criteo-display-ad-challenge/data 全部的数据集下载：http://labs.criteo.com/2014/02/kaggle-display-advertising-challenge-dataset/

### lr:
train-logloss:  0.117204349458  
val-logloss:  0.594054488135  

### gbdt:
train-logloss: 0.319873  
val-logloss: 0.521285  

### gbdt+lr:
tr-logloss:  0.261914566568  
val-logloss:  0.502417918338  

##### 综上：gbdt+lr的val-logloss最小。但是gbdt+lr并不是适用于所有的业务数据，当存在高度稀疏特征的时候，线性模型一般会优于非线性模型。  

### FFM：
![](https://note.youdao.com/yws/api/personal/file/156F8B3B13E042909520348E80D105E0?method=download&shareKey=bb75dc742741374a2adb14fd83cd0164)   

### gbdt+FFM
![](https://note.youdao.com/yws/api/personal/file/7BC3F5E9E84C48CEA0F9D8E731728B7E?method=download&shareKey=30492d70d1e4ebe84276984ea832a262) 

#### gbdt+FFM的效果要优于FFM
