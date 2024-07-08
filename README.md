nifti2dicom-cli
=================
Modified version of biolab-unige/nifti2dicom for CLI use optimised for NIFTI conversion to Brainlab-compatible DICOM

The [**original Nifti2Dicom**](https://github.com/biolab-unige/nifti2dicom) is a conversion tool that converts 3D NIfTI files to DICOM. Unlike other conversion tools, it can import a DICOM file that is used to import the patient and study DICOM tags, and allows you to edit the accession number and other DICOM tags, in order to create a valid DICOM that can be imported in a PACS. However, latest versions along with compatible dependencies are incompatible with current Brainlab PACS software.

We optimised version, dependency versions, and code for Nifti2Dicom CLI use to import DICOMs into [**Brainlab**](https://www.brainlab.com/) for pre-operative neurosurgical planning at NHNN (see our [**recent paper**](https://doi.org/10.1162/imag_a_00139) for an example of how processed images feature in our neurosurgical planning protocol (Goedemans et al., 2024). 
Dependencies for nifti2dicom-cli are: :
* Nifti2Dicom v4.9.0
* ITK v5.0.0
* GDCM v2.8.9
* GCC/G++ 8.0
* TCLAP v1.2+
  
## :whale: We made a Docker container for nifti2dicom-cli
So that you don't have to hack at getting nifti2dicom-cli to work on your local system, you can use it out of the box by pulling our nifti2dicom-cli Docker image:

```docker pull nhnnufun/nifti2dicom-cli
```

and run 

```docker run -v /path/on/system/to/nifti/files/to/convert:/opt/nifti2dicom -it nhnnufun/nifti2dicom-cli
```

and use Nifti2Dicom as instructed once the Docker container is running: 

```Nifti2Dicom -h
```

Follow [**these instructions**](https://www.docker.com/get-started/) to install and use Docker.

To use FAT1 Toolbox, which includes our modified Nifti2Dicom-cli tool, go to either our [**Github repo**](https://github.com/nhnnufun/fat1-toolbox) or [**Docker repo**](https://hub.docker.com/layers/nhnnufun/fat1_toolbox). 

