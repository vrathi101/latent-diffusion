this is my implementation of a latent diffusion model (ldm) - i used a vae + ddpm (with cross attention to combine text w/ images)
to incorporate image caption embeddings i used pre-trained clip text encoder
similar to what's done in academia, i incorporated cfg (classifier free guidance) by randomly setting caption to null caption so model can learn both conditional and unconditional
then in the sampling process we can guide the model by computing difference between conditional and unconditional noise (which is the "direction")
i wasn't able to actual train this (sadly) b/c i kept getting cuda out of memory (i guess 512x512 resolution with a large dataset is too much for kaggle?)
