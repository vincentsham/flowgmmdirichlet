# FlowGMMDirichlet

The visualizations are captured the latent space of training data at training step 0-9, 10, 20, 30, ..., 80, 90, 100, 200, 300, ..., 3800, 3900, 4000.

The dot and circle correspond to the mean and std of GMM components. During training, the GMM components either disappear or turn from grey to the assigned class color. 

### Pinwheels (learning rate of GMM and Dir = 1e-1)
<img src="pinwheels_1e-1_0.gif" width="60%" height="60%">
<ul>
  <li>The latent outputs first shrink to the middle at the first couple steps.</li>
  <li>The GMM components are also followed the latent outputs to move to the middle.</li>
  <li>At step 300, GMM components and latent outputs start to move away from the middle to create 5 clusters.</li>
</ul>

### Pinwheels (learning rate of GMM and Dir = 1e-2 and 1e-3)
<img src="pinwheels_1e-2_0.gif" width="60%" height="60%">
<img src="pinwheels_1e-3_0.gif" width="60%" height="60%">
