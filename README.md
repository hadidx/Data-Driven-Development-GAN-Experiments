# Data-Driven-Development-GAN-Experiments

The following are part of our data driven modeling course project to train a GAN to generate CT scans of vertebra. The notebooks are based off the tensorflow tutorials: [Deep Convolutional Generative Adversarial Network](https://www.tensorflow.org/tutorials/generative/dcgan) and [Convolutional Variational Autoencoder](https://www.tensorflow.org/tutorials/generative/cvae)

The notebooks require around 25GB of VRAM to run properly. Furthermore, the notebooks assume an environment with CUDA enabled tensorflow setup (v.2.15.0 preferably), matplotlib, numpy, opencv, nibabel, nPerlinNoise, and mrivis setup.

The "CTSpine1K Segmentation Maps Processing" notebook shows how we generated synthetic CT scans from the CTSpine1K dataset segmentation maps. The synthetic data that results from this notebook is stored in the padded_seg2cts3.zip file.

The "dcgan_on_synthetic_spine_cts" shows how to load the data, define a DCGAN, its losses, training step, how to calculate the FID score, and save the results for the synthetic vertebra dataset.

"Variational Autoencoder Synthetic CTs" and "Variational Autoencoder Real CTs" notebooks show how to define convolutional VAEs, their losses, their training step, and how to train them for the synthetic and AUBMC datasets respectivly. Both notebooks are similar with differences being limited to the names of the folders being loaded and files being saved.


The "var_ae_gan_synthetic_data" notebook shows all the steps needed to train a VAE-GAN on the synthetic dataset. "var_ae_gan_real_fractured_data" and "var_ae_gan_real_fractured_data_transfer_learning" show the steps to tain a VAE-GAN from scratch and using tansfer learning on the fractured AUBMC data respectivly. "var_ae_gan_real_healthy_data" and "var_ae_gan_real_healthy_data_transfer_learning" show the steps to tain a VAE-GAN from scratch and using tansfer learning on the healthy AUBMC data respectivly. All notebooks are similar with with differences being limited to the names of the folders being loaded and files being saved.

The "CNN_with_Augmentation" notebook shows how to train and evaluate a CNN on VAE-GAN generated data for both healthy and fractured vertebra.

"var_ae_gan_vs_real_data_using_var_ae" and "var_ae_gan_vs_synthetic_data_using_var_ae" show how the reconstruction loss analysis was done.

Note that all file paths used in the notebooks are based on where we placed our data and code on disc, so feel free to change those paths to suite your setup.

Also, do not the first command that sets the CUDA_DIR and XLA_FLAGS unless tensorflow is not able to find your CUDA install directory. Even then, make sure to change the paths to what corresponds to where CUDA is on your system.

