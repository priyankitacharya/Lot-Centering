# Lot-Centering
 Automation for aligning text items (i.e. lot numbers) with the geometric centers of closed path items (i.e. lot polygons) within an AI script. After having discussions with designers,  manually doing the same task on average takes around 30 mins and in some couple of hours , per AI script.\


## Implementation-Algorithm\

INPUTS : A set of selected items i.e. PathItems (Closed polygons representing lots) and TextFrames (Text items to be aligned to the centroids of the PathItems)\
Step 1 : Aligning TextFrame with respective PathItem using a boundary validation algorithm\
        For each TextFrame:\
            First test against the bounding box of the PathItem.\
            If inside, perform a detailed boundary check (Ray-Casting approach).\
Step 2 : Centroid Calculation:\
         For the PathItem containing the TextFrame:\
            Compute its centroid using Geometric Decomposition:\
            Decompose the shape into triangles.\
            Calculate the centroid of each triangle and weight it by its area.\
            Aggregate results to find the overall centroid.\
Step 3 : Text Alignment\
OUTPUT : TextFrames aligned to the centroids of their corresponding PathItems.\
