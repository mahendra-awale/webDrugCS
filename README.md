# webDrugCS



Visualization of DrugBank Chemical space
========================================

*It's a website (www.gdbtools.unibe.ch:8080/webDrugCS/) for exploration of DrugBank Chemical Space. The visualizer part of the application is based on publicly available THREE.js (http://threejs.org/) javascript library.*

The webDrugCS provides accessed to five different representations of DrugBank Chemical space, which were generated from Principal Components Analysis (PCA) of five different fingeprints namely: MQN, SMIfp, APfp, Xfp and Sfp fingerprints. A user can also map or project external set of compounds onto the DrugBank Chemical Space.

Description of files:

a) webDrugCS.zip: contains files neccessary to run the webDrugCS website. It should be noted that WEB-INF folder contains the JAVA  NetBeans project. One needs to complied this project before deplyoing the web-application. Included JAVA project uses external JCHEM chemistry library from ChemAxon Pvt. Ltd. (https://www.chemaxon.com/). JCHEM library is used to read the molecules (which are supplied by user) and for calculation of molecular fingerprints. Some other task perfomed by classes in JAVA-project is projecting compounds on map and generating iamges for external compounds and re-organizing a co-ordinate data. 

Inside webDrugCS one can find index.html (start page), MQN.jsp, SMIfp.jsp, APfp.jsp, Xfp.jsp and Afp.jsp files. There is one JSP file for each fingeprint. For each fingerprint, respective JSP file loads all related data from file *.data. 

For instance MQN.jsp loads data from MQNhac.data MQNring.data MQNhba.data and MQNrbc.data. So whats inside these files? Each of *.data file contains five lines. 

First Line: 3D-cordinates (X_Y_Z);(X_Y_Z);(X_Y_Z).. for points in 3D-space. Points are sperated by ";". 
Second Line: RGB color information (R_G_B) for respective points given in first line.
Third Line: Average, Standard Deviation and Frequency values for respective points given in first line.
Fourth-Line: DrugBank IDs for drugs locating at respective points given in first line.

b) APfp_mols.zip, MQN_mols.zip, SMIfp_mols.zip, Xfp_mols.zip, Sfp_mols.zip: For each fingeprint there is one zip folder. This zip folder contains the images (png files) of Drgus molecules, which will be shown when mouse is hover on a points in 3D-space. Unzip this folder and copy as it is inside the webDrugCS folder. In zip folder there are png files. Named of the png files start with the index. For instance 0.png, 1.png, 3.png and so on.. This index is actually corrosponds to the points provided on a line 1 in *.data file. So the first X_Y_Z co-ordiante in *.data file is index as 0, second X_Y_Z as 1 and so on.. 

Important: All JSP files call classes from JAVA project in WEB-INF folder. Basically these classes check for the external molecules from user. If the molecules present then it calculated fingepreints for them, their position on map and then images for them. 

If you want to get rid-off these WEB-INF folder then, you will need to change the JSP files and somehow directly needs to read the *.data file by your own. 

c) dbases folder: you find dbases folder inside wrbDrugCS folder. This folder contains subfolder, which corrosponds to each fingeprint. FOr each fingepreint, eigenvalues and eigenvectors are provided. *.totalminmax file contains min and max values from PC1 and PC-2. These files will be used in JAVA-project for projecting the external molecules onto DrugBank chemical space.   
