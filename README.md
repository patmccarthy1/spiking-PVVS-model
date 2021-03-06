# Spiking Neural Network Model of the Primate Ventral Visual System

Biologically realistic model of a network of neurons in the primate ventral visual pathway. This was developed to investigate the emergence of feature selectivity for forming representations of shape, and to test a newly proposed solution to feature binding: hierarchical binding by polychronization <sup>[1,2]</sup>.

## Model Features and Architecture

Images are processed by a Gabor filter set, and pixel values of the filtered images determine the mean firing rate of Poisson neurons, acting as an input layer. The rest of the model consists of 4 layers of conductance-based LIF neurons, containing excitatory and inhibitory neurons in a 4:1 ratio. Neurons are connected in a topologically corresponding manner to facilitate the development of retinotopic maps. Neurons are connected with feedforward, feedback, recurrent and lateral (inhibitory) conductance-based synapses. Conduction delays between neurons are Gaussian distributed, and an STDP learning rule is implemented in synapses between excitatory LIF neurons, encouraging the emergence of polychronous neuronal groups. 

The model architecture is illustrated below.

![diagram of model architecture](https://github.com/patmccarthy1/spiking-PVVS-model/blob/master/misc/architecture.png)

## Requirements

* Python v3.7.7
* MATLAB R2021a
* Brian 2 v2.3.0.2
* NumPy v1.19.1
* SciPy v1.6.2
* OpenCV v3.4.2
* Matplotlib v3.3.1

## Model Use

After installing the dependencies mentioned above, clone this Git repository to your local drive. The most important files and folders are:

* [model.py](https://github.com/patmccarthy1/spiking-PVVS-model/blob/master/model.py) - defines model architecture and includes functions present images to model
* [simulation.ipynb](https://github.com/patmccarthy1/spiking-PVVS-model/blob/master/simulation.py) - used to run simulations and plot live results
* [analysis](https://github.com/patmccarthy1/spiking-PVVS-model/blob/master/analysis) - contains a range of MATLAB scripts to perform data analysis and create plots

Upon opening the Jupyter Notebook file [simulation.ipynb](https://github.com/patmccarthy1/spiking-PVVS-model/blob/master/simulation.py), you will be able to run cells to import the model class 'SpikingVisNet' from [model.py](https://github.com/patmccarthy1/spiking-PVVS-model/blob/master/model.py), create a new model, 
import image data to present from [input_data](https://github.com/patmccarthy1/spiking-PVVS-model/blob/master/input_data) and run simulations. The Jupyter Notebook environment is used so that results can be plotted in real-time, and the model can be used by somebody with minimal coding ability. Access to a high number of CPU cores and ideally GPU boosting will be required.

## Development
Developed by Patrick McCarthy at Imperial College London, 2021 under the supervision of Simon Schultz<sup>a</sup>, Simon Stringer<sup>b</sup> and Dan Goodman<sup>c</sup>.

<sup>a</sup> <sub>Neural Coding Lab, Imperial College London</sub>\
<sup>b</sup> <sub>Centre for Theoretical Neuroscience and Artificial Intelligence, University of Oxford</sub>\
<sup>c</sup> <sub>Neural Reckoning Lab, Imperial College London</sub>
## References

[1] [https://www.oftnai.org/articles/Brain_modelling_articles/Publications/Vision/2018-25960-001.pdf](https://www.oftnai.org/articles/Brain_modelling_articles/Publications/Vision/2018-25960-001.pdf)\
[2] [https://www.mitpressjournals.org/doi/pdfplus/10.1162/089976606775093882](https://www.mitpressjournals.org/doi/pdfplus/10.1162/089976606775093882)\
[3] [https://brian2.readthedocs.io/en/stable/index.html](https://brian2.readthedocs.io/en/stable/index.html)
