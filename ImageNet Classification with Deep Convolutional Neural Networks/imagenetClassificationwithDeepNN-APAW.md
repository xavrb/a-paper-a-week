# ImageNet Classification with Deep Convolutional Neural Networks (A summary) [1st Week APAW]  

## Why?
As Shagun Sodhani (https://shagunsodhani.in) says in his own APAW post, the idea behind writing this kind of posts is to have a summary of the papers we read each week. For a better understanding of ours and others. But, in my opinion this accomplishes another job; it creates a reading habit and kind of forces you to keep the pace, and for a big time procrastinator as myself I think that’s great.  

Also, I’m following the guidelines suggested in “How to read a research paper” written by Dr. Michael Mitzenmacher (Harvard), which can be found here, and also Dr. Jason Eisner’s (JHU) post “How to Read a Technical Paper” which you can read here.  

For my first week on APAW I read the paper ImageNet Classification with Deep Convolutional Neural Networks written by Alex Krizhevsky, Sutskever, Ilya and Hinton, Geoffrey E. it describes how they trained a large deep convolutional neural network with the ImageNet ILSVRC-2010 dataset, having an improvement over state-of-the-art methods (lower error rates). They describe the 8 layer architecture they designed for that purpose and the challenges they had to overcome (overfitting), using a method called dropout.

# Summary  

In order to accomplish object recognition we should use a deep learning approach. Normally to do this, with an acceptable accuracy, a large amount of samples is needed to tackle realistic settings; one of those large data sets that can be used for this is ImageNet (>15M labeled HD images and 22K categories).  

In order to learn from huge datasets as ImageNet, one have to use approaches such as CNN (convolutional neural networks), since we have to compensate for all the data we dont have (even on ImageNet). CNN’s are easier to train and can give more strong and correct assumptions about the nature of the images we are training with.  

Nevertheless, althought CNN’s are powerful, it’s still very expensive to apply them on large datasets of high quality images by their own. So, a combination of CNN’s, GPU and 2D convolution optimized algorithms are the way to go in this case; and as faster GPU’s are available one would be able to get improved results while using this models.  

The paper describes the architecture used in this case, namely, an 8 layer CNN; with 5 **convolutional** layers and 3 **fully connected**.  

It’s important to mention the fact that the team didn’t use the standard way to model a neuron output, namely tanh neurons *(f(x)=tanh(x))*, but they based their work on Rectified Linear Units, whose are way faster when training and they don’t need input normalization to prevent them from saturating.  

Also, workload as divided among 2 GPUs, putting half the neurons on each and connecting them in certain layers.  

As the most remarcable things that came out of this paper we can mention:
Error rates were reduced, as compared to state-of-art methods. Namely, Top-1 and Top-5 error rates of 37.5% & 17% were achieved.  

Due to the size of the data set, overfitting was a big issue, that was dealt with using 2 primary methods, namely, data augmentation and dropout.
The neural network, as big as it was, had to be divided among 2 GPU’s.  

# My thoughts
Personally, I think reducing the percentages from 47.1% & 28.2% to 37.5% & 17% on Top-1 and Top-5 error rates respectively is an amazing task acomplished. And the reduction of those error rates would decrease marginally by using some tricky methods, namely, pooling overlapping, which redices the rate error by 0.4% and 0.3%.  

As they state, one has to be very careful when designing the CNN beause even the minimum modification can backfire greatly.  

One can find himself thinking about how much this results can be improved, maybe in the next 2 decades when we can develop GPUS twice as fast as the ones we can get nowadays. But one has to take into account increasing the size f the data set can bring new challenges that may need all that computing power to be solved.
