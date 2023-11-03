#compressivesensing #deeplearning #CNN #WaveletDomain #geneticalgorithm 
# Introduction

[[ Deep CNN ]] is a robust method to classify an image, when the test image is compressed the accuracy falls. Can be overcomed by training models in the compressed domain which enables faster communication and the need for reconstruction. Compressed Domain Inference is proposed by Calderbank et al. use a [[ Support Vector Machine | SVM ]] for this task and proved classification used the [[ Rate-Adaptive Network ]] proposed by Davenport et al.

[[ Compressive Sensing ]] is a shift in the sampling and compression process, where only the required number of measurements are taken and original signal is reconstructed using optimization techniques.

Xu et al developed a single neural network and used it to categorize data in any measurement rate (MR) using a single-pixel camera. Since a CNN is used and the pixels taken are sparse a single pass reconstruction is done to get a minimum visually legible image to be trained on.


# Proposed Contribution

## Previous work of author
Use a reduced pixel transform of the training images obtained by applying  a binary mask on training/test images and use only _P%_ of pixels in the image. Using [[ Genetic Algorithm-based Compressed Learning ]]( GACL ) which will increase training accuracy by learning the binary mask to apply.

Applying of the binary mask is the [[Compressive Sensing | CS ]] framework and this process reduces the MR, but keep the images legible which can be directly used for training.

## Current proposal
Extend idea of [[Genetic Algorithm-based Compressed Learning| GACL]] in the Wavelet domain, the wavelet is the *best* tool to compress images and masking of wavelet coefficients can be considered as a [[Compressive Sensing | CS ]] process. The wavelet used is the [[ Haar wavelet ]]. The wavelet approximation coefficients only constitutes $1/4$ of the total number of pixels the [[Haar wavelet | Haar ]] approximation coefficient matrix visually resembles the original image. This enables drastically low MR of $10\%$ of $1/4$ of the original image.

To calculate visual quality the [[ Structural Similarity Index | SSIM ]] and the [[ Peak Signal To Noise Ratio | PSNR ]] are used. $S_{avg}$ and $PSNR_{avg}$ represent this. Also $S_{avg}$ decreases as $P\%$ increases, but $S_{avg}$ improves as [[Genetic Algorithm-based Compressed Learning | GACL ]] is applied, which implies that GACL learns the best mask. 

## Key Takeaways
 - A new dataset is created by applying the wavlet transform and only retaining the approximation coefficient images, using [[Haar wavelet]].
 - A structured binary mask is applied retaining only $P\%$ of pixels
- [[Genetic Algorithm-based Compressed Learning | GACL ]] is implemented to learn binary mask
- experiment demonstrated for very low MR of $2.5\%$ 


# Compressed Domain Learning with Haar Wavelet

## Dataset creation
For each image the [[Haar wavelet]] discrete transform is applied to get approximation coefficient matrix and detailed matrices. Th approximation matrix, which is downsampeld and consists of $25\%$ of the original image is kept and the detailed matrices are ignored.

## Binary mask
Key process is to apply a binary mask to retain $P\%$ of the pixels