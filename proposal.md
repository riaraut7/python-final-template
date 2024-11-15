# Final project proposal
### Please prepare a short proposal on your final project idea by **Nov 18**. The proposal should include:

## Title & description of the project
Title: Sea all the birds
We will be looking at seabirds distribution and generally exploring how seabird populations have changed over the past few decades (1987-present day) due to ecosystem protection, climate variables/sea temp, and fishery practices. 

## Your name & partner's name
Ria Raut, Eric Heisey, Maedeh Chitsaz 

## A precise description of the data required, and how it will be obtained (e.g. please link directly to an actual data source you can read into Python)
Dataset: seabird data (link: https://data.caloos.org/#module-metadata/2458d7c2-af69-4a76-abfb-195fb5aa8f14/fd52ea1e-8259-41b0-8a7b-cf75f018b834, go to the bottom and click downloads, then download the csv). We used a subset of this data that's available in this project folder (see calcofi_birds_species_subset), because the original file was 20 MB and difficult to upload/push to GitHub:) 

We'll be using a series of other datasets, which are all open access: 
- Question 1:
For protected areas: https://data.ca.gov/dataset/california-marine-protected-areas-ds582 

- Question 2:
climatic variables data: https://www.faralloninstitute.org/moci
Sea surface temperature: https://library.ucsd.edu/dc/search?f%5Bcollection_sim%5D%5B%5D=Shore+Stations+Program+Data+Archive%3A+Current+and+historical+coastal+ocean+temperature+and+salinity+measurements+from+California+stations&id=bb4719748r&sort=title_ssi+asc

- Question 3:
Fisheries: dataset from module 2: https://huggingface.co/datasets/cboettig/ram_fisheries/tree/main/v4.65 

Description of the data: Each row is a observation of species of the California, and there are > 90k observations. Columns include: species, geometry, year, date, count (# of that species found; there's also a value of count per km2), lat and long values, season, a 'cruise' column (which is a unique sampling effort - all data was collected from a set number of cruises out to sea). 
  
## 3 questions / analysis tasks you will perform on the data; in the spirit of the assignments we have been doing
1. Are seabird popoulations more stable or increasing in marine protected areas compared to unprotected ones?
To do this, we can talk to another dataset to get geometric multipolygons for marine protected areas and overlay them on a map. Then we'll ovealy all the seabird data on the same map and specify whether or not a given obseration falls within or outside the marine protected area, and see overtime if seabird populations are more stable (so increasing or basically not significantly declining) in marine protected area than outside. We will do this using glms (or something similar). We might also using the fisheries data as a variable in the glm to test this hypothesis. Fishing was banned around Channel islands in 2003 when it was designated a marine protected area. Our seabird observations cover all of the Channel Islands (and a couple other marine protected areas). 
 
2. How do seabird populations of different species respond to changing sea surface temperatures or climatic variables?
To address this, we could used a combination of sea surface temperature datasets from different stations and see how changing sea temps in our areas of interest (the locations where we have observed these seabirds) correlate with average (per species) population change. We will also use the MOCI dataset (which gives you a metric of a bunch of sea/climate variables) to see if seabird species populations change with other climatic predictors as well, such as ENSO oscillations. Note that the MOCI dataset starts in 1994, so we'd be clipping some of the older data from our seabirds dataset, which is a major factor in also considering sea surface temperature. 

3. How do fishery practices/methods influence different seabirds species populations over time?
To address this, we would basically see how the amount of fish caught in this section of California (in certain regions, if possible), influences seabird populations over time.


This seabird dataset has over a hundred species recorded in the 33 years of data collection, however, 42 species have over 100 observations, so we will likely focus on these species. Of particular interest may be species like Ashy Storm-Petrel, or Black-vented Shearwater, where most of the species' range falls within California. Ashy Storm-Petrel only breeds in California, and Black-vented Shearwater only breeds on a few islands in Baja California, Mexico just outside California waters. Ashy Storm-Petrel is listed as federally endangered, while Black-vented Shearwater is near threatened. We may look at other species as well, but these might be good starting points.

Please create your proposal in a markdown file called `proposal.md` in the root directory of the final project repo.  

