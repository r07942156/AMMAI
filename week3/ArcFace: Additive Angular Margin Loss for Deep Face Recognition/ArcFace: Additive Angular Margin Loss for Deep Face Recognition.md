### ArcFace: Additive Angular Margin Loss for Deep Face Recognition

https://arxiv.org/pdf/1801.07698.pdf


1. For the softmax loss, the learned features are separable for the closed-set classification problem but not discriminative enough for the open-set face recognition problem.

2. For the triplet loss: (1) there is a combinatorial explosion in the number of face triplets especially for large-scale datasets, leading to a significant increase in the number of iteration steps.

3. Sphereface introduced the important idea of angular margin, their loss function required a series of approximations in order to be computed, which resulted in an unstable training of the network. https://arxiv.org/pdf/1704.08063.pdf

4. The proposed ArcFace has a constant linear angular margin throughout the whole interval. By contrast, SphereFace and CosFace only have a nonlinear angular margin.


對latent feature與最後一層FC layer的weight做normalization然後算cos距離，對此距離取arccos得到角度，將此角度加上一個additive angular margin(在實驗中此margin為0.5)，然後再scale回去算softmax loss。
![image](https://github.com/r07942156/AMMAI/blob/master/week3/ArcFace:%20Additive%20Angular%20Margin%20Loss%20for%20Deep%20Face%20Recognition/f1.PNG)

這個margin可以增加inter-class的discrepancy與intra-class的comcpactness
![image](https://github.com/r07942156/AMMAI/blob/master/week3/ArcFace:%20Additive%20Angular%20Margin%20Loss%20for%20Deep%20Face%20Recognition/f2.PNG)
