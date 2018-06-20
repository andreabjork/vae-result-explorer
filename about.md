---
layout: default
title: About
permalink: /about/
---
{:.large_header}
Parallel variational autoencoders for image segmentation

{:.subtext}
A summary of the VAE project and its results.

{:.subtext}
Andrea Björk Björnsdóttir

# The Idea

The following diagram outlines the general idea of the network structure. The shared encoder has the first convolutional layers of the variational autoencoders for feature extraction. The decoders each output an image along with the confidence for each pixel. Thus the weighted sum over the images yields the reconstructed image. 

![]({{"/assets/cnn.png"| absolute_url}}){:.center}

The loss function for a traditional variational autoencoder is


In the network above, the loss factor is added up and tthe KL term is captured by taking the sum of squares over the autoencoders. 

# Google's Deepmind Lab

{:.spacious}
Data is generated using Google's Deepmind Lab. 
A rotating agent is used to capture 2D snapshots of the environment which contains several rotating objects. The snapshot images are 128 by 128 pixels.



![jekyll](https://media.giphy.com/media/2vkl7bbV5DFqu9UK2y/giphy.gif){:.center .gifstyle}

 
# First look at the results

| Snapshot of experiment 201805081625 | [Go to experiment](http://127.0.0.1:4000/vae-result-explorer/experiments/2018/05/09/exp201805081625.html){:.exp_link} |
| -----------------------------------|
| Latent Dimension         | 100     |
| KL multiplier            | 0.00003 |
| KL individual multiplier | 2       |
| KL individual exponent   | 2       |
| Autoencoders used		   | 5       |

![]({{"/assets/images/201805081625/1.png"| absolute_url}})
![]({{"/assets/images/201805081625/4.png"| absolute_url}})
![]({{"/assets/images/201805081625/6.png"| absolute_url}})
![]({{"/assets/images/201805081625/7.png"| absolute_url}})

# Improvements to the loss

| Snapshot of experiment 201805091727 | [Go to experiment](http://127.0.0.1:4000/vae-result-explorer/experiments/2018/05/09/exp201805091727.html){:.exp_link} |
| -----------------------------------|
| Latent Dimension         | 100     |
| KL multiplier            | 0.0000 |
| KL individual multiplier | 2       |
| KL individual exponent   | 2       |
| Autoencoders used		   | 5       |

![]({{"/assets/images/201805091727/1.png"| absolute_url}})
![]({{"/assets/images/201805091727/4.png"| absolute_url}})
![]({{"/assets/images/201805091727/6.png"| absolute_url}})
![]({{"/assets/images/201805091727/7.png"| absolute_url}})


# Introducing more complicated objects

Now using a simplistic background, the former objects have been swapped out for more complicated forms such as a car, a tv and a hat.

![jekyll](https://media.giphy.com/media/8lSYcEIyfUMQzn6rC9/giphy.gif){:.center .gifstyle}

# Common problems 

| Snapshot of experiment 201806040130 | [Go to experiment](http://127.0.0.1:4000/vae-result-explorer/experiments/2018/06/04/exp201806040130.html){:.exp_link} |
| -----------------------------------|
| Latent Dimension         | 100     |
| KL multiplier            | Linearly scaled from 3e-10 to 3e-09 |
| KL individual multiplier | 2       |
| KL individual exponent   | 2       |
| Autoencoders used		   | 6       |

![]({{"/assets/images/201806040130/1.png"| absolute_url}})
![]({{"/assets/images/201806040130/2.png"| absolute_url}})
![]({{"/assets/images/201806040130/4.png"| absolute_url}})
![]({{"/assets/images/201806040130/9.png"| absolute_url}})

# How to improve 

| Snapshot of experiment 201806051754 | [Go to experiment](http://127.0.0.1:4000/vae-result-explorer/experiments/2018/06/06/exp201806051754.html){:.exp_link} |
| -----------------------------------|
| Latent Dimension         | 100     |
| KL multiplier            | Linearly scaled from 3e-11 to 3e-10 |
| KL individual multiplier | 2       |
| KL individual exponent   | 4       |
| Autoencoders used		   | 6       |

![]({{"/assets/images/201806051754/1.png"| absolute_url}})
![]({{"/assets/images/201806051754/4.png"| absolute_url}})
![]({{"/assets/images/201806051754/5.png"| absolute_url}})
![]({{"/assets/images/201806051754/7.png"| absolute_url}})
![]({{"/assets/images/201806051754/9.png"| absolute_url}})

[Similar results with 5 autoencoders](http://127.0.0.1:4000/vae-result-explorer/experiments/2018/06/07/exp201806070038.html) 

# Current outlook 

| Snapshot of experiment 201806160741 | [Go to experiment](http://127.0.0.1:4000/vae-result-explorer/experiments/2018/06/16/exp201806160741.html){:.exp_link} |
| -----------------------------------|
| Latent Dimension         | 100     |
| KL multiplier            | Linearly scaled from 6e-12 to 3e-11 |
| KL individual multiplier | 10       |
| KL individual exponent   | 4       |
| Autoencoders used		   | 5       |

![]({{"/assets/images/201806160741/1.png"| absolute_url}})
![]({{"/assets/images/201806160741/4.png"| absolute_url}})
![]({{"/assets/images/201806160741/6.png"| absolute_url}})
![]({{"/assets/images/201806160741/9.png"| absolute_url}})

# Classification based on latent representation

Currently the focus is on classifying the images based on the latent representations the network learns. A simple neural network takes the latent representations and labels as inputs and outputs the likelyhood of each kind of object being seen on the image. This is a work in progress but an example can be seen in [experiment 201806201953](http://127.0.0.1:4000/vae-result-explorer/experiments,/classifier/2018/06/20/exp201806201953.html){:.exp_link}

![]({{"/assets/images/201806201953/0.png"| absolute_url}}){:.center}
![]({{"/assets/images/201806201953/1.png"| absolute_url}}){:.center}
![]({{"/assets/images/201806201953/4.png"| absolute_url}}){:.center}