## Objective
Create a NoSQL table using DynamoDB and insert sample items.

## Steps

1. Open DynamoDB service
   - Go to DynamoDB → Tables → Create table

2. Configure table
   - Table name: Students
   - Partition key: StudentID (Number)
   - Keep default settings

3. Create table and wait until status becomes Active.

4. Add items
   - Open the created table
   - Go to Explore table items → Create item

5. Insert sample data
   Item 1
   StudentID: 1
   Name: John
   Age: 22

   Item 2
   StudentID: 2
   Name: Alice
   Age: 21

6. Save items

7. View stored records in table

## Result
The DynamoDB table is created successfully and sample records are stored and displayed.