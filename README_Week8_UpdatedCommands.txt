#!/bin/bash/sh

echo '###########'
echo "loading....."

#Action 1:

#To delete the species without a full taxonomy breakdown, we uploaded the README_Week7_Data.txt file to GitHub to view the data. 

#We used Ctrl F to find ';;' which indicates that one category within the phylogeny was non identified. This was to confirm how may species would have to be deleted in the text file. We followed this same step to find the number of lines with single ';' characters, the written 'NA', and just blank spaces.

#We returned to README_Week7_Data.txt file and deleted the lines with the ';;' character present, single ';' character present, 'NA' present, and blank spaces present  using the command...

grep -n ";;" OriginalData.txt | grep -n ";$"
grep -n "NA" OriginalData.txt


#Action 2:

#We officially deleted all of the lines with ';;', ';', 'NA' and blank spaces by using the command...

#sed -e '3d; 5d; 6d; 8d; 12d; 13d; 14d; 15d; 18d; 20d; 21d; 22d; 23d; 24d; 26d; 28d; 29d; 30d; 31d; 33d; 34d; 35d; 36d; 37d; 38d; 39d; 40d; 41d; 42d; 43d; 44d; 45d; 46d; 48d; 49d; 50d; 52d; 54d; 55d; 56d; 56d; 58d; 59d; 60d; 61d; 63d; 64d; 67d; 69d; 72d; 73d; 74d; 76d; 78d; 79d; 80d; 81d; 82d; 84d; 85d; 88d; 89d; 90d; 91d; 92d; 93d; 96d; 98d; 101d; 102d; 103d; 104d; 106d; 107d; 108d; 111d; 114d; 115d; 116d; 118d; 119d; 120d; 121d; 122d; 123d; 125d; 127d; 128d; 129d; 131d; 132d; 133d; 135d; 136d; 137d; 138d; 139d; 142d; 143d; 144d; 145d; 150d' OriginalData.txt

#We decided to use a pipe with a combination of commands, exemplified below, in order make be more time and space efficient. See below, under Action 3.


#Action 3:

#This command will separate the taxonomy categories (Kingdom, Phylum, Class, Order, Family, Genus, Species) listed for each species. These are listed at the very end of the data.

#This command will take out the single semicolons and replace them with tabs, to create the space in between each column.

sed -e '3d; 5d; 6d; 8d; 12d; 13d; 14d; 15d; 18d; 20d; 21d; 22d; 23d; 24d; 26d; 28d; 29d; 30d; 31d; 33d; 34d; 35d; 36d; 37d; 38d; 39d; 40d; 41d; 42d; 43d; 44d; 45d; 46d; 48d; 49d; 50d; 52d; 54d; 55d; 56d; 56d; 58d; 59d; 60d; 61d; 63d; 64d; 67d; 69d; 72d; 73d; 74d; 76d; 78d; 79d; 80d; 81d; 82d; 84d; 85d; 88d; 89d; 90d; 91d; 92d; 93d; 96d; 98d; 101d; 102d; 103d; 104d; 106d; 107d; 108d; 111d; 114d; 115d; 116d; 118d; 119d; 120d; 121d; 122d; 123d; 125d; 127d; 128d; 129d; 131d; 132d; 133d; 135d; 136d; 137d; 138d; 139d; 142d; 143d; 144d; 145d; 150d' OriginalData.txt | sed 's/;/\t/g' | sed 's/\.\./\t/g' 


#Action 4:

#Went to first line of the text file, which provides the titles for each column of data. Added the terms Kingdom, Phylum, Class, Order, Family, Genus, Species, all of which were separated by tabs.

#This was done manually instead of using a command. We did this to ensure the titles were were correctly placed over the corresponding data and to save time.




#This completes the first part of our Final Project as the data is properly organized with incomplete data eliminated.

#The remainder of our project with focus on using RStudio and TR8 Package to analyze different variables of the remaining species data in README_Week7_Data.txt.


echo "done"
