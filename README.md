# AirBnB MongoDB Analysis

`ssh rs8050@i6.cims.nyu.edu`
password: `#X:r7Jz+c[`

`module load mongodb-4.0`
`export LC_ALL=en_US.UTF-8`

`mongoimport --headerline --type=csv --db=rs8050 --collection=listings --host=class-mongodb.cims.nyu.edu --file=listings_clean.csv --username=rs8050 --password=XiVBZLDs`

`mongosh rs8050 --host class-mongodb.cims.nyu.edu -u rs8050 -p`
password: `XiVBZLDs`

