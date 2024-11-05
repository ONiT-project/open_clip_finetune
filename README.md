# OpenCLIP Fine-Tuning
The code published in this repository follows the [WiSE-FT](https://github.com/mlfoundations/wise-ft) method for finetuning an [OpenCLIP](https://github.com/mlfoundations/open_clip) model. This work was funded as part of the Austrian Science Fund project Ottoman Nature in Travelogues [(ONiT) project](https://onit.oeaw.ac.at/).

The latest version of the notebook implements contrastive learning fine-tuning of an OpenCLIP model ('ViT-B-32' pretrained on the LAION 400m dataset) with a sub-set of the [ICONCLASS AI Test Set](https://iconclass.org/testset/) adapted for this task.
- The training dataset was extracted in context of our conference paper published at the Digital History Tagung 2023, Berlin (vignoli_impact_2023). The subset used for this fine-tuning contains caption-image pairs of the ICONCLASS AI Test Set images featuring nature representations (i.e., flora, fauna, landscapes, and maps).
- The fine-tuned model is used for image similarity and natural language prompt search of nature representations in the image corpus extracted from the printed travelogues. For this, the features of the ONiT image dataset, which were previously extracted from a corpus of ~1500 travelogues on the Ottoman empire printed between 1501 and 1850 ([ONiT Image Extraction](https://github.com/ONiT-project/onit-image-extraction)), are encoded with the fine-tuned model and subsequently searched for similar features. First, the cosine similarity between the encoded image features is computed between a reference image and all other images in the dataset. Second, the cosine similarity between an encoded prompt and all image features in the dataset is computed.

Code in this notebook was adapted from [Interacting with openCLIP](https://github.com/mlfoundations/open_clip/blob/main/docs/Interacting_with_open_clip.ipynb) with elements adapted from code generated with ChatGPT (free version). Code for the training was adapted from vinson2233 ([CLIP Training Code #83](https://github.com/openai/CLIP/issues/83)) and Silvia Poletti (AIT Austrian Institute of Technology).

# Keywords
Digital Humanities, Artificial Intelligence, Computer Vision, Book History, Image Classification, Early Modern Prints, Multi-Modal Contrastive Learning

# References
This work complements our experiments done with a CLIP zero-shot model and the ICONCLASS AI Test Set, which were published in a conference paper at the Digital History Tagung 2023 in Berlin, DE:

```
@article{vignoli_impact_2023,
	title = {Impact of {AI}: {Gamechanger} for {Image} {Classification} in {Historical} {Research}?},
	copyright = {Creative Commons Attribution 4.0 International, Open Access},
	shorttitle = {Impact of {AI}},
	url = {https://zenodo.org/record/8322398},
	doi = {10.5281/ZENODO.8322398},
	abstract = {Ein Beitrag zur Digital History 2023: Digitale Methoden in der geschichtswissenschaftlichen Praxis: Fachliche Transformationen und ihre epistemologischen Konsequenzen, Berlin, 23.-26.5.2023. {\textless}strong{\textgreater}Abstract: {\textless}/strong{\textgreater}AI opens new possibilities for processing and analysing large, heterogeneous historical data corpora in a semi-automated way. The Ottoman Nature in Travelogues (ONiT) project develops an interdisciplinary methodological framework for an AI-driven analysis of text–image relations in digitised printed material. In this paper, we discuss our results from the first project year, in which we explore the potential of multi-modal deep learning approaches for combined analysis of text and image similarity of “nature” representations in historical prints. Our experiments with OpenCLIP for zero-shot classification of prints from the ICONCLASS AI Test Set show the potential but also limitations of using pre-trained contrastive-learning algorithms for historical contents. Based on the results and our learnings, we discuss in which way computational, quantitative methods affect our underlying epistemology stemming from more traditional “analogue” methods. Our experiences confirm that interdisciplinary collaboration between historians and AI developers is important to adapt disciplinary conventions and heuristics for use in applied AI methods. Our main learnings are the necessity to differentiate between distinct visual features in historical images versus representations of “nature” that require interpretation, and to develop an understanding for the features an AI algorithm can be retrained to detect.},
	language = {de},
	urldate = {2023-10-13},
	author = {Vignoli, Michela and Gruber, Doris and Simon, Rainer and Weißenfeld, Axel},
	month = oct,
	year = {2023},
	keywords = {artificial intelligence, book history, computer vision, early modern prints, image classification},
}

```
