# Detection-and-Classification-of-Nannofossil-Genera-in-Microscopic-Nannofossil-Images

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
