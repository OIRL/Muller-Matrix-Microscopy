## Determination of the Mueller matrix from intensity-based images recorded by a bright-field microscope

The hallmark of polarization-sensitive microscopy is the estimation of polarimetric information of samples, making them a suitable tool for detecting and diagnosis different type of cells and tissues in life sciences. In this work, we describe a practical procedure for measuring the Mueller matrix of samples using a bright-field microscope using  36 intensity-based images. The hallmark of the proposed method is the retrieval of the Mueller matrix across the transverse section of a sample, being suitable for analyzing biological samples. The method has been implemented in Python and MATLAB.

### Mueller matrix and retrieval of polarization properties
Polarization-sensitive microscopy is a technique that allows obtaining the polarization properties of biological and material samples. Over the last decade, polarization-sensitive microscopy has been widely used in biological studies since it enables detecting states and diseases in biological samples analyzing their polarimetric properties. Polarization-based techniques are commonly based on estimating the Jones or Mueller matrices. Whereas the estimation of the Jones matrix requires an optical interferometer, the Mueller matrix can be estimated directly from intensity-based images, resulting in a more simple optical configuration. Another advantage of Mueller formalism is its applicability to polarized and depolarized light. Therefore, using Mueller formalism, one can recover the birefringence, diattenuation, and depolarization in a single measurement. Since these three parameters represent the polarization properties of a biological sample completely, the Mueller approach results in a powerful tool for biological samples.

### Method to estimate the Mueller matrix
Here, we propose a computation method to estimate the Mueller matrix for a complex sample whose polarimetric properties vary across its transverse field of view. The method requires 36 images that are recorded by changing the polarization state of both the polarization state generator (PSG) and polarization state analyzer (PSA) systems. Based on these polarization states of PSG and PSA systems, the Mueller matrix, M¸ is


where each element of the Mueller matrix is estimated by adding and/or subtracting 4 of the 36 images 


In Eq. (2), the first letter represents the polarization state of the PSG system, and the second one corresponds to the polarization state of the PSA system. For example, based on this notation, in the HV image, the polarization state of the PSG and PSA systems is horizontal and vertical, respectively. Once the Mueller matrix is calculated, we can estimate the values of the diattenuation (D), polarizance (P), depolarization (Δ), and the angle of polarization (θ) via


The polarization angle θ is only relevant if the optical element is a linear polarizer.

### Experimental Results
We have reconstructed the polarimetric information of a linear polarizer (LPVISE100-A, Thorlabs) oriented at two angles: 90 degrees and +45 degrees. The linear polarizer in the experimental bright-field microscope is illuminated by a beam of light emerging of a collimated laser-diode-pumped DPSS laser (CPS532, Thorlabs source). The microscope is composed of an infinity-corrected MO with a lateral magnification of 40× and numerical aperture of NA = 0.75 and an tube lens of 200-mm focal length. A Basler acA5472-17um CMOS sensor (5472×3648 pixels, 2.4-µm square pixel size) is placed at the microscope's image plane, allowing the acquisition of the intensity-based images. 

To provide polarization-sensitive measurements, we insert the PSG and PSA systems in the microscope. The elliptical polarization state of the illumination source was changed to randomly polarized using a quartz depolarizer (DPU-25-A, Thorlabs). Thus, the polarizing elements of the PSG and PSA systems are two linear polarizers (LPVISE100-A, Thorlabs) and two achromatic quarter wave-plates (AQWP10M-580, Thorlabs), see Fig. 1. 

![Experiemntal Setup](https://raw.githubusercontent.com/OIRL/Muller-Matrix-Microscopy/gh-pages/Optical_system_Repository.png "Experimental Setup")

From the recorded 36 intensity-based images, we have estimated their corresponding Mueller matrices. Comparison between the theoretical and experimental values for the Mueller matrix of  the LP at the two angular position is shown in Fig. 2. For both orientation angles, we have estimated the mean and the standard deviation value of each element of the Mueller matrix (values also reported in Fig. 2). 

![Matrix at 90 deg theoretical and experiemntal](https://raw.githubusercontent.com/OIRL/Muller-Matrix-Microscopy/gh-pages/Matrix_90_Theo_and_Exp.png "Matrix at 90 deg theoretical and experiemntal")


![Matrix at 45 deg theoretical and experiemntal](https://raw.githubusercontent.com/OIRL/Muller-Matrix-Microscopy/gh-pages/Matrix_45_Theo_and_Exp.png "Matrix at 45 deg theoretical and experiemntal")


The agreement between the experimental and theoretical Mueller matrices is high. Table 1 compares the experimental and theoretical polarimetric parameters (diattenuation, polarization, depolarization, and angle of polarization) of the linear polarizer for both orientation angles. Again, the degree of correlation between theoretical and experimental results is very high.

### Script 
The computational method to estimate the Mueller matrix from 36 intensity-based images is implemented in Python and MATLAB. 

### Samples
We have available the 36 intensity-based experimental images of:
-A linear polarizer oriented at 90 degrees (add a link to download the images)
-A linear polarizer oriented at 45 degrees (add a link to download the images)

### Funding
This project has received funding from the University of Memphis (Memphis, TN, United States) and EAFIT University (Medellin, Antioquia, Colombia)

### Citation
If using this information for publication, please kindly cite the following paper:
S. Obando-Vasquez, A. Doblas, and C. Trujillo, “Apparatus and method to estimate the Mueller matrix in bright-field microscopy,” Applied Optics, under review (2021).

### Support or Contact 

| Researcher  | email | Google Scholar | 
| ------------- | ------------- |-------------| 
| Sofia Obando-Vasquez | *sobandov@eafit.edu.co* | |
| Ana Doblas| *adoblas@memphis.edu* | [AnaGoogle](https://scholar.google.es/citations?user=PvvDEMYAAAAJ&hl=en) |
| Carlos Trujillo| *catrujilla@eafit.edu.co* | [TrujilloGoogle](https://scholar.google.com/citations?user=BKVrl2gAAAAJ&hl=es) | 
