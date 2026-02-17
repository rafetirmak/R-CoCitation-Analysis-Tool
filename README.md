Project Title: R-CoCitation-Analysis
Automated Bibliometric Networks from PubMed via NCBI E-utilities

Description
This repository provides a robust R-based workflow for researchers and scientometricians to automate the retrieval of citation data and the construction of scholarly networks using PubMed IDs (PMIDs).

Unlike manual citation harvesting, these scripts utilize the NCBI E-utilities API (via reutils or rentrez) to fetch "cited-by" information and metadata. The workflow is designed to handle API rate limits and potential connection errors through built-in checkpoints and retry loops, ensuring data integrity for large-scale analyses.

Key Features
Citation Retrieval: 
Automates the collection of cited-by links to build raw citation edgelists.

Metadata Enrichment: 
Fetches detailed bibliographic information (Journal, Publication Date, First Author, Title) for any list of PMIDs.

Network Construction:
Converts raw citation data into Bibliographic Coupling or Co-citation networks using igraph.

Robustness: 
Includes rate-limiting (sleep cycles) and progress checkpoints to prevent data loss during long-running tasks.

Format Compatibility: 
Outputs standardized CSV files ready for further analysis or visualization in tools like Gephi.

File,Purpose,Key Library
Supplementary_Code_1_Citation_Retrieval.R,Retrieves citation links (cited-by) for target PMIDs.,reutils
Supplementary_Code_1_Citation_Retrieval_rentrez.R,Alternative retrieval script using the rentrez package.,rentrez
Supplementary_Code_2_Metadata_Enrichment.R,"Collects metadata (authors, journals, dates) for PMIDs.",reutils
Supplementary_Code_3_Network_Construction.R,Generates weighted/unweighted similarity networks.,igraph

How to Use
Prerequisites: 
Install the required R packages:
install.packages(c("reutils", "rentrez", "igraph"))

API Configuration:
While not mandatory, it is highly recommended to use an NCBI API Key to increase your request rate from 3 to 10 requests per second. Set your key in your R environment:
options(reutils.api.key = "YOUR_API_KEY") 
# or
Sys.setenv(ENTREZ_KEY = "YOUR_API_KEY")
Execution: Run the scripts in sequence (1 -> 2 -> 3) to move from a list of PMIDs to a fully structured citation network.

Citation
If you use these scripts in your research, please cite them as follows:

Irmak, R. (2026). R-CoCitation-Analysis: Automated Bibliometric Networks from PubMed. [GitHub Repository/Zenodo DOI].
