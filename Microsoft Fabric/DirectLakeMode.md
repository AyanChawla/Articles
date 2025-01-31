
```mermaid  
graph TD  
    A[File]  
    A --> B[Row Group 1 <br> (Rows 1-5)]  
    A --> C[Row Group 2 <br> (Rows 6-10)]  
      
    B --> B1[Column Chunk 1: CustomerID <br> Page: [1, 2, 3, 4, 5]]  
    B --> B2[Column Chunk 2: FirstName <br> Page: [John, Jane, Alice, Bob, Charlie]]  
    B --> B3[Column Chunk 3: LastName <br> Page: [Doe, Smith, Johnson, Brown, Davis]]  
    B --> B4[Column Chunk 4: Age <br> Page: [28, 34, 29, 42, 37]]  
    B --> B5[Column Chunk 5: Gender <br> Page: [M, F, F, M, M]]  
    B --> B6[Column Chunk 6: Email <br> Page: [john@example.com, jane@example.com, alice@example.com, bob@example.com, charlie@example.com]]  
    B --> B7[Column Chunk 7: PhoneNumber <br> Page: [1234567890, 2345678901, 3456789012, 4567890123, 5678901234]]  
    B --> B8[Column Chunk 8: Address <br> Page: [123 Elm St, 456 Oak St, 789 Pine St, 101 Maple St, 202 Birch St]]  
    B --> B9[Column Chunk 9: City <br> Page: [Springfield, Metropolis, Gotham, Star City, Central City]]  
    B --> B10[Column Chunk 10: Country <br> Page: [USA, USA, USA, USA, USA]]  
      
    C --> C1[Column Chunk 1: CustomerID <br> Page: [6, 7, 8, 9, 10]]  
    C --> C2[Column Chunk 2: FirstName <br> Page: [Eve, Frank, Grace, Henry, Irene]]  
    C --> C3[Column Chunk 3: LastName <br> Page: [Wilson, Miller, Moore, Taylor, Anderson]]  
    C --> C4[Column Chunk 4: Age <br> Page: [31, 45, 26, 38, 33]]  
    C --> C5[Column Chunk 5: Gender <br> Page: [F, M, F, M, F]]  
    C --> C6[Column Chunk 6: Email <br> Page: [eve@example.com, frank@example.com, grace@example.com, henry@example.com, irene@example.com]]  
    C --> C7[Column Chunk 7: PhoneNumber <br> Page: [6789012345, 7890123456, 8901234567, 9012345678, 0123456789]]  
    C --> C8[Column Chunk 8: Address <br> Page: [303 Cedar St, 404 Ash St, 505 Fir St, 606 Spruce St, 707 Willow St]]  
    C --> C9[Column Chunk 9: City <br> Page: [Coast City, Bludhaven, Hub City, Keystone City, Smallville]]  
    C --> C10[Column Chunk 10: Country <br> Page: [USA, USA, USA, USA, USA]]  
