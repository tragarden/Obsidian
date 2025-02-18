# Diffusion Models

Diffusion Models are an example of generative AI that is intended to create high-quality images as output. They feature noise addition and removal methods while learning data distribution to generate images and audio.

Diffusion works by slowly introducing more noise into an input image and then reversing the process to generate new images. Prompts must be refined and thoughtful to produce accurate and desired images.

A Text Encoder like a transformer or CLIP is used to generate the images from a text-based prompt. This produces a latent representation that will then go through the denoising process to make sure the generated image aligns with the descriptions within the text prompt.

This process is detailed below:

1. Text Encoding - the text prompt is encoded using a pre-trained text encoder. The expressions or sentences are converted into high-dimensional vectors that capture the semantic meaning of the given text. The vector is the conditioning input for the diffusion model.
2. Conditioning the Denoising - after a latent representation is created, it is then used to condition the denoising network. This network then predicts the noise that will be removed and ensures that the generated image aligns with the text in the original prompt. This happens with the loss function is modified to include terms that measure discrepancies between generated images and the original text.
3. Sampling - this begins with pure noise until the denoising network uses a noisy image and the embedded text to predict the noise. This allows the generated image to gradually evolve into a match for the original text prompt.
4. Final Image - a final image is produced that is consistent with the provided prompt. This is an iterative process of adding and removing noise based on conditions of the embedded text until a high-quality and accurate image is generated.

#### Forward Process

Noise is gradually added into the data until it is pure noise. This is known as forward diffusion or the noising process.

A mathematical representation of the noising process is below:

>x_T = q(x_T | x_0)

- x_0 is the original input
- x_T is the pure noise
- q(x_T | x_0) is the distribution of noisy data given the original data

The forward process can be described with the following:

>x_t = q(x_t | x_\{t-1})

- t is the time step from 0 to T
- the whole expression is the transition probability from t-1 to t

#### Reverse Process

The Reverse Process is also known as the denoising process and is used to remove the noise from the forward process stages. The neural network is trained to predict the anticipated noise at each step. 

The denoising process is mathematically represented below:

>x_\{t-1} = p_0 (x_\{t-1} | x_t)

- this is the learned distribution parameterized by the model paramerrters 0
- this process minimizes the difference between the predicted and actual noise added in the forward process. This is often achieved using a loss function like the mean squared error (MSE)