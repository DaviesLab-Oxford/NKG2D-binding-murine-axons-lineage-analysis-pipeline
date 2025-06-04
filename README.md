# NKG2D-binding-neurites-analysis-pipeline

We share a pipeline for semi-automatically quantifying NKG2D binding on axons by using scripts based in Matlab and Fiji. It can be applied to other experiments for analysing the binding of a protein to axons of neurons.

We would like to acknowledge Dr Demetrio Labate for the creation of the Dimensionality Ratio method contained within the SomaExtration package and thank Dr Labate for allowing its inclusion as part of our analysis pipeline:
Kayasandik CB, Labate D. Improved detection of soma location and morphology in fluorescence microscopy images of neurons. J Neurosci Methods. 2016 Dec 1;274:61-70. doi: 10.1016/j.jneumeth.2016.09.007. 

Before running the pipeline, please see 'MATLAB online_installation.PDF' for installing the package (SomaExtraction-master) on Matlab (online or desktop version). 

The test images (Example_Test images.zip) can be downloaded from 'files'.
 
Please run the pipeline by following the steps below:
 
Step 1: Generate MIP (maximum intensity projection) images of BtubIII+ neurons and segmented images by running script 'NKG2D macro A_threshold_transform.ijm' in Fiji.
 
Step 2: Upload the generated BtubIII+ and segmented images to the folder on Matlab and run the script 'Matlab_Script_Gaussian.m'. Soma mask array written in .txt files can be downloaded.

Step 3: Transform mask array into soma mask images by running script 'NKG2D macro B_Soma_mask.ijm' in Fiji.

Step 4: Automatically Measure total area of BtubIII+ and BtubIII+Tdtomato+ axons and count NKG2D+ particles within the corresponding axons by running 'NKG2D macro C_area_particle counting.ijm'in fiji.

Step 5: Save 'Summary' containing particle counts and 'Results' containing area of axons. 

Step 6: Calculate NKG2D+ particle density in BtubIII+Tdtomato+ and BtubIII+Tdtomato- axons: 
        
        total area of BtubIII+Tdtomato- axons = total area of BtubIII+ axons - total area of BtubIII+Tdtomato+ axons; 
        
        NKG2D+ particle cunts of BtubIII+Tdtomato- axons = NKG2D+ particle counts of BtubIII+ axons - NKG2D+ particle counts of 
        BtubIII+Tdtomato+ axons; 
        
        NKG2D+ particle density of BtubIII+Tdtomato+ axons = NKG2D+ particle counts of BtubIII+Tdtomato+ axons / total area of 
        BtubIII+Tdtomato+ axons;
        
        NKG2D+ particle density of BtubIII+Tdtomato- axons = NKG2D+ particle counts of BtubIII+Tdtomato- axons / total area of 
        BtubIII+Tdtomato- axons
 
