# Parsing DICOM files

Digital Imaging and Communications in Medicine (DICOM) is the standard for the communication and management of medical imaging information and related data. [Source](http://dicom.nema.org/medical/dicom/current/output/chtml/part01/chapter_1.html#sect_1.1)

### What is in a DICOM file?
A DICOM data object contains a number of attributes, one of whic is the image data stored as 'PixelData'. There is noly one instance of the ttribute int he object but it can represent one or more images (frames) stored as part of the DICOM file. 

File extension for a DICOM file is .dcm.

### File format
Each element/attribute has a Data Element Tag (gggg,eeee), where ggg represents the Group Number and eeee represents the Element Number. The category of datatstored is defined by these tags - data elements (medical info), file metadata or file structuring data.

### The attributes
[dicom_tags.txt]() file contains the list of attributes we will be recording from the DICOM files. 

[Source of file](https://github.com/khvu/DICOM-Reader/blob/master/DICOM_Reader/DICOM%20Tags.csv)

Apart from these tags, users are allowed to create private tags to store other information. These private tags have odd group numbers and a description of their own.

These tags are stored ina seperate list for later reference.

### The parsing code
The python file in the repo has code to parse the contents of the given DICOM files into a single CSV file containing the filename, all the attributes except PixelData (images) and a list of the private attributes.

THe images are stored in a folder with the filename at the specified location. 

#### To do
* Manage attributes with sub-sequences (Store as seperate csv under folder).
* Resolve package error tat occurs while parsing images in certain DICOM files.
* Find a better way to store private attributes (better retrieval).
