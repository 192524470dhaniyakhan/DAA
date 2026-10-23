# Task 12: Challenge Scenario

## Given Scenario

The Student Record System must handle 50,000 search requests per hour and maintain 1,000,000 student records. New student records are added daily.

### A. Selection of Algorithm

I would choose **Hash Table Search** as the primary search algorithm because it provides an average search time complexity of O(1). It is suitable for handling frequent searches across one million student records using a unique student registration number.

### B. Performance and Scalability

A hash table can provide fast lookups without scanning all student records. For 50,000 requests per hour, the average request rate is approximately 13.89 requests per second.

The system should be tested under realistic workloads to verify response time, memory usage, and concurrent request handling. Hash table performance depends on the quality of the hash function and collision-handling method.

### C. Handling Daily Updates

When new student records are added, the system should insert the records into the hash table and update the index. Duplicate registration numbers should be rejected or handled according to the system's rules. Record updates and deletions must also keep the index consistent with the main database.

### D. Final Design and Conclusion

The recommended design is to use a **hash-table-based index on student registration numbers**, supported by a reliable database for storing student details.

This design offers expected O(1) search time, supports frequent searches, and allows new records to be indexed as they are added. The system should also include input validation, error handling, backup procedures, and performance testing.

Therefore, hash table indexing is a suitable choice for the given scenario, provided that memory requirements, concurrent requests, and index maintenance are managed properly.
