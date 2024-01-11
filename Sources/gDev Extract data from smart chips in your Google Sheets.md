src
[Extract data from smart chips in your Google Sheets - Google Docs Editors Help](https://support.google.com/docs/answer/13524011#zippy=%2Cextract-data-with-syntax%2Cextract-data-from-smart-chip%2Cevent-smart-chip)

# Extract data
When you [insert smart chips into a spreadsheet](https://support.google.com/docs/answer/12319513?sjid=10162500325649056368-NA), you can extract data from the smart chips into separate rows or columns.

![](https://storage.googleapis.com/support-kms-prod/q2cw3WnqhEBQLF2A5xpTleboSyzRi3GW74gY)

1. On your computer, [open a spreadsheet in Google Sheets](http://sheets.google.com/).
2. Select a cell with a single chip or a range of cells that each contain a chip.
3. Choose an option:
    
    1. Right click on the cell or cells ![and then](https://lh3.googleusercontent.com/3_l97rr0GvhSP2XV5OoCkV2ZDTIisAOczrSdzNCBxhIKWrjXjHucxNwocghoUa39gw=w36-h36) **Data extraction** ![](https://lh3.googleusercontent.com/QpJ5UEgqGqkwIkDzxgh2Hw7YXXnsWnmY_wd-qSwnIyTPlQMQlUJirsadX_i4WGzWaQ=w36-h36).
    
    ![Dataextraction](https://storage.googleapis.com/support-kms-prod/7ZHUwbYIIsX89vMm2peJmOMUVrOjOS9pry8o)
    2. Click **Data** > **Data extraction** ![](https://lh3.googleusercontent.com/QpJ5UEgqGqkwIkDzxgh2Hw7YXXnsWnmY_wd-qSwnIyTPlQMQlUJirsadX_i4WGzWaQ=w36-h36).
4. Under “Data to extract,” select the data types you want to extract.
5. Under “Extract to,” select a cell or a range of cells for the extracted data.

## Extract data with syntax

#### Sample Usage

`A2.Location`

`A2.[Creation Time]`

`A2:A4.Title`

#### Syntax

`Cell_or_range.data_type`

- `Cell_or_range`: A cell with one smart chip, or a range of cells each containing a smart chip with the same type.
- `Data_type`: The data type to be extracted from the selected cell or range of cells. 

#### **Example**

Input this formula in B2: 
	=A2.[file name]`

Input this formula in C2: 
	=A2.[creation time]`

Input this formula in D2: 
	=A2.[last modified time]`

#### **Result:**

|   |   |   |   |   |
|---|---|---|---|---|
||**A**|**B**|**C**|**D**|
|**1**|**Chip**|**File Name**|**Creation Time**|**Last Modified Time**|
|**2**|<file chip><br><br>![](https://storage.googleapis.com/support-kms-prod/8pLY5PnpPap04aiuac5lBvYixVT7X9ACnS3u)|Sample Chip Extraction Doc|1/25/2023 13:22:29|1/25/2023 13:22:41|

## Extract data from smart chip

1. On your computer, [open a spreadsheet in Google Sheets](http://sheets.google.com/).
2. Hover over a cell with a single chip.
3. Click **Data extraction** to open a sidebar on the right.
4. Under “Data to extract,” select the data types you want to extract.
5. Under “Extract to,” select a cell or a range of cells for the extracted data.

# Refresh extracted data

To refresh extracted data from cells:

1. On your computer, [open a spreadsheet in Google Sheets](http://sheets.google.com/).
2. Select a cell with a single chip or a range of cells with each containing a chip.
3. Right click on a cell ![and then](https://lh3.googleusercontent.com/3_l97rr0GvhSP2XV5OoCkV2ZDTIisAOczrSdzNCBxhIKWrjXjHucxNwocghoUa39gw=w36-h36) **Smart chips** ![and then](https://lh3.googleusercontent.com/3_l97rr0GvhSP2XV5OoCkV2ZDTIisAOczrSdzNCBxhIKWrjXjHucxNwocghoUa39gw=w36-h36)**Refresh data**.

To refresh extracted data from Data extraction sidebar:

1. On your computer, [open a spreadsheet in Google Sheets](http://sheets.google.com/).
2. Select a cell with a single chip or a range of cells with each containing a chip.
3. Choose an option:
    1. Right click on the cell or cells ![and then](https://lh3.googleusercontent.com/3_l97rr0GvhSP2XV5OoCkV2ZDTIisAOczrSdzNCBxhIKWrjXjHucxNwocghoUa39gw=w36-h36) **Data extraction** ![](https://lh3.googleusercontent.com/QpJ5UEgqGqkwIkDzxgh2Hw7YXXnsWnmY_wd-qSwnIyTPlQMQlUJirsadX_i4WGzWaQ=w36-h36).
    2. Click **Data** > **Data extraction** ![](https://lh3.googleusercontent.com/QpJ5UEgqGqkwIkDzxgh2Hw7YXXnsWnmY_wd-qSwnIyTPlQMQlUJirsadX_i4WGzWaQ=w36-h36).
4. Click **Refresh & manage**.
5. Find the smart chips data you want to refresh.
6. Click Refresh data ![Refresh](https://lh3.googleusercontent.com/czfTw8xFymlMxjcedq9M74vC5dC-vgWPkoh5k50dbu-BJRiZJ1bTgVHkFibURbRZ804=w36-h36)

> [!Tip]
> **Tip:** to refresh all smart chips data, click **Refresh all** at the bottom of the sidebar.

# Smart chip basic types
## People smart chip
Information comes from domain profiles.

- Email
- Name
- Location*
- Phone*
- Title*

> [!NOTE]
> Information with * are only available to Google Workspace Business Standard, Business Plus, Enterprise Essentials, Enterprise Standard, Enterprise Plus, Education Fundamentals, Education Plus, Education Standard, and the Teaching and Learning Upgrade users.

## File smart chip
Information comes from your files in Google Drive.

- MIME Type
- URL
- File Name
- Owner*
- Creation Time*
- Last Modified By*
- Last Modified Time*

> [!NOTE]
> information with * are only available to Google Workspace Business Standard, Business Plus, Enterprise Essentials, Enterprise Standard, Enterprise Plus, Education Fundamentals, Education Plus, Education Standard, and the Teaching and Learning Upgrade users.

## Event smart chip
Information comes from events on your calendar.

- URL
- Summary
- Creator*
- Description*
- Date/time*
- Location*
- Attendees*

> [!NOTE]
>information with * are only available to Google Workspace Business Standard, Business Plus, Enterprise Essentials, Enterprise Standard, Enterprise Plus, Education Fundamentals, Education Plus, Education Standard, and the Teaching and Learning Upgrade users.

