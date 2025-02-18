# Generative AI

Generative Artificial Intelligence is a field within Machine Learning that creates new content or data that emulates human-generated output. The intention is to produce original content in creative fields like text, music, image, and code generation.

The algorithms used by generative ai is most commonly based on neural networks used to learn patterns and structures. Statistical properties are applied to these algorithms to generate other new samples that share characteristics.

The general process has three steps:

- Training - examples of text, images, or sounds are given to the agent and the model learns statistical relationships between the input content.
- Generation - creation of new content from sampling the learned distribution of input content. A random seed is generated before being iteratively refined based on agent policies aimed towards accurate content creation.
- Evaluation - generated content is assessed for quality, originality, and resemblence to relevant human created content. This evaluation can be subjective or rely on human judgement - or it can be objective and use indicated metrics for specific properties.

####  Concepts

There are various models and concepts that are currently being used within the generative AI space.

##### Latent Space 

Latent Space is a hidden representation of data that captures it's essential features and relationships in a compressed form. Variational Autoencoders (VAE) interpret this compressed representation and use the latent space to generate the new content via sampling.

##### Sampling

Sampling is how new content is generated from existing content. Values for variables are selected in the latent space and then these values are then mapped into the output space. When the quality and range of content is diverse and consistent, the model has learned its given distribution well.

##### Mode Collapse

Mode Collapse is when the generator learns to produce a very limited range of outputs. This is when the agent develops a sort of tunnel vision and fails to fully explore the input content it is training on.

##### Overfitting

Overfitting is a common hurdle in machine learning with respect to generative AI. The agent learns the input data too well to the point where it is including noise and irrelevant information in output. This results in poor generalization where new content differs significantly from the content the model was trained on. Overfitting often leads to limiting the creativity and originality observed in output.

##### Evaluation Metrics

Some metrics used to objectively assess the output and learning capabilities of generative AI are shown below:

- Inception Score (IS) - measures the quality and diversity of output by assessing clarity and diversity of predicted classes.
- Frechet Inception Distance (FID) - compares the distribution of output to distribution of input. Lower scores indicate greater similarity and quality.
- BLEU Score - measures similarities between input and output of generated text, additionally assessing for fluency and accuracy.


### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Generative AI](https://academy.hackthebox.com/module/290/section/3266 "HTB Generative AI")