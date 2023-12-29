# Document-Interaction-Assistant
   
<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
       <li>
      <a href="#salient-features">Salient Features</a></li>
      <li>
      <a href="#description">Description</a>
      <li>
      <a href="#data-preprocessing">Data Preprocessing</a></li>
      <li>
      <a href="#Document Classification Model">Document Classification Model</a></li>
      <li>
      <a href="#results">Results</a>
      <li>
      <a href="#Information extraction model">Information extraction model</a>
      <li>
      <a href="#team">Team</a>
    </li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About the project
We put out a model that can recognize the collection of papers contained in a PDF or image made up of numerous documents. To accomplish this, the input PDF is divided into individual pages. The CNN model is used to categorize each page into the appropriate document category. After that, each document's data is extracted using OCR (optical character recognition). This is being recommended for five documents: voter identification, driver's license, PAN, and Aadhar. Except for the front and back of the same document, the input PDF must include a single document on a single page.
Initially, our data classification model achieved an accuracy of 0.7342 on the training set and 0.7736 on the validation set, with gains of 0.6923 and losses of 0.8340.

In our ongoing efforts to enhance performance, we explored and discovered VGG16 and VGG19 models. Hyperparameter tuning was applied to our model, incorporating additional layers to the pre-trained models. As a result, we achieved a validation loss of 0.3677 and a validation accuracy of 0.8769 for VGG16.

In addition to this, we incorporated two more features:

#### 1. Read Aloud:
* Utilizes text-to-speech technology for accessibility.
* Translates text into spoken words.
* Supports auditory learners and those with visual impairments.
* Enhances accessibility and consumability.

#### 2. Document Summarization:
* Aids time-constrained users by condensing lengthy papers.
* Uses Hugging Face Transformers library for NLP models.
* Provides clear and instructive document synopses.
* Maximizes time efficiency by distilling crucial insights.

### Salient Features
Hyperparameter tuning, regularization(early stopping,dropout), document split 

### Tech stack used
* models: CNN, VGG16, VGG19 and OCR engine tesseract
* Google TTS(Text to speech), Hugging Face Transformers for text summarization 
* Framework-Keras 

### User Flow
<img width="500" alt="image" src="https://github.com/kanikakj/Document-Interaction-Assistant/assets/77913500/f3f60978-d4b4-4f11-9862-90b1482de9cb">

### Data Description 
When we began searching for an appropriate dataset, we observed that there is no publicly available dataset of identity documents as they hold sensitive and personal information. But we came across a dataset on Kaggle that consisted of six folders, i.e., Aadhar Card, PAN Card, Voter ID, single-page Gas Bill, Passport, and Driver's License.  We added a few more images to each folder. These were our own documents that we manually scanned, with the rest coming from Google Images.
Thus, these are the five documents we are classifying and extracting information from.
<img width="310" alt="image" src="https://github.com/PrincySinghal/Document-Interaction-Assistant/assets/87893594/3abe0bc7-9178-484d-804d-81b3bf6387b3">




### Data Preprocessing
Originally, we implemented horizontal and vertical data augmentation through random flips to enhance dataset size and diversity. Currently, we have transitioned to utilizing image data generators for both the train and test sets.


### Document Classification Model
## CNN model
<img width="555" alt="image" src="https://user-images.githubusercontent.com/87893594/224973161-2513f1f7-0291-41ed-9b79-c14ef2578882.png">

Various hyperparameters like the number of layers, neurons in each layer, number of filters, kernel size, the value of p in dropout layers, number of epochs, batch size, etc. were changed until satisfactory training and validation accuracy was achieved.

<img width="500" alt="image" src="https://user-images.githubusercontent.com/87893594/224972235-be7435d0-1f11-4c38-8ab6-6958fcb3bb83.png">

<img width="500" alt="image" src="https://user-images.githubusercontent.com/87893594/224972374-4244b1b6-418d-4364-8fea-77a05450ca19.png">


### CNN Model results
<img width="500" alt="image" src="https://user-images.githubusercontent.com/87893594/224972133-8bf9642b-d16e-4880-b017-161c61d8f247.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/87893594/224972187-cd7f5c48-95d7-42fa-a187-bfd84344e903.png">

## VGG16
The VGG model's architecture uses small convolution filters and deep structure that allows it to capture fine details, which is crucial for distinguishing between various ID documents that often have subtle differences. 
<img width="555" alt="image" src="https://github.com/kanikakj/Document-Interaction-Assistant/assets/77913500/fbddf1d3-b20a-487e-b570-015f92cdbe7f">

4 additional layers were incorporated into the pre-trained model.

<img width="500" alt="image" src="https://github.com/kanikakj/Document-Interaction-Assistant/assets/77913500/b02cc9d3-4b49-4063-b0f5-d1087ef19ff4">

Before landing unto our final chosen model shown above, we tweaked the pre-trained architecture until satifactory results were acheived.
![Comparative results of identity document classification models]<img width="417" alt="image" src="https://github.com/PrincySinghal/Document-Interaction-Assistant/assets/87893594/87a4d649-db0c-43a8-b4f2-e6d78b59aad6">


### Information extraction model
Following are the steps of OCR done on images:

<img width="650" alt="image" src="https://user-images.githubusercontent.com/87893594/224973268-06a235f9-6657-4970-befc-78cf665bfb65.png">

<img width="650" alt="image" src="https://user-images.githubusercontent.com/87893594/224973311-0b5c26d3-46d4-4df8-96a3-c4287072637a.png">

### Ongoing Improvements:
1. Interactive Summarization and Query Answering
2. Advanced Handwritten Text Extraction
3. Global Accessibility with Multilingual Support
4. Wider document classfication systems covering legal documents 
5. Exploring advanced CNN architectures

### Team
- Kanika Kanojia [GitHub](https://github.com)        [Linkedin](https://www.linkedin.com/in/kanika-kanojia-348620207/) 
- Princy Singhal [GitHub](https://github.com/PrincySinghal) [Linkedin](https://www.linkedin.com/in/princy-singhal-047414224/)
