## Determination of the Mueller matrix from intensity-based images recorded by a bright-field microscope

The hallmark of polarization-sensitive microscopy is the estimation of polarimetric information of samples, making them a suitable tool for detecting and diagnosis different type of cells and tissues in life sciences. In this work, we describe a practical procedure for measuring the Mueller matrix of samples using a bright-field microscope using  36 intensity-based images. The hallmark of the proposed method is the retrieval of the Mueller matrix across the transverse section of a sample, being suitable for analyzing biological samples. The method has been implemented in Python and MATLAB.

### Mueller matrix and retrieval of polarization properties
Polarization-sensitive microscopy is a technique that allows obtaining the polarization properties of biological and material samples. Over the last decade, polarization-sensitive microscopy has been widely used in biological studies since it enables detecting states and diseases in biological samples analyzing their polarimetric properties. Polarization-based techniques are commonly based on estimating the Jones or Mueller matrices. Whereas the estimation of the Jones matrix requires an optical interferometer, the Mueller matrix can be estimated directly from intensity-based images, resulting in a more simple optical configuration. Another advantage of Mueller formalism is its applicability to polarized and depolarized light. Therefore, using Mueller formalism, one can recover the birefringence, diattenuation, and depolarization in a single measurement. Since these three parameters represent the polarization properties of a biological sample completely, the Mueller approach results in a powerful tool for biological samples.

### Method to estimate the Mueller matrix
Here, we propose a computation method to estimate the Mueller matrix for a complex sample whose polarimetric properties vary across its transverse field of view. The method requires 36 images that are recorded by changing the polarization state of both the polarization state generator (PSG) and polarization state analyzer (PSA) systems. Based on these polarization states of PSG and PSA systems, the Mueller matrix, M¸ is

<img src="https://latex.codecogs.com/gif.latex?M=\begin{bmatrix}m_{00}&m_{01}&m_{02}&m_{03}\\m_{10}&m_{11}&m_{12}&m_{13}\\m_{20}&m_{21}&m_{22}&m_{23}\\m_{30}&m_{31}&m_{32}&m_{33}&space;\end{bmatrix}" title="M=\begin{bmatrix}m_{00}&m_{01}&m_{02}&m_{03}\\m_{10}&m_{11}&m_{12}&m_{13}\\m_{20}&m_{21}&m_{22}&m_{23}\\m_{30}&m_{31}&m_{32}&m_{33} \end{bmatrix}" />

where each element of the Mueller matrix is estimated by adding and/or subtracting 4 of the 36 images 

<img src="https://latex.codecogs.com/gif.latex?\begin{matrix}m_{00}=HH{&plus;}HV{&plus;}VH{&plus;}VV&m_{01}=HH{&plus;}HV{-}VH{-}VV\\m_{02}=PH{&plus;}PV{-}MH{-}MV&m_{03}=RH{&plus;}RV{-}LH{-}LV\\m_{10}=HH{-}HV{&plus;}VH{-}VV&m_{11}=HH{-}HV{-}VH{&plus;}VV\\m_{12}=PH{-}PV{-}MH{&plus;}MV&m_{13}=RH{-}RV{-}LH{&plus;}LV\\m_{20}=HP{-}HM{&plus;}VP{-}VM&m_{21}=HP{-}HM{-}VP{&plus;}VM\\m_{22}=PP{-}PM{-}MP{&plus;}MM&m_{23}=RP{-}RM{-}LP{&plus;}LM\\m_{30}=HR{-}HL{&plus;}VR{-}VL&m_{31}=HR{-}HL{-}VR{&plus;}VL\\m_{32}=PR{-}PL{-}MR{&plus;}ML&m_{33}=LL{-}RL{-}LR{&plus;}RR\\\end{matrix}" title="\begin{matrix}m_{00}=HH{+}HV{+}VH{+}VV&m_{01}=HH{+}HV{-}VH{-}VV\\m_{02}=PH{+}PV{-}MH{-}MV&m_{03}=RH{+}RV{-}LH{-}LV\\m_{10}=HH{-}HV{+}VH{-}VV&m_{11}=HH{-}HV{-}VH{+}VV\\m_{12}=PH{-}PV{-}MH{+}MV&m_{13}=RH{-}RV{-}LH{+}LV\\m_{20}=HP{-}HM{+}VP{-}VM&m_{21}=HP{-}HM{-}VP{+}VM\\m_{22}=PP{-}PM{-}MP{+}MM&m_{23}=RP{-}RM{-}LP{+}LM\\m_{30}=HR{-}HL{+}VR{-}VL&m_{31}=HR{-}HL{-}VR{+}VL\\m_{32}=PR{-}PL{-}MR{+}ML&m_{33}=LL{-}RL{-}LR{+}RR\\\end{matrix}" />

In Eq. (2), the first letter represents the polarization state of the PSG system, and the second one corresponds to the polarization state of the PSA system. For example, based on this notation, in the HV image, the polarization state of the PSG and PSA systems is horizontal and vertical, respectively. Once the Mueller matrix is calculated, we can estimate the values of the diattenuation (D), polarizance (P), depolarization (Δ), and the angle of polarization (θ) via the following equations

<img src="https://latex.codecogs.com/gif.latex?D=\frac{\sqrt{m_{01}^2&plus;m_{02}^2&plus;m_{03}^2}}{m_{00}}" title="D=\frac{\sqrt{m_{01}^2+m_{02}^2+m_{03}^2}}{m_{00}}" />

<img src="https://latex.codecogs.com/gif.latex?P=\frac{\sqrt{m_{10}^2&plus;m_{20}^2&plus;m_{30}^2}}{m_{00}}" title="P=\frac{\sqrt{m_{10}^2+m_{20}^2+m_{30}^2}}{m_{00}}" />

<img src="https://latex.codecogs.com/gif.latex?\Delta=1-\frac{\sqrt{\left(\sum_{i=0}^{3}m_{ii}^2\right)-m_{00}^2}}{\sqrt3m_{00}}" title="\Delta=1-\frac{\sqrt{\left(\sum_{i=0}^{3}m_{ii}^2\right)-m_{00}^2}}{\sqrt3m_{00}}" />

<img src="https://latex.codecogs.com/gif.latex?\theta=\frac{1}{2}{tan}^{-1}{\left(\frac{\sqrt{m_{20}^2&plus;m_{30}^2}}{m_{10}}\right)}" title="\theta=\frac{1}{2}{tan}^{-1}{\left(\frac{\sqrt{m_{20}^2+m_{30}^2}}{m_{10}}\right)}" />

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

* [HMM-MATLAB](https://drive.google.com/file/d/1Z_uzQeUmP79HdQMYWdQggInOGumdvZgb/view?usp=sharing)

* [HMM-Python](https://drive.google.com/file/d/11WrIFU30zQwAgMMdCH1cybYQhCRFHpjl/view?usp=sharing)

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
