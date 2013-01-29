# Canadian Census: 2011 & 2006 Population by Province and Territory
This repository contains two datasets:
  - Provincial and territorial boundaries
  - Provincial and territorial populations, 2006 & 2011

They are based on 2011 and 2006 Canada Census data obtained from the Government
of Canada's [Open Data Portal].

## Google Fusion Tables Choropleth Instructions:

### Requirements:
- A personal Google account.
- Two datasets provided in this repository:
   - ```canada_provincial_territorial_boundaries.kml```: Province and territory 
     boundaries
   - ```canada_provincial_territorial_populations.csv```: Filtered Census Canada,
     2006 and 2011 population counts for provinces and territories.

### Steps:

#### Import data:
1.  Open Google Drive on a free, personal Google account. Go to 
    http://drive.google.com and log in. 
2.  Create a new table.
    Click: 'Create' -> 'More' -> 'Fusion Table (experimental)'
3.  Upload the provided ```canada_provincial_territorial_boundaries.kml``` file and click 'Next'.
4.  Review the dataset's rows - the column names should be in row 1.
    Click 'Next'.
5.  (Optional) Fill out table metadata. Click 'Finish'.

6.  Repeat steps 1-5 with the provided ```canada_provincial_territorial_populations.csv``` file.

#### Merge tables:
1.  Identify columns in each dataset to merge on:
      - For the provincial boundaries dataset use 'PRENAME'
      - For the provincial populations dataset use 'Prov_Name'.
2.  With the provincial boundaries dataset open, select 'File' -> 'Merge...'
3.  Select the provincial boundaries table from your Google Drive and click
    'Next'.
4.  For each table select the appropriate column identified in step 7 to join
    on. Click 'Next'.
5.  Select the columns to include in the new table and click 'Merge'. I
    recommend the following columns:
      - PRENAME (Province english name)
      - PREABBR (Province english abbreviation)
      - geometry (Province boundary geo-data)
      - Topic
      - Characteristic
      - Total
5.  Click 'View table'.

#### Add a Filter to switch between 2006 and 2011 populations.
1.  In the provincial boundaries dataset, mouse-over the 'Characteristic'
    column header and select 'Change'.
2.  Set 'Type' to 'Text' (Google's import feature incorrectly detects this
    column as containing date data).
    _This change is propagated through to all merged tables._
3.  Switch back to the newly created 'merge' table.
4.  Click 'Filter' -> 'Characteristic'.
    _You should see a sidebar on the left with checkboxes to filter the data to
    show only 2006 or 2011 data.

#### Create choropleth overlay
1. In the tabs along the top, click the '+' button and select 'Add map'.
   _Your existing filters will be carried over and applied to the new layout._
2. From the file menu, select 'Tools' -> 'Change map styles'.
3. Under 'Polygons' select 'Fill color' and select the 'Gradient' tab.
4. Check the 'Show a gradient' radio and select the 'Total' column.
5. Google should have determined the column's range automatically, make sure 
   it is '29474 - 12851821' then click 'use this range'. Click 'Save'.


[Open Data Portal]: http://www.data.gc.ca/
