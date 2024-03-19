# Data Exploratory Analysis #

## NO ONE-HOT ENCODING ##

## genre ##
- 8 / 10 genres have less than 10% representation in the data
- Should oversample randomly for these genres
- Should undersample randomly for the other 2 genres
- There are 3 features that heavily correlate to genre (with the skewed representations):
1. loudness (10% correlation)
2. avg_timbre2 (7.5% correlation)
3. mode (6.8% correlation)

## duration ##
- There are a few massive outliers, which is heavily skewing this feature.
- I think we should standardize this data to minutes and get rid of anything greater than 15 min

## var_timbre (ALL) ##
- There are a lot of outliers in each feature. 
- I propose that we standardize by finding the standard deviation and putting each var_timbre in terms of how many standard deviations it is away from the mean


## average_timbre1 ##
- This is the only average_timbre feature that doesn't have all their values 0 centered
- One thing to fix this is subtracting the mean from all the values to adjust it to be 0 centered.

## mode ##
- There's significantly more of mode 1 than 0. This should be okay because the best practice is to have every feature equally represented, but the main focus is balancing the classification features (ie. `genre`).
- One potential solution is to upsample mode 0 and downsample mode 1 before augmenting the classification features.


## time_signature ##
- The time signature 4 was the most prominent out of all the other time signatures.
- I don't think this will play a big factor in the long run, but if we do need to change it, we can try balancing out the time signatures via up/down sampling