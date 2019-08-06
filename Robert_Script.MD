# Data 
`0:15` Let's talk a little about this dataset. This dataset is huge. There were 83 columns including the label and 8.9 million rows. The size of this dataset caused many challenges in itself.

`0:15` The first thing we had to overcome was unpacking and understanding the data. The file itself was too large to be unzipped in the GUI. But, to get around this, we unzipped it on the command line and then did a chmod to give it the right permission.

`0:30` When we started looking into what features were included, we found that the dataset was a little bit different than our expections of it. This data did not have any sort of forensic indicators that could be used to predict malware. Nor, did it have many features that would let us know if there was any sort of risky user behavior. This data only contained Microsoft versioning, configurations, hardware configurations, and location data such as city, state, and organization.

`0:20` Also, we found that a lot of the fields duplicated information that was found in other fields. There were some values that were direct duplicates due to the gathering method, such as SkuEdition and Census_OSSkuName. There were also some fields that were two or more of other fields in the dataset combined. 

`0:10` What this means is that one of the main challenges we had to overcome is which features to select that aren't duplicitive or not affect the label outcome if we included it.

`0:15` To add further complexity to this, almost all of the data in dataset was categoricial. These features were examined as to if they should be one hot encoded, label encoded, or even binary encoded.

`0:45` A good example of this is using binary encoding to separate out the individual flags in the AVProductStatesIdentifier field. Through our research, we learned that this field, even though it looked like an integer was actually a bitwise composite of 17 different features in the Defender Suite whether they were on or off. Some of these settings were also included as separate variables, so to consolidate, we relied mostly on this one.
We tried running this as an integer, as a one hot encoded category, and as the binary encoded 17 categories. However, all of these made marginal differences in model outputs.

