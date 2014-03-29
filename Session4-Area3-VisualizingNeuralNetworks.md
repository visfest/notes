## Visualizing neural networks at d3.unconf

_(some rough notes of a meandering conversation)_

Can we find a new idea/concept for visualizing neural networks? How can we visualize the fact that a bunch of neuron weights can pick up features we didn't realize were there?

* The textbook picture is pretty basic
* Also it doesn't work so well for deep learning (thousands of layers)

Consider brain researchers using fMRI to follow oxygen flow through the brain (as a proxy for which bits of the brain are "on" at any given time. Can we do an artificial neural network visualization to track the data / track the flow of things that are on?

The brain has functional regions / bits that can be lost and still have the whole machine function, so maybe we can group the nodes like that.

One approach for understanding a thing is to break it down to an algorithm -- first this happens, then that, then the next step. Can we visualize the steps of a neural network? Can we group the "functional regions" that are activating with a particular input?

What about taking the dataset you're working with, and visualizing how the NN works through that information? We'll try jumping in with an example (e.g. the canonical digit OCR dataset).

Talking about "operant conditioning" experiments where you have an animal, a sound plays, then you blow a puff of air at its eyes 80ms later, and does it learn to blink ahead of time. There are auditory neurons that pick up the sound, and motor neurons that trigger the blink, and there's some mystery process in between.

We decide that this visualization is too complicated, and talk about the model of a single neuron instead. It might be best to start with a single component and then describe how that builds up into the entire network.

Or maybe we should go in the other direction, start with the data and discuss the relative influence of different parts of the data? Either way we have a lot of possibilities, and maybe we want to simplify things for our visualization.

A good research/learning tool would be a visualization of the neurons in the network, you train it and then see all the weights. But then you could go and change weight values with sliders/knobs and see the effect on the output -- a little like the decision-tree pictures of BigML. (How much can you perturb the network and still get the same output? If you change this value radically, what happens?)

Another way of thinking about the weights is in a hyperplane, and that the weights represent a vector that you want to move in towards a cone of successful outputs. To some extent this is the general problem -- we have an n-dimensional thing that we want to make sense of for normal people. Maybe there is some projected image of the hyperplane which changes as you twiddle weight values for the neurons.

Alternatively, perhaps a grid/cube of each neuron and each time step, and a circle or color-coded thing how they fire in each subsequent cycle. If you try to keep a dense path through the timeline, you might see a pattern in the movement of the neurons that might be insightful towards the structure of the network. The animal example above involves modelling multiple systems that react differently, and something like this might help to understand how they react.

We want to watch activation (in number of neurons) change over time, and maybe we should look at different graphs of that with different input data? So e.g. in the OCR example, if you draw a 5 and a 6 and a bunch of shapes in between, there's something that happens in the middle to make a decision of "is this 5" or "is this 6". So if you watch the pattern of activation of neurons along that spectrum, maybe you learn something about the broader process.

All of the above talks about visualizing a converged, already trained neural network. What about watching the training stages? A giant picture of all the neurons and their weights shifting? Or some picture of the topology of the process and how it changes as we train? Interactivity is probably a key element of this picture, maybe a slider to go along the spectrum between a 5 and a 6. But maybe a slider is the wrong input mechanism -- there's several ways to get from 5 to 6, so maybe we need some kind of image editor (imagine a picture of a face, and letting them drag eyes around or distort a nose).

There's a difference between visualizing the classification of an input, and visualizing the training process -- which is more useful?

Are there radically different examples, some sort of density distribution that changes as the network is trained? A lot of the above doesn't deviate from the standard textbook circles-and-lines picture. Can we draw a heat map, a bunch of lines changing thickness, or a set of time series of weights? The latter would answer how the distribution of weights has changed during training (e.g. this layer converged quickly, this one took forever). A force-directed layout type thing could also convey the same information and would be fun to watch!

There are certain patterns over training time and/or over the execution of a classification, and we could look for a way of representing this in terms of activity levels, input levels, or probabilities. If we want to get away from the network picture of individual neurons, can we find semi-autonomous groups of neurons and see how they interact (instead of single neurons)?

Or what if colors apply to data instead of neurons: you pour in blue data at the top of the neurons, then pour in red data, and you can look for spots of purple or spots that stay blue to try to find things that pick out differences between the two. There are number OCR examples where there's a monochrome picture of the parts of an image being differentiated, such as just the top and bottom lines to distinguish between 7 and 2. In comparing those pictures, maybe the key is to highlight or color-code the bits that the network is making its decisions on. This helps highlight the things that the neural network is finding "magically".

This last concept in more general terms -- take the input data and find some transformation into another domain that represents the features that have been found.

Examples mentioned:

* [ConvNetJS](http://cs.stanford.edu/people/karpathy/convnetjs/)
* [BigML](https://bigml.com/gallery/models)