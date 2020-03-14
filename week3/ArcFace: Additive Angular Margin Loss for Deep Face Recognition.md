### ArcFace: Additive Angular Margin Loss for Deep Face Recognition

https://arxiv.org/pdf/1801.07698.pdf

for the softmax loss, the learned features are separable
for the closed-set classification problem but not discriminative enough for the open-set face recognition problem.

For the triplet loss: (1) there is a combinatorial explosion in the
number of face triplets especially for large-scale datasets,
leading to a significant increase in the number of iteration
steps

Sphereface [18] introduced the important idea
of angular margin, their loss function required a series of approximations in order to be computed, which resulted in an
unstable training of the network
