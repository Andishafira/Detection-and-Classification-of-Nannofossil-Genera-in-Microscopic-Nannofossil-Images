# Detection-and-Classification-of-Nannofossil-Genera-in-Microscopic-Nannofossil-Images

## Abstract
In paleoclimatology, nannofossils can serve as important indicators for reconstructing and analyzing past climate change. Traditionally, such analyses are conducted by manually counting nannofossil abundance from microscopic images—a process that requires skilled experts and is highly time-consuming. Therefore, there is a need to develop an automated system capable of detecting, classifying, and counting nannofossil objects in microscopic images. Object detection-based approaches offer a promising solution; however, their implementation faces several challenges. These include the inherently small size of objects in the images and imbalanced class distributions in the dataset. If left unaddressed, these issues can result in an unreliable detection model.

To address these challenges, this study proposes an automated system for nannofossil detection, classification, and quantification from microscopic images. Several strategies were employed to optimize model performance. First, a primary dataset was collected from polarized light microscope images provided by the Paleontology Laboratory, Department of Geological Engineering, Faculty of Engineering, Universitas Gadjah Mada (UGM). The use of primary data ensures that the resulting model is tailored to paleontological research needs and reflects real-world conditions. Second, a contrast enhancement technique was applied to improve image quality. Additionally, class distribution in the training dataset was balanced to mitigate bias. Following preprocessing, the dataset was trained using the You Only Look Once (YOLO) object detection model with various configurations, including hyperparameter optimization for learning rate and image size.

Experimental results indicate that the YOLOv11 X model achieved the highest performance in detecting and classifying nannofossil genera. The proposed contrast enhancement technique improved both precision and recall compared to alternative methods. Testing further demonstrated that the combination of dataset balancing, image quality enhancement, and hyperparameter optimization led to notable improvements across evaluation metrics, with recall, precision, mAP-50, and mAP50–90 reaching 0.919, 0.667, 0.733, and 0.593, respectively. This approach demonstrates that AI-based nannofossil detection can overcome existing challenges in paleoclimatological analysis, enabling faster and more efficient workflows. Its implementation is expected to support paleotemperature studies through precise, automated, and data-driven analysis, thereby contributing significantly to paleoclimatology research


## Dataset
The dataset used in this study consists of microscopic images of nanofossils obtained from the Paleontology Laboratory, Department of Geological Engineering, Universitas Gadjah Mada. The dataset was collected through observations made using a polarizing microscope on finely ground limestone samples.
The dataset consists of four classes: 
  - `Coccolith PPL`
  - `Coccolith XPL`
  - `Discoaster PPL`
  - `Discoaster XPL`

This is because the observed nanofossils belong to two genera: Discoaster and Coccolith, while the types of microscope polarization lighting used are Plane Polarized Light (PPL) and Cross Polarized Light (XPL).

## Dataset Preview

### Discoaster object preview

![Discoaster](https://github.com/Andishafira/Detection-and-Classification-of-Nannofossil-Genera-in-Microscopic-Nannofossil-Images/blob/main/discoaster.jpg) 

### Coccolith object preview
!["Coccolith"](https://github.com/Andishafira/Detection-and-Classification-of-Nannofossil-Genera-in-Microscopic-Nannofossil-Images/blob/main/coccolith.jpg)

### PPL image preview
![PPL](https://github.com/Andishafira/Detection-and-Classification-of-Nannofossil-Genera-in-Microscopic-Nannofossil-Images/blob/main/ppl%20sample%20image.jpg) 

### XPL image preview
!["XPL"](https://github.com/Andishafira/Detection-and-Classification-of-Nannofossil-Genera-in-Microscopic-Nannofossil-Images/blob/main/xpl%20sample%20image.jpg)

## Project Flow
1. Collect the dataset
2. Dataset preparation (balancing data and image enhancement)
3. Training data with YOLO 11 with many scenarios
4. Model testing
5. Added an algorithm to calculate the occurrence of objects
6. Report the result
7. Developing methods (still underway)

## File Description
1. preprocessing_dataset_withEsrgan.ipynb : This file contains the image data preprocessing process. The preprocessing performed in this file is resolution enhancement with ESRGAN and contrast enhancement with a modified mean and standard deviation method.
2. training_yolo11_size.ipynb : This file contains the training process with various YOLO model sizes. The model sizes used are M, L, and X. This is intended to find the model size that provides the maximum model performance. it can be concluded that size X gets the most optimal results.
3. training_dataset_variation.ipynb : This file contains the dataset training process with various dataset scenarios. These scenarios include training using the original dataset, the dataset before it was enhanced, and the dataset that has been balanced and enhanced.
4. training_enhance_hyperparam_yolo8x_yolo11x.ipynb : This file contains the training process by comparing the YOLO v8 model with YOLOv11.
5. testing.ipynb : This file contains the testing process for each model.
6. demo.ipynb : This file contains a demo process using new data. This file has been added with an algorithm to calculate the occurrence of nanofossil genus objects.
7. improved_yolo11.yaml : This file represents the YOLO 11 model structure that has been modified by adding a new head layer. This layer was added to allow the model to more reliably detect small objects.
