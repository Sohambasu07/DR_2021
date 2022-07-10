<h1> Segmentation of Blood Vessels, Optic Disc Localization, Detection of Exudates and Diabetic Retinopathy Diagnosis from Digital Fundus Images </h1>

[Soham Basu](https://scholar.google.com/citations?user=VFrBx88AAAAJ&hl=en), [Sayantan Mukherjee](https://orcid.org/0000-0001-9385-7369), [Ankit Bhattacharya](https://orcid.org/0000-0003-1434-7892), [Anindya Sen](https://scholar.google.com/citations?user=vA6hgasAAAAJ&hl=en)

[![paper](https://img.shields.io/badge/Springer-Full_Paper-blue)](https://doi.org/10.1007/978-981-16-1543-6_16) 
[![dataset](https://img.shields.io/badge/DRIVE-Dataset-red)](https://drive.grand-challenge.org/)
[![dataset](https://img.shields.io/badge/IDRiD-Dataset-rgb(255,20,212))](http://dx.doi.org/10.21227/H25W98)
[![slides](https://img.shields.io/badge/Presentation-Slides-yellow)](https://drive.google.com/file/d/1xo0QhifZ2juq-dHoke1nMhcgLlhQJKsj/view?usp=sharing)





> **Abstract:** *Diabetic Retinopathy (DR) is a complication of long-standing, unchecked diabetes and one of the leading causes of blindness in the world. This paper focuses on improved and robust methods to extract some of the features of DR, viz. Blood Vessels and Exudates. Blood vessels are segmented using multiple morphological and thresholding operations. For the segmentation of exudates, k-means clustering and contour detection on the original images are used. Extensive noise reduction is performed to remove false positives from the vessel segmentation algorithm's results. The localization of Optic Disc using k-means clustering and template matching is also performed. Lastly, this paper presents a Deep Convolutional Neural Network (DCNN) model with 14 Convolutional Layers and 2 Fully Connected Layers, for the automatic, binary diagnosis of DR. The vessel segmentation, optic disc localization and DCNN achieve accuracies of 95.93%, 98.77% and 75.73% respectively.*


<h2>Proposed Methods</h2>
<hr />

<!--
  ======================BLOOD VESSEL SEGMENTATION===========================
                          -->

<h3>1. Blood Vessel Segmentation</h3>

<figure>
<table>
  <tr >
    <td width=25% style="text-align:center;"><img src = "./figures/Figure_2a.png">(a) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_2b.png">(b) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_2c.png">(c) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_2d.png">(d) </td>
  </tr>
  <tr>  
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_2e.png">(e) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_2f.png">(f) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_2g.png">(g) </td>
  </tr>
</table>
<figcaption style="text-align:center;">(a) Original Image, (b) Green channel component of (a), (c) CLAHE applied image, (d) Background estimated after Alternate Sequential Filtering, (e) Image (d) subtracted from (c) and CLAHE applied again, (f) Median blur and thresholding, (g) Final segmentation output.</figcaption>
</figure>

<br><br>

<figure>
<img  style="background-color:rgba(255,255,255,0.2);" src = "./figures/Figure_3.png">
<figcaption style="text-align:center;">Blood vessel segmentation algorithm </figcaption>
</figure>

<br>

<!--
  =========================OPTIC DISC LOCALIZATION========================= 
                          -->
 

<h3>2. Optic Disc Localization</h3>

<figure>
<table>
  <tr >
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_4a.png">(a) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_4b.png">(b) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_4c.png">(c) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_4d.png"><br>(d) </td>
  </tr>
  <tr>  
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_4e.png">(e) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_4f.png">(f) </td>
    <td width=25% style="text-align:center;"> <img src = "./figures/Figure_4g.png">(g) </td>
  </tr>
</table>
<figcaption style="text-align:center;">(a) Original image, (b) Grayscale of (a), (c) Result of k-means clustering, (d) Generated Template, (e) Template Matching result (using NCCOEFF; notice the OD region has highest similarity), (f) Marking OD and its center, (g) Masking OD region. </figcaption>
</figure>

<br><br>

<figure>
<img  style="background-color:rgba(255,255,255,0.2);" src = "./figures/Figure_5.png">
<figcaption style="text-align:center;">Optic Disc Localization algorithm </figcaption>
</figure>

<br>


<!--
  ============================DETECTION OF EXUDATES=========================
                          -->

<h3>3. Detection of Exudates</h3>

<figure>
<table>
  <tr >
    <td width=20% style="text-align:center;"> <img src = "./figures/Figure_6a.png">(a) </td>
    <td width=20% style="text-align:center;"> <img src = "./figures/Figure_6b.png">(b) </td>
    <td width=20% style="text-align:center;"> <img src = "./figures/Figure_6c.png">(c) </td>
    <td width=20% style="text-align:center;"> <img src = "./figures/Figure_6d.png">(d) </td>
    <td width=20% style="text-align:center;"> <img src = "./figures/Figure_6e.png">(e) </td>
  </tr>
</table>
<figcaption style="text-align:center;">(a) Original Image, (b) K-means clustering result, (c) Extracting the exudates from (b) and thresholding, (d) Logical OR of (c) and the images containing the smallest exudates, (e) Final segmentation result after OD masking. </figcaption>
</figure>

<br><br>

<figure>
<img  style="background-color:rgba(255,255,255,0.2);" src = "./figures/Figure_7.png">
<figcaption style="text-align:center;">Exudates Detection algorithm </figcaption>
</figure>

<br>


<!--
  =================================DEEP CNN=================================
                          -->

<h3>4. Binary Diagnosis of Diabetic Retinopathy using a Deep Convolutional Neural Network</h3>

<figure>
<img  style="background-color:rgba(255,255,255,0.2);" src = "./figures/Figure_8.png">
<figcaption style="text-align:center;">Proposed Neural Network architecture with the corresponding kernel/Filter sizes (k), number of feature maps (n) and strides (s) specified for each convolutional layer.</figcaption>
</figure>



<!--
  ====================================RESULTS===============================
                          -->

<h2>Results </h2>
<hr />
<h3>1. Blood Vessel Segmentation</h3>

The DRIVE dataset was used for the evaluation of the proposed method.

<figure>
<img src = "./figures/Figure_9.png">
<figcaption style="text-align:center">The segmentation result for the best case (left) with ground truth (right)</figcaption>
</figure>
<br>

<figure>
<img src = "./figures/Table1.png">
<figcaption style="text-align:center"></figcaption>
</figure>

<figure>
<img src = "./figures/Table2.png">
<figcaption style="text-align:center"></figcaption>
</figure>
<br><br>


<h3>2. Optic Disc Localization</h3>

The proposed method had an accuracy of 98.77% on the IDRiD Segmentation Dataset.

<figure>
<img src = "./figures/Figure_10.png">
<figcaption style="text-align:center">Optic Disc masked image (left) with the original image (right)</figcaption>
</figure>
<br><br>

<h3>3. Detection of Exudates</h3>

We used the IDRiD Segmentation Dataset for testing our proposed exudates detection algorithm.

<figure>
<table>
  <tr>
    <td style="text-align:center;"> <img src = "./figures/Figure_11a.png">(a) </td>
    <td style="text-align:center;"> <img src = "./figures/Figure_11b.png">(b) </td>
  </tr>
</table>
<figcaption style="text-align:center">(a), (b) Result of proposed exudates detection method (left) with original
image (right).</figcaption>
</figure>
<br><br>

<h3>4. Binary Diagnosis of DR using Deep CNN</h3>

The IDRiD Disease Grading dataset was used to train and evaluate the proposed network. It had an accuracy of 75.73% on a test set comprising 25% of the entire dataset.

<figure>
<img src = "./figures/Figure_12.png">
<figcaption style="text-align:center">DCNN training results with Training Accuracy, Test Accuracy and Training Loss</figcaption>
</figure>
<br><br>


<h2>Cite our work</h2>
<hr />
    
    Basu, S., Mukherjee, S., Bhattacharya, A., Sen, A. (2021). Segmentation of Blood Vessels, Optic Disc Localization, Detection of Exudates, and Diabetic Retinopathy Diagnosis from Digital Fundus Images. In: Pan, I., Mukherjee, A., Piuri, V. (eds) Proceedings of Research and Applications in Artificial Intelligence. Advances in Intelligent Systems and Computing, vol 1355. Springer, Singapore. https://doi.org/10.1007/978-981-16-1543-6_16


<h2>Contact</h2><hr />
For any queries, please contact: <a href="mailto:soham.basu07@gmail.com">soham.basu07@gmail.com</a>