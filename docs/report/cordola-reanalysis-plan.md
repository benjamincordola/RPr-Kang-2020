# Pre-Registration of Rpr - Reproduction of Kang et al. 2020 Rapidly measuring spatial accessibility of COVID-19 healthcare resources: a case study of Illinois, USA
Benjamin Cordola 


Published in 2020, Kang et al. measured the spatial accesibilty of COVID-19 resources in Illinois. Better understanding how resources are spatially orientated related to population, specifically COVID-19 patients and population over 50, informs decisionmakers when allocating resources and funding throughout the state. Their study, written in Python, utilizes a lot of unneccessary parallel processing, and manages population data and relies on a hospital nearest neighbor function inneficiently. 

There is also a problem with the speed limit dataset used in building the network that the study relies on. Roads missing a speed limit, of which there were hundreds, were assigned a default speed limit of 35mph. 

Finally, the original study has a function called overlap_calc which, if the hexagon is more than 50% overlapping with that catchment, assigns the weight of a hospital catchment to the hexagon.

## Planned modifications

I will make handling of population data more efficient by using Pandas/Geopandas packages. I will also simplify the study by focusing on just one permutation of variables, as well as redesigning the hospital setting function to utilize a spatially indexed geodataframe of the network nodes to calculate the nearest hospitals. 

In regard to problems with speed limit, I will use the osmnx.speed package to fill in missing speed limit data by using the mean speed limits of the other roads of the same type (residential, primary, trunk).

A modification to the hexagon overlapping problem would be to instead use an area weighted reaggregation to assign weights to the hexagons, based on the percentage of area that is overlapping.

## Plan for visualizing results

Simplifying the code will not necessarily change the results of the study, just make it faster and more efficient to run. This will improve the experience of students or peers attempting to analyze this study in the future. 
I will evaluate the change a new speed limit calculation and new area weighted reaggregation might have on the study by ocmparing before and after changes in the final output figures. 
