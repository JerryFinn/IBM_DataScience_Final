
# IBM Applied Data Science Certificate Capstone Final Project

This project was done to complete the [Applied Data Science Specialization](https://www.coursera.org/specializations/applied-data-science) certificate offered by IBM through Coursera. It was the final project in a series of 4 courses.  
  
1. Python for Data Science, AI & Development
2. Data Analysis with Python
3. Data Visualization with Python
4. Applied Data Science Capstone

## Essential Files to Start

This project is not contained in just one notebook.

### Essential Code

To run all the code, the following files are need:

1. `Capstone_BattleOfNeighborhoods.ipynb`: This is the main driving program. It is the notebook that produces the final report
2. `Census_GeoSpatial.ipynb`: This notebook contains all the calls to GeoPandas. Stack overflow recommended if you had dependencies issue installing Geopandas, but did not want to change your current environment, you could install a 2nd Python environment on your local system. I already had a cloud environment where it worked fine, so I created a separate notebook for GeoPandas calls and ran it in the cloud environment.  
3. `OMA.Rmd`: Some of the data transformation has to be done in R. 

### Essential Data Files

The following files have to exist to run the report. They have to be manually obtained. 

1. `./data/isw_rfp.csv`: This file contains data manually transcribed from a set RFPs that have to be manaully solicited. There is no automated way to get the data.
2. `./data/LTDB/LTDB_Std_All_fullcount.zip`: This file is downloaded from and interactive website. There is no automated way to get the data.
3. `./data/LTDB/LTDB_Std_All_Sample.zip`: Same as the previous file in 2.

### Essential Image Files

Some of the graphics are taken from a previous report and are not generated from the project's code. The images that need to exist prior to execution are:

1. `./data/img/Clusters_all.png`
2. `./data/img/Cluster_BC_2_Strug.png`
3. `./data/img/Cluster_BlueCollar.png`
4. `./data/img/Cluster_Struggling.png`
5. `./data/img/Figure1_SequenceOfMethodology.png`

### Nonesstial Code

`NeighborhoodEvolution.ipynb` contains code that produced some models and did some analysis that lead to the decision to abandon those models. It could be interesting for those that want to see more about model selection. 

## How to Run the Notebooks

`Capstone_BattleOfNeighborhoods.ipynb` contains cells with text that tell the user when to stop and run other notebooks. This it done because the notebooks `Census_GeoSpatial.ipynb` and `OMA.Rmd` need input files created by the Capstone notebook, and the Capstone notebook also needs input files produced by the latter notebooks.

1. Run `Capstone_BattleOfNeighborhoods.ipynb` up till the point the file `./data/isw_rfp_updated.csv` is created
2. Run `Census_GeoSpatial.ipynb` so that it will create the following files needed to continue running `Capstone_BattleOfNeighborhoods.ipynb`. 
    + `./data/cook_tract.geojson`
    + `./data/cook_tract.csv`
    + `./data/isw_rfp_tract.csv`
    + `./data/isw_rfp_tract.geojson`
3. Continue running `Capstone_BattleOfNeighborhoods.ipynb` up till the files `./data/LTDB/colorcode.csv` and `./data/LTDB/ltdb_tracts_labeled.csv` are created.
4. Run `OMA.Rmd` so that it will create the following files needed to continue running `Capstone_BattleOfNeighborhoods.ipynb`.
    + `./data/LTDB/differenceMatrix.RDS`
    + `./data/LTDB/ltdb_series.RDS`
    + `./data/LTDB/ltdb_seq_cluster.RDS`
5. Finish running `Capstone_BattleOfNeighborhoods.ipynb`.
6. From the command line run this command to produce the HTML report  
  
`jupyter nbconvert Capstone_BattleOfNeighborhoods.ipynb --to html --output Capstone_BattleOfNeighborhoods.html --no-input`