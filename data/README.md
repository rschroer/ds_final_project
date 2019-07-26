### Notes for Microsoft Defender Kaggle Project dataset.

## Getting and extracting

This dataset is big and I had some challenges in it and with it. It is too big for excel, too big for the OSX GUI unzip and it takea abuout a minute to load into pandas.

To help the other members, I've documented some of the commands to get this up and running on OSX.

1. Unpack it in the command line
`unzip -a microsoft-malware-prediction.zip`

2. Change file priviledges to read write (everyone)
`chmod 666 train.csv`

3. Count the number of lines
`1wc -l train.csv`

Soo, yes, we have 8.9 million rows.