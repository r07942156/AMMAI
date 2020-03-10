###A survey on Image Data Augmentation for Deep Learning
link: https://link.springer.com/content/pdf/10.1186/s40537-019-0197-0.pdf


Data augmentation的方法包含: Flipping, Color space transformations與Cropping, Rotation，透生成對抗樣本(ex:FGSM)也是一種augmentation的方法

Te safety of a Data Augmentation method refers to its likelihood
of preserving the label post-transformation. 
並不是所有資料集都適用於所有的資料增強方法。(ex:當在MNIST上旋轉角度過多時，會使有些data無法辨識)

input image的downsampling也是以視為一種data augmentation，256×256的top-5 error為7.96%，512×512的top-5 error為7.42%，將這兩
個model ensemble起來top-5 error為6.97%，
The researchers found that composing an ensemble of models trained with high and low-resolution images performed
better than any one model individually.

資料集類別的不平衡會使model過擬和在那個類別上
Imbalanced datasets are harmful because they bias models towards majority class predictions. 
