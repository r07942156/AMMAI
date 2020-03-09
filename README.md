### Rethinking ImageNet Pre-training

https://arxiv.org/pdf/1811.08883.pdf

像VGG16這種淺層網路若參數初始化得當，就可以 be trained from scratch without activation normalization。

ImageNet pre-training對於避免overfitting的功效不大，除非訓練的dataset很小(ex:百分之一的coco dataset)。

Object detector與image classifier相比，通常會用比較高解析的input image，這會使得batch size變小，進而deterioriate BN的準
確度，這種情況可以用pre-train的方式來避免， because ﬁne-tuning can adopt the pretraining batch statistics as ﬁxed parameters。

Group Normalization 是BN的一種替代方式，對於batch size 比較insentive。

train from scratch不影響模型的收斂，只是需要比較多的時間，也能達到不遜色於pre-training的結果(即便在只有10K coco dataset的情況下)。
