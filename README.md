Petrographic report data extraction scripts 
==============================

*project under construction*

This repo contains scripts to extract both volumetric mineralogical data and the complete sample petrographic descriptions from pdf petrographic reports.

Lithological and mineralogical information about rock samples is a key data type in geology. However, commercial petrographic labs tend to provide their reports in document formats like .docx and .pdf. To make effective use of these data we need to be able to extract the specific information in a digital format which we can query and relate to other data.

The scripts in these notebooks currently work on Mason Petrographics reports. Because of the lack of standardisation in reporting, it is a challenge to make a universal approach to extracting the required data.

There are currently 2 notebooks in this repo. The Mason_mineralogy_extract.ipynb notebook uses a combination of computer vision (using OpenCV library) to detect bounding boxes and TesseractOCR engine to OCR the document and extract the volumetric mineralogy provided in tabular form in the Mason reports (see figure below for an example of the page layout). The script then converts these descriptions to the Geological Survey of South Australia mineral and abundance codes for loading into the SA Geodata database.

The second notebook (Mason_mineralogy_extract.ipynb) uses the TesseractOCR engine and regex to extract the petrographic descriptions, sample by sample, for loading into SA Geodata. 

The lithology_mapper.ipynb notebook is a work in progress. The aim is to extract long form lithological names/descriptions and convert these into the most likely rock name and convert to GSSA lithology codes to add a lithology name to each sample in the database.

This project is a work in progress and I will continue to add different scripts to extract data from different styles of petrographic reports as I develop them. These scripts are also quite manual (providing hard links to input directories), and I will work to automate the process more. 

## How to run locally

1. Install the TesseractOCR binaries for your OS: [tesseract on GitHub](https://github.com/tesseract-ocr/tesseract)
2. Clone this repo and create a virtual environment using conda or venv running Python 3.7
3. `pip3 install -r requirements.txt`
4. Ensure you put the correct path to the Tesseract executable if it's not already in your path in the notebook imports

## Example Mason Petrographics sample page

![Mason Petrographics example sample page](https://github.com/RADutchie/Petrography-report-data-extractor/blob/master/static/Mason_eg.jpg)



