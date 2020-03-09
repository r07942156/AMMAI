### Rethinking ImageNet Pre-training

https://arxiv.org/pdf/1811.08883.pdf

1.像VGG16這種淺層網路若參數初始化得當，就可以 be trained from scratch without activation normalization。

2.ImageNet pre-training對於避免overfitting的功效不大，除非訓練的dataset很小(ex:1%的coco dataset)。當使用10% coco dataset訓練時， new hyperparameters must be selected for ﬁne-tuning (from pretraining) to avoid overﬁtting，when training from random initialization using these same hyper-parameters, the model can match the pre-training accuracy without any extra regularization, even with only 10% COCO data. 
 

3.Object detector與image classifier相比，通常會用比較高解析的input image，這會使得batch size變小，進而deterioriate BN的準
  確度，這種情況可以用pre-train的方式來避免， because ﬁne-tuning can adopt the pretraining batch statistics as ﬁxed parameters。

4.Group Normalization 是BN的一種替代方式，對於batch size 比較insentive。

5.train from scratch不影響模型的收斂，只是需要比較多的時間，也能達到不遜色於pre-training的結果(即便在只有10K coco dataset的情況下)。

6.ImageNet pre-training shows no beneﬁt when the target tasks/metrics are more sensitive to spatially welllocalized 
  predictions，也就是說與影像分類相比，ImageNet pre-training在目標檢測的任務上效果比較差。
