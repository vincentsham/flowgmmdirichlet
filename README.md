# FlowGMMDirichlet

The visualizations are captured the latent space of training data at training step 0-9, 10, 20, 30, ..., 80, 90, 100, 200, 300, ..., 3800, 3900, 4000.

The 'x's represent the latent space output of training data. The dot and circle correspond to the mean and std of GMM components. During training, the GMM components either disappear or turn from grey to the assigned class color. The 

### Pinwheels
#### FlowGMMDirichlet (20 clusters, learning rate of GMM and Dir = 1e-1)
<img src="pinwheels_1e-1_0.gif" width="60%" height="60%">

<ul>
  <li>The latent outputs first shrink to the middle at the first couple steps.</li>
  <li>The GMM components are also followed the latent outputs to move to the middle.</li>
  <li>At step 300, GMM components and latent outputs start to move away from the middle to create 5 clusters.</li>
</ul>

#### FlowGMMDirichlet (20 clusters, learning rate of GMM and Dir = 1e-2 (left) and 1e-3 (right))
<p float="left">
    <img src="pinwheels_1e-2_0.gif" width="45%" height="45%">
    <img src="pinwheels_1e-3_0.gif" width="45%" height="45%">
</p>

<ul>
  <li>Both GMM components have very little moment. At the begining, they follow the latent outputs to move toward center a bit. Then, they move away from the center slowly.</li>
  <li>Most GMM components slowly disappear as the model learns to discard them.</li>
  <li>With lr=1e-3, the colors of GMM components are not very sharp. I think it would turn the color sharper with more training epochs</li>
</ul>

#### FlowGMM (prior trainable (left) and non-trainable (right))
<p float="left">
    <img src="pinwheels_flowgmm_trainable_0.gif" width="45%" height="45%">
    <img src="pinwheels_flowgmm_0.gif" width="45%" height="45%">
</p>

<ul>
  <li>A major artifact is that FlowGMM tries to merge two orange clusters together while the gap in between has some blue points.</li>
</ul>

### 2 Rings
#### FlowGMMDirichlet (20 clusters, learning rate of GMM and Dir = 1e-1)
<p float="left">
    <img src="circles_1e-1_0.gif" width="45%" height="45%">
    <img src="circles_1e-1_1.gif" width="45%" height="45%">
</p>
<p float="left">
    <img src="circles_1e-1_3.gif" width="45%" height="45%">
    <img src="circles_1e-1_2.gif" width="45%" height="45%">
</p>

<ul>
  <li>The topologies of top left, top right and bottom left are totally different. The top left, top right and bottom left converges to 3, 2, 4 clusters, respectively.</li>
  <li>The bottom right seems to have an issue, which few of the orange data are in the bottom blue cluster. Training with more epochs may mitigate the issue.</li>
</ul>

#### FlowGMMDirichlet (20 clusters, learning rate of GMM and Dir = 1e-2 (left) and 1e-3 (right))
<p float="left">
    <img src="circles_1e-2_0.gif" width="45%" height="45%">
    <img src="circles_1e-3_0.gif" width="45%" height="45%">
</p>

<ul>
  <li>Same as above. The GMM components do not move.</li>
  <li>The model just learns to move the latent outputs toward those GMM components to form clusters and discard the unused GMM components.</li>
</ul>

#### FlowGMM (prior trainable (left) and non-trainable (right))
<p float="left">
    <img src="circles_flowgmm_trainable_0.gif" width="45%" height="45%">
    <img src="circles_flowgmm_0.gif" width="45%" height="45%">
</p>

<ul>
  <li>FlowGMM performs well in this case. The model just needs to focus on moving the latent outputs toward two clusters.</li>
</ul>

In general, FlowGMMDirichlet seems harder to train based on the visualization. I may examine whether training with more epochs can improve the performance further.
