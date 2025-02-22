# Important Data observations:
- The diseases we have:
    - Neural Foraminal Narrowing (L/R)
    - Subarticular Stenosis (L/R)
    - Spinal Canal Stenosis 
- The orientation is assoicated with the series (so each series of scans is taken from 1 orientation)
- Some studies do not have 25 labels
    - what i mean is that if you look at 1 study, or you index the dataframe and get the rows that correspond to 1 study, there should be 25 rows
        - 5 types of diseases (2 NFN + 2 SS + 1 SCS) * 5 Locations = 25 
    - but some studies dont have all 25 rows
    - 193 of the studies dont have all 25 labels

- Another thing is that each disease SHOULD??? corresponds to 1 orientation, so we can do 1 model per orientation (since there is only 1 outlier)
    - Mapping:
        - Sagittal T1 -> Neural Foraminal Narrowing
        - Sagittal T2/STIR -> Spinal Canal Stenosis	
        - Axial T2 -> Subarticular Stenosis
- NOTE:
    - For Sagittal T1 orientation, there is 1 study (study: 3637444890, series: 3951475160)
    - that was the only study where they gave a diagnosis of Spinal Canal Stenosis from a Sagittal T1 orientation

- We have 1974 unique studies
- There are 6290 unique series, Sagiital one has 2k samples around so 6k divided by 3 which makes sense
- Each study has around 3-4 series

- Usually a majority of the scans use more than 1 scan to make a diagnosis across all 5 locations on the spine
    - what i mean is that if you look at the 5 diagnosis on each location for a series, they use more than 1 scan,
    - so one location can use 1 scan, 2-3 locations can use 1 scan
- there are around 80 sth unique combinations of severity scores and its very imbalanced, some combinations are have a lot more occurences than others, so need to be mitigated.

- The contrast level (look at histogram) and compare among different series vs different studies
- The distribution of pixel values, do a comparison
- Be careful of relatioship btw instance number and slice location 
- What is the relationship btw the instance used for making the diagnosis and the total number of instances in  the series?
- currently what I do is 