Glossary of relevant terminology.
Block (HDFS block): This means a block in HDFS and the meaning is unchanged for describing this file format. The file format is designed to work well on top of HDFS.

File: A HDFS file that must include the metadata for the file. It does not need to actually contain the data.

Row group: A logical horizontal partitioning of the data into rows. There is no physical structure that is guaranteed for a row group. A row group consists of a column chunk for each column in the dataset.

Column chunk: A chunk of the data for a particular column. They live in a particular row group and are guaranteed to be contiguous in the file.

Page: Column chunks are divided up into pages. A page is conceptually an indivisible unit (in terms of compression and encoding). There can be multiple page types which are interleaved in a column chunk.

Hierarchically, a file consists of one or more row groups. A row group contains exactly one column chunk per column. Column chunks contain one or more pages.


Below is a visualization, for how it'll look like - 
# Hierarchical Structure of Sample Data  
  
## Sample Data  
  
| CustomerID | FirstName | LastName | Age | Gender | Email             | PhoneNumber | Address       | City        | Country |  
|------------|-----------|----------|-----|--------|-------------------|-------------|---------------|-------------|---------|  
| 1          | John      | Doe      | 28  | M      | john@example.com  | 1234567890  | 123 Elm St    | Springfield | USA     |  
| 2          | Jane      | Smith    | 34  | F      | jane@example.com  | 2345678901  | 456 Oak St    | Metropolis  | USA     |  
| 3          | Alice     | Johnson  | 29  | F      | alice@example.com | 3456789012  | 789 Pine St   | Gotham      | USA     |  
| 4          | Bob       | Brown    | 42  | M      | bob@example.com   | 4567890123  | 101 Maple St  | Star City   | USA     |  
| 5          | Charlie   | Davis    | 37  | M      | charlie@example.com| 5678901234  | 202 Birch St  | Central City| USA     |  
| 6          | Eve       | Wilson   | 31  | F      | eve@example.com   | 6789012345  | 303 Cedar St  | Coast City  | USA     |  
| 7          | Frank     | Miller   | 45  | M      | frank@example.com | 7890123456  | 404 Ash St    | Bludhaven   | USA     |  
| 8          | Grace     | Moore    | 26  | F      | grace@example.com | 8901234567  | 505 Fir St    | Hub City    | USA     |  
| 9          | Henry     | Taylor   | 38  | M      | henry@example.com | 9012345678  | 606 Spruce St | Keystone City| USA    |  
| 10         | Irene     | Anderson | 33  | F      | irene@example.com | 0123456789  | 707 Willow St | Smallville  | USA     |  
  
## Hierarchical Structure  
  
### File  
- Row Group 1 (Rows 1-5)  
  - Column Chunk 1: CustomerID  
    - Page: [1, 2, 3, 4, 5]  
  - Column Chunk 2: FirstName  
    - Page: [John, Jane, Alice, Bob, Charlie]  
  - Column Chunk 3: LastName  
    - Page: [Doe, Smith, Johnson, Brown, Davis]  
  - Column Chunk 4: Age  
    - Page: [28, 34, 29, 42, 37]  
  - Column Chunk 5: Gender  
    - Page: [M, F, F, M, M]  
  - Column Chunk 6: Email  
    - Page: [john@example.com, jane@example.com, alice@example.com, bob@example.com, charlie@example.com]  
  - Column Chunk 7: PhoneNumber  
    - Page: [1234567890, 2345678901, 3456789012, 4567890123, 5678901234]  
  - Column Chunk 8: Address  
    - Page: [123 Elm St, 456 Oak St, 789 Pine St, 101 Maple St, 202 Birch St]  
  - Column Chunk 9: City  
    - Page: [Springfield, Metropolis, Gotham, Star City, Central City]  
  - Column Chunk 10: Country  
    - Page: [USA, USA, USA, USA, USA]  
  
- Row Group 2 (Rows 6-10)  
  - Column Chunk 1: CustomerID  
    - Page: [6, 7, 8, 9, 10]  
  - Column Chunk 2: FirstName  
    - Page: [Eve, Frank, Grace, Henry, Irene]  
  - Column Chunk 3: LastName  
    - Page: [Wilson, Miller, Moore, Taylor, Anderson]  
  - Column Chunk 4: Age  
    - Page: [31, 45, 26, 38, 33]  
  - Column Chunk 5: Gender  
    - Page: [F, M, F, M, F]  
  - Column Chunk 6: Email  
    - Page: [eve@example.com, frank@example.com, grace@example.com, henry@example.com, irene@example.com]  
  - Column Chunk 7: PhoneNumber  
    - Page: [6789012345, 7890123456, 8901234567, 9012345678, 0123456789]  
  - Column Chunk 8: Address  
    - Page: [303 Cedar St, 404 Ash St, 505 Fir St, 606 Spruce St, 707 Willow St]  
  - Column Chunk 9: City  
    - Page: [Coast City, Bludhaven, Hub City, Keystone City, Smallville]  
  - Column Chunk 10: Country  
    - Page: [USA, USA, USA, USA, USA]  
