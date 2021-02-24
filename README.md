# FlowGMMDirichlet

The visualizations are captured the latent space of training data at training step 0-9, 10, 20, 30, ..., 80, 90, 100, 200, 300, ..., 3800, 3900, 4000.

The 'x's represent the latent space output of training data. The dot and circle correspond to the mean and std of GMM components. During training, the GMM components either disappear or turn from grey to the assigned class color. The 

### Pinwheels

<figure>
  <img src="pinwheels_1e-1_0.gif" width="60%" height="60%">
  <figcaption> Pinwheels (learning rate of GMM and Dir = 1e-1) </figcaption>
</figure>
<ul>
  <li>The latent outputs first shrink to the middle at the first couple steps.</li>
  <li>The GMM components are also followed the latent outputs to move to the middle.</li>
  <li>At step 300, GMM components and latent outputs start to move away from the middle to create 5 clusters.</li>
</ul>

<figure style='content: "";clear: both;display: table;'>
    <figure style='content: "";clear: both;display: table;float:left;'>
    <img src="pinwheels_1e-2_0.gif" width="40%" height="40%" >
    <figcaption> Pinwheels (learning rate of GMM and Dir = 1e-2) </figcaption>
    </figure>
    <figure style='content: "";clear: both;display: table;float:left;'>
    <img src="pinwheels_1e-3_0.gif" width="40%" height="40%" >
    <figcaption> Pinwheels (learning rate of GMM and Dir = 1e-3) </figcaption>
    </figure>
</figure>



