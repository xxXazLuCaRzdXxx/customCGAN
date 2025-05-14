## cGAN

It stands for Conditional Generative Adversarial Network, a deep learning architecture trained for generating images given a lable.

## How it works under the hood:

It plays the same minimax game as GAN, but with slight modification. We pass on the class label as an additional input to both, Generator and Discriminator.
<br/>
Like the GAN, Generator component is tasked with fooling the Discriminator, it samples a random noise from the distribution along with a random class label, they are provided as input to the Discriminator.
<br/>
The Discriminator component is tasked with identifying whether the image belonging to the given class label is real.
<br/>

### Loss function:
It uses the same loss function but with modifications only to the inputs of Generator and Discriminator.
<br/>
In practice we use the following loss function:
<br/>
<br/>
For Discriminator: Minimize *L*D​    =    −Ex,y∼P*data*​(x,y) ​[logD(x,y)]  −  Ez∼Pz​,y∼Py ​​[log(1−D(G(z,y),y))]
<br/>
For Generator: Minimize *L*G    ​=    −Ez,y∼Pz​ *×* Py ​​[logD(G(z,y),y)]
<br/>
*Symbols have there usual meanings*

<br/>


After training, the Generator would generate images belonging to the given class label that would be similar to the those of the respective dataset.

