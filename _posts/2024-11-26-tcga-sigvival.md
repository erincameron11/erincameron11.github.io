---
title: 'TCGA SIGvival: Survival Analysis - Python'
date: 2024-11-26
permalink: /posts/2024/11/tcga-sigvival/
tags:
  - Python
  - Jupyter Notebook
  - Streamlit

---

An interactive TCGA survival analysis application, using ssGSEA to calculate gene signature scores, and kaplanmeier python package to plot kaplan meier plots.


## Introduction
The `TCGA SIGvival` tool is a Python-based web application designed to make cancer data exploration accessible and interactive. Built with Streamlit Community Cloud, the app allows users to perform survival analysis using datasets from The Cancer Genome Atlas (TCGA). By entering specific gene names and cancer types, users can calculate ssGSEA scores and visualize the impact of different genetic factors on patient survival through Kaplan-Meier plots. This streamlined approach enables researchers and data enthusiasts alike to gain insights into cancer outcomes without the need for extensive coding or data preprocessing.

Visit the `TCGA SIGvival` application to explore it yourself at https://tcga-sigvival.streamlit.app.   


<video width="590" height="660" style="display: block;margin: 0 auto;" autoplay loop muted>
  <source src="https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/tcga-sigvival-video.mov" type="video/mp4">
</video>


## Tools & Techniques
* Python
* Jupyter Notebook
* Streamlit


## Objective
Develop a Python application, using Streamlit Community Cloud to perform interactive survival analysis on TCGA cancer datasets.

Behind the scenes, the application performs the following tasks:
1. Loads all relevant datasets to extract gene names, and cancer type data.
2. Uses the user-entered data to calculate ssGSEA scores.
3. Plots the results on a Kaplan Meier plot and outputs the plot.


## Implementation
### Files:
The TCGA Survival Analysis Tool is composed of several key Python files, each serving a distinct function in the process. Below is an overview of the contents of each file and its role in the project:
* **DataPreprocessing.ipynb**: This notebook handles the preprocessing of TCGA data, including formatting, cleanup, and gene name mapping. It ensures that the data is ready for downstream analysis by converting it into a usable format and resolving any inconsistencies in gene annotations.
* **DataAnalysis.ipynb**: This notebook focuses on testing and validating the core calculations for the app. It contains code for performing GSVA (Gene Set Variation Analysis) or ssGSEA (single-sample Gene Set Enrichment Analysis), as well as generating Kaplan-Meier plots to visualize survival data based on gene expression signatures.
* **SurvivalAnalysisTool.py**: This is the main application file, where the Streamlit UI/UX is structured. It defines the layout, handles user inputs, and integrates the functionality provided by the other modules. This is the heart of the app, allowing users to interact with the data and visualize results.
* **data.py**: This file is responsible for loading all the necessary datasets into the application. It provides the data infrastructure for the app, ensuring that the correct files are accessible and properly formatted for analysis.
* **helpers.py**: This utility file handles various functions to support the app’s operation. It includes form validation, submission handling, garbage collection for unused variables, and the creation of the RNA expression dataframe from the selected cancer types. Additionally, it calculates ssGSEA scores, plots Kaplan-Meier curves, and provides functionality for users to download the results.
* **styling.py**: This file implements custom JavaScript and CSS to enhance the user interface of the app. It includes styling for various elements, as well as functionality for auto-scrolling the page in response to user actions, improving the overall user experience.
* **./data folder**: This folder includes all TCGA expression matrices, separated out by cancer types.

### Entering Data into the App
To use the TCGA Survival Analysis Tool, follow these steps on the app's interface:
1. **Enter Signature Name**: Provide the custom name of the gene signature you wish to analyze.
2. **Select Gene Names**: Choose the specific genes you want to include in the analysis. These can be selected from the list of available genes based on the signature.
3. **Select Cancer Types**: Pick one or more cancer types from the available options.
4. **Select Cut-Point**: Choose the cut-point for the survival analysis. This value will be used to categorize patients into high or low expression groups for the Kaplan-Meier plot.   

![TCGA SIGvival - Form Complete](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/tcga-sigvival-form-complete.png)   

5. **Click "Create KM Plot"**: Once all the form fields are filled out, press the button to generate the Kaplan-Meier plot, which visualizes the survival curves based on the selected gene signature and cancer types.   

Output:   
![TCGA SIGvival - ssGSEA Calculation](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/tcga-sigvival-ssgsea-calculation.png) 


![TCGA SIGvival - Output1](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/tcga-sigvival-output1.png)   


![TCGA SIGvival - Output2](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/tcga-sigvival-output2.png) 

These steps provide a simple yet powerful way to perform survival analysis using TCGA data, making the tool accessible to both novice users and experienced researchers.



