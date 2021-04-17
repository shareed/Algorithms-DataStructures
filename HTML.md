## Tables and List
- two of the most common ways of presenting information to users

## Table
- `<table></table>`: Table tag and every tag for the table goes inside this tag
- `tr`: table row
-`td`: table data, each row can contain cells of data
- Each cell in a row fits into a column, giving a grid structure
- `th`: table header(cells that should act as headers, and have special styling)
- semantic elements to arrange our rows into three sections. These tags apply no styling and don’t change our table in any way, they’re just used for organization
    - `thead`
    - `tbody`
    - `tfoot`
    
- There are two important attribute that can be used in table elements, and those are rowspan and colspan. Both of these attributes are used within a td or th element, and they specify how many rows or columns a particular cell might stretch across ex. `rowspan="1"`  and  `colsoan="1"`

- The caption element will attach a caption to a table, should always be placed at the very top of a table, just under the opening table tag

- You can use the type attribute to change the type of characters used to denote a list item
    - `type = "A"` to render uppercase letters
    - `type = "a"` to render lowercase letters
    - `type = "I"` to use roman numerals
- ordered lists support both lowercase and uppercase roman numerals