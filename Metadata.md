# Brain imaging in latam-fingers
Example of data derivative sharing

The following are the details associated with the derivative data from the project "XXXXXXXXXXX," data request ID number XXXXXXXX:

**Description**: Cortical thickness estimated from the baseline MRI of 230 individuals using FreeSurfer (this should be a brief description to indicate what the data pertains to).
**Author**: Esteban Quito  
**Contact**: estebanquito@sillas.edu  
**Date of Last Data Update**: June 6, 1966  
**Associated Files**: data.csv (data) and data_dictionary.csv (data dictionary)

## Methods
 Preprocessing of anatomical brain data
We used the computational anatomy toolbox (CAT12, version r1742,  http://www.neuro.uni-jena.de/cat/, Dahnke et al., 2013) implemented in the statistical parametric mapping software (SPM 12, version v7771, http://www.fil.ion.ucl.ac.uk/spm/software/spm12/) for preprocessing, which consisted of the following steps: We (1) classified brain tissue into grey matter (GM), white matter (WM), and cerebrospinal fluid (CSF) by using an adaptive maximum a posterior technique, which does not necessitate a priori information on tissue probabilites, and by applying a partial volume segmentation approach, which estimates a simplified mixed model of a maximum of two tissue types (Tohka et al., 2004). Based on this tissue segmentation, we (2) estimated for each GM voxel its distance from the WM/GM boundary. This resulted in a WM distance map whose values at the outer GM/CSF boundary represent the GM thickness. Then, we (3) projected these distances’ local maxima to other GM voxels by using a neighbor relationship described by the WM distance. By using this projection-based method, cortical thickness is corrected for partial volume effects, sulcal blurring, and sulcal asymmetries. Next, we (4) corrected topological defects like handles or holes by using spherical harmonics (Yotter, Dahnke, et al., 2011
). We (5) created a spherical map of the cortical surface by using an algorithm that reduces area distortion ( Yotter, Thompson, et al., 2011 ). This spherical mapping allows for reparameterizing the surface mesh into a common coordinate system for inter-subject analysis. Finally, we (6) applied spherical registration to MNI standard space by using the volume-based diffeomorphic DARTEL algorithm ( Ashburner, 2007 ), which was adapted to work with spherical maps. To prepare the surface data for statistical analysis, we used the defaults suggested by CAT12 for cortical thickness analyses: We resampled the surface data by using the supplied 32k surface mesh, which has an average vertex spacing of about 2 mm, and smoothed the data with a full width at half maximum smoothing kernel of 12 mm.