## Challenges
### 1) Data File Size Limitations
One of the primary obstacles in developing this application was managing the large size of TCGA datasets. These files often exceed several gigabytes, making it challenging to store, share, and process them efficiently. Below are the specific issues faced:

    GitHub File Size Limits: GitHub repositories have a strict file size limit of 100MB per file. This meant that directly pushing TCGA datasets to GitHub was not feasible, as most files were well over this limit.

    Git LFS Restrictions: Git Large File Storage (LFS) was explored as an option for storing large datasets, but the free tier comes with a 1GB storage limit. The TCGA datasets significantly exceed this capacity, forcing a reevaluation of storage solutions. Upgrading to a paid plan was not ideal given the scope and potential budget constraints of the project.

    Various File Reduction Methods: I tested several file formats and compression techniques to reduce overall file sizes. I experimented with Feather for quick read/write times, but it didn't reduce the size enough. Gzip offered good compression, but did not compress the files enough once again. I also tried HDF5, which had minor reductions but remained too large for upload limits and had compatibility challenges. In the end, I chose to stick with Parquet, which provided efficient compression.

    Google Drive Integration: Attempting to use Google Drive as a storage solution faced performance bottlenecks. Downloading and reading the large datasets via Google Drive's share links was extremely slow, impacting the user experience. Additionally, the file handling complexity added extra steps to the workflow, making it less streamlined.

    Dropbox Limitations: Using Dropbox was another potential solution, but the free tier has a 2GB overall storage cap. With the TCGA data exceeding this limit, Dropbox was quickly ruled out as a viable long-term storage solution without significant compromises.
    
    Sparse Matrix Handling: Even when compressing the data into sparse matrices—a technique used to reduce storage requirements by only storing non-zero elements—the file sizes were still problematic. While sparse matrices offer considerable space savings for certain types of datasets, the density of data in TCGA files meant that even compressed versions remained too large to handle efficiently within the constraints of available storage solutions.

### 2) Streamlit Memory Limitations
Another significant challenge encountered during the development of the TCGA survival analysis application was managing memory usage within Streamlit, the framework used to create the app. Handling large datasets in a web-based environment can quickly lead to memory consumption issues, impacting the app's performance and responsiveness. Here are some of the specific memory-related challenges and attempted solutions:

    Caching Data: One approach to mitigate memory limitations was to leverage Streamlit's caching capabilities. Caching allows the app to store previously computed results, potentially reducing memory usage and speeding up load times. However, due to the large size of TCGA data, caching did not yield significant improvements in holding data in memory. The cache seemed insufficient for retaining large datasets, as Streamlit's caching mechanism was not designed to handle the volume and complexity of the data being processed.

    Garbage Collection: To further optimize memory usage, an investigation into Python's garbage collection was conducted. This involved manually clearing variables, objects, and data frames that were no longer in use, allowing the garbage collector to free up memory space. Although this strategy led to some minor memory savings, the improvements were not substantial enough to make a noticeable difference in overall performance. The size and structure of the datasets continued to pose a challenge, requiring additional strategies beyond conventional garbage collection.

Despite numerous attempts to address the file size, memory, and data storage challenges, the ultimate solution required a more targeted approach. The first breakthrough was to split the TCGA expression matrix into separate files based on cancer type, making each file manageable enough to be uploaded to GitHub within its standard limits. This segmentation streamlined the data handling process and allowed for easier access and processing. Additionally, to further reduce the dataset size, and ultimately reduce memory usage as well, the decision was made to focus exclusively on protein-coding genes, using GENCODE's v23 GTF file for data processing. This filtering step significantly decreased the data volume while retaining the most relevant information for survival analysis, making the app more efficient and responsive without sacrificing analytical depth.


## Retrospective Project Analysis
In hindsight, there are several aspects I would approach differently, including:
* **Data Management and Preprocessing**: One of the biggest challenges in this project was dealing with the large size of the TCGA datasets. In retrospect, I could have dedicated more time to optimizing the preprocessing steps, such as more extensive data filtering before loading the datasets into the app. This might have reduced the data size and improved the app’s performance from the beginning.
* **Memory Optimization**: While I explored various memory management strategies within Streamlit, such as caching and garbage collection, there were still instances where the app faced performance bottlenecks. A more in-depth exploration of how to optimize memory usage in a web application, or the use of more powerful back-end processing, might have improved the overall experience, especially with large datasets.
* **File Formats and Compression**: Although I tested several file formats (e.g., Feather, Gzip, Parquet) to reduce data size, I would have taken a more systematic approach to evaluating the trade-offs between compression time, storage space, and load times. For future projects, I would consider exploring more advanced data formats or even custom compression techniques tailored to genomic data.
* **Scalability**: The app worked well with smaller datasets, but as the complexity of the data increases, scalability could become an issue. I would explore ways to scale the app to handle larger datasets more efficiently, such as by integrating cloud computing resources for data processing or optimizing the app's architecture.
* **User Interface Design**: The user interface was functional but could have been more intuitive and polished. I would revisit the design, ensuring that data input and visualization are as seamless as possible for users with varying technical expertise. Adding features like progress indicators or more informative tooltips would also help guide the user experience.