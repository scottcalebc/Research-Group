#compressivesensing #reconstruction #machinelearning #deeplearning 

[Paper](https://www.sciencedirect.com/science/article/abs/pii/S0165168422002766)


# Introduction

Uses [[ Block compressed sensing ]] as [[Compressive Sensing]] framework, but introduces global image priors knowledge to reduce block artifacts in reconstruction.

Use a ML optimization unrolling on deep learning reconstruction step to add interptability to model output at each $k$ steps of unrolling and can optimize for $k$ steps.

This single model also works for various measurement ratios. Utilize standard metrics, [[Structural Similarity Index | SSIM ]] and [[Peak Signal To Noise Ratio | PSNR ]], for validating visual effect distoration.