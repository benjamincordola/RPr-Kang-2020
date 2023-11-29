## Original Study Design
Kang et al. published their study in 2020, measuring the spatial accesibilty of COVID-19 resources in Illinois. Better understanding how resources are spatially orientated related to population, specifically COVID-19 patients and population over 50, informs decisionmakers when allocating resources and funding throughout the state. Their study, written in Python, utilizes a lot of unneccessary parallel processing, and manages population data and relies on a hospital nearest neighbor function inneficiently. 

There is also a problem with the speed limit dataset used in building the network that the study relies on. Roads missing a speed limit, of which there were hundreds, were assigned a default speed limit of 35mph. 

# Planned modification

I will make handling of population data more efficient by using Pandas/Geopandas packages. I will also simplify the study by focusing on just one permutation of variables, as well as redesigning the hospital setting function to utilize a spatially indexed geodataframe of the network nodes to calculate the nearest hospitals. 

In regard to problems with speed limit, I will use the osmnx.speed package to fill in missing speed limit data by using the mean speed limits of the other roads of the same type (residential, primary, trunk).

# Plan for visualizing results

Simplifying the code will not necessarily change the results of the study, just make it faster and more efficient to run. This will improve the experience of students or peers attempting to analyze this study in the future. I will evaluate the change a new speed limit calculation might have on the study by ocmparing before and after changes in the final output figures. 
