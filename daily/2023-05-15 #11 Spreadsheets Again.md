---
date : "2023-05-15"
title : "#11 Spreadsheets Again"
slug : "11-again"
time : "1h-30m"
summary : "Finished Intro to spreadsheets"
---

Finally finished the the Intro to spreadsheets course on Datacamp. Learned about references and how it can be used.

---

- Chapter 1
    - Navigate spreadsheets
    - Import data
    - Perform calculations
    - Format cells
- Chapter 2
    - Cell references
    - Copy references
    - Calculations w/ references
    - Absolute references

---

- Every cell in a spreadsheet has an associated data type
    - Data types is auto assigned
- `Numeric` Data Type
    - Supports arithmetic and statistical operations
    - Right aligned by default
    - Precision of decimal places can be +/- using the toolbar
- `Plain Text` Data Type
    - Assigned by default, if no other is detected
    - Change Format>Number>Plan Text
    - Also prepend with single quote like `'2` or `'=2+3,` the latter will store the formula rather than evaluating it
- `Date` Data Type
    - Format > Number > Date
    - Right aligned by default
- `Currency` Data Type
    - Anything that starts with `$` , or any other currency is auto detected and assigned
    - It is right aligned by default
- `Logical` Data Type
    - or Boolean values : `TRUE` & `FALSE`
    - These are case sensitive, spreadsheet will convert to upper case
    - Center aligned by default
    - Returned by formulas that include comparison operators.
        - `=` : equals to
        - `<>` : not equals to
        - `<` / `>` : less / greater than
        - `<=` / `=>` : less / greater than equals to

---

- Cell References are a neat way to point and retrieve the values from another cell
    - `#REF!` error is thrown when you try to use self-referencing logic or a circular logic
    - A reference that either directly or by a chain of other references, refers to itself is called a circular reference.
    - Formulas created on circular reference can’t be computed
- Copying of referencing cells horizontally or vertically has the same effect as it follows the referenced cell in the same direction.
- So far these have been relative references

---

- Absolute references don’t change when copied over
    - `$B$7` is represented by `$` before row and column, as this one is showing 7th row of B column
    - It locks and stops the reference shifting in either direction when copied
- Partial absolute references that change in only one direction
    - `$B4` here we are fixing the column index, so it wont change when moving column wise but only when we move row wise
- Examples
    - D2 : `=B2/$B$12 * 100`
    - D3 : `=B3/$B$12 * 100`
    - E2 : `=($C2/$C$12)*100`      
    - E3 : `=($C3/$C$12)*100`
    

---
