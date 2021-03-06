# ccg-bibfiles
![.github/workflows/auto_update_ccg_bib.yml](https://github.com/schen149/ccg-bibfiles/workflows/.github/workflows/auto_update_ccg_bib.yml/badge.svg)

Repository to store cogcomp's bib and cited bib files

## The full steps of maintaining up-to-date cited.bib and cited-recent.bib

0. Create a new bib file containing *only* your added bib entries: yourfile.bib

1. Make sure your bib file is following CCG format with the [conversion tool].(https://github.com/CogComp/ccg-bibfiles/tree/master/ccg_bib_converter)

2. Merge yourfile.bib into cited.bib

       either by copy-paste or the "cat" command

3. *Sub-rountine - Generate correct bib entry keys and sort them by year via JabRef*

       To generate cited-recent.bib: 

              select all entries after year 2004 (2004 included) and make a copy

4. Run script genCitedConference.sh to generate both long and compact bib files

## The full steps of maintaining up-to-date ccg.bib and sync with group server

1. Download the latest bib file version from the group server:
        
       scp hpeng7@legolas.cs.illinois.edu:/srv/data/cogcomp/html/bib/ccg.bib ccg_web.bib

       Remove all the header information

2. Check if the author names is correctly separated by "and"

       manually correct errors 

       or use the java code for assistance (see MainClass.java for details)

3. *Sub-rountine - Generate correct bib entry keys and sort them by year via JabRef*

4. Update the group server version with the fixed ccg_web.bib 

       Add back all the header information

       scp ccg_web.bib legolas.cs.illinois.edu:/srv/data/cogcomp/html/bib/ccg.bib

5. Remove all the header information from ccg_web.bib to get ccg.bib

6. Run script genCitedConference.sh to generate both long and compact bib files

**_Sub-rountine - Generate correct bib entry keys and sort them by year via JabRef_**

       open the program: java -jar jabref.jar

       open file: cited.bib / ccg.bib

       sort all bib entries by year (descending order, i.e. the most recent appears first)

       select-all and generate!: Ctrl-a then Ctrl-g

       say yes, you want to overwrite the keys

       open "Options" - "Preferences" from menu bar, and select "File"

              in "Sort Order" section, make sure you select "Save in current table sort order" 

       save! 

       Manually delete the header:
       % This file was created with JabRef 2.10.
       % Encoding: UTF-8
