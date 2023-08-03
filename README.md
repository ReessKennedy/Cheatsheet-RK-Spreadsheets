
> [!warning] 
> This is a very drafty draft. Just pulled together an off-the-top-of-my-head summary to save me time when working in Excel or Gsheets with the plan to iterate (simplify) and improve on this as I go 

## TOP

### Duplicate Values

#### Extensions
[This paid extension](https://www.ablebits.com/google-sheets-add-ons/remove-duplicates/index.php) is really good and creates a status column, which is nice. You can use it once per day for free. 
#### Cell formula method
```
=IF(COUNTIF(A$2:A2, A2)>1, "dup", "")
```
#### Conditional formatting method
(Format > Conditional Formatting)

This will highlight values ... basically just 
```
=COUNTIF($A$2:$A$15,A1)>1
```

But maybe this simplified version that selects the whole column is simpler and better ... it just first sets the range to search and then sets the value to search. 
```
=COUNTIF($A:$A,A1)>1
```
#### Unique only
Because the dup formulas seem to have a hard time marking the second dup, the unique formula-method may be superior
```
=UNIQUE(A2:B15)
```

#### Remove Dups
GSheets has now added this to core: 
Data > Data Cleanup > Remove Dups

more info: 
[Zapier blog](https://zapier.com/blog/remove-duplicates-google-sheets/) <- Catching dups across columns, something I haven't have to do
[Coefficient.io](https://coefficient.io/highlight-duplicates-in-google-sheets) <- Catching fully dup rows instead of just values

### Concat
Joins text strings together. AKA "Merge"
`Example: =CONCATENATE("Hello", " ", "World")` =  Merge many
`concat(a1,a2)` = Merge 2

[My example](https://docs.google.com/spreadsheets/d/17WjoQrpSzYwGH1MSX4pSrcWRrH3o4bUikWfJWT_WwRc/edit?usp=sharing)

### Get values
`A1` = variable = will follow this value around where it is moved to (relative)
`$A1` = hone in on A (relative coluimn)
`$A$1` = hone in specifically on this location (absolute)

From another sheet:
Populate values from another sheet 
```
=Sheet1!A1
```

[My example](https://docs.google.com/spreadsheets/d/17WjoQrpSzYwGH1MSX4pSrcWRrH3o4bUikWfJWT_WwRc/edit#gid=943410636)

### Images
Remote images = `  =IMAGE("https://i.imgur.com/4GRuO9Y.png")  `
Embedded images = INSERT > INSERT IMAGE \> INSERT IMAGE IN CELL

### Moving sheets
1. Click on current sheet drop down
2. Click "Copy to" > Existing spreadsheets (or move it to a new one)

Very helpful! .. you do loose comments when you do this, in my experience, which is why adding motes instead of comments is sometimes more flexible but has some collaborative drawbacks as well. 

### Conditional Formatting
See above for use with finding dups. 

#### Gray-White Rows
This is now a part of core GoogleSheets
[My example](https://docs.google.com/spreadsheets/d/17WjoQrpSzYwGH1MSX4pSrcWRrH3o4bUikWfJWT_WwRc/edit#gid=1945807175)

### Cool add-ons
#### Sheets Nav
Not sure when this was added but the vertical popup makes navigating large sheets much easier.
![Example|200](https://jimhokanson.com/blog/2020/2020_04_Vertical_Tabs_Google_Sheets/default_all_sheet_nav.png)

And then a professor named James (Jim) Hokanson made acool script that improves the vertical navigation and makes it available here [Vertical Tabs in GSheets](https://jimhokanson.com/blog/2020/2020_04_Vertical_Tabs_Google_Sheets/)

### Links to more info

## Nice things

### Adjustability of heights
Adjustable row height and column width is really a great feature. 


## MORE
Top functions for GSheets ...
### SUM
Adds up a range of cells. `Example: =SUM(A1:A10)`

### AVERAGE
Calculates the average of a range of cells. 
`Example: =AVERAGE(A1:A10)`

### COUNT
Counts the number of cells that contain numbers within a range. 
`Example: =COUNT(A1:A10)`

### MAX
Finds the maximum value in a range of cells. `Example: =MAX(A1:A10)`

### MIN
Finds the minimum value in a range of cells. `Example: =MIN(A1:A10)`

### IF
Evaluates a logical condition and returns one value if true, another if false. 
`Example: =IF(A1 > 10, "Greater than 10", "Less than or equal to 10")`

### VLOOKUP
Searches for a value in the leftmost column of a table and returns a corresponding value from another column. 
`Example: =VLOOKUP(A1, Sheet2!A1:B10, 2, False)`

### HLOOKUP
Searches for a value in the top row of a table and returns a corresponding value from another row. 
`Example: =HLOOKUP(A1, Sheet2!A1:B10, 2, False)`

### TEXT
Formats a value as text using a specified format. 
`Example: =TEXT(A1, "dd-mmm-yyyy")`

### TODAY
Returns the current date. 
`Example: =TODAY()`

### NOW
Returns the current date and time. 
`Example: =NOW()`

### LEN
Returns the length of a text string. 
`Example: =LEN(A1)`

### MID
Extracts a substring from a text string. 
`Example: =MID(A1, 3, 5)`

### LEFT/RIGHT
Extracts a specified number of characters from the beginning or end of a text string. `Example: =LEFT(A1, 3) or =RIGHT(A1, 3)`

### SUMIF
Sums values in a range that meet a specified condition. 
`Example: =SUMIF(A1:A10, ">5")`

### COUNTIF
Counts the number of cells that meet a specified condition. `Example: =COUNTIF(A1:A10, ">5")`

### AVERAGEIF
Calculates the average of cells that meet a specified condition. 
`Example: =AVERAGEIF(A1:A10, ">5")`

### COUNTIFS
Counts the number of cells that meet multiple specified conditions. `Example: =COUNTIFS(A1:A10, ">5", B1:B10, "<10")`

### QUERY
Retrieves data from a range using SQL-like syntax. 
`Example: =QUERY(A1:D10, "SELECT A, B WHERE C > 100")`

---
