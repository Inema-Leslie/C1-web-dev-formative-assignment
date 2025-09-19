# SQL to JSON Field Mapping All Field Name conversions.

### users table → user.json
[SQL Column]   [JSON Field]
User_id         user_Id 
Name            name 
Phone_number    phone_Number

### transaction table → transaction.json
[SQL Column]   [JSON Field]
 Trans_id       transaction_Id 
 user_id        user_Id 
 Date           date
 Time_stamp     time_Stamp 
 Body           body 

### transaction_categories table → transaction_Categories.json
[SQL Column]     [JSON Field]
 Category_id      category_Id 
 Trans_id         transaction_Id 
 payment_type     payment_Type
 transfer_type    transfer_Type 

### system_logs table → system_Logs.json
[SQL Column]       [JSON Field]
 Log_id             log_Id 
 Trans_id           transaction_Id 
 Status             status 
 Time_stamp        time_Stamp 


## Only user 1 Data Used
- **User**: Des Gasana (ID: 1)
- **Transaction**: Payment to BYD Garage (ID: 2)
- **Category**: Sent MOMO payment (ID: 2)
- **System Log**: Completed status (ID: 6)

## Relationships 
- Transaction 2 belongs to User 1
- Category 2 describes Transaction 2
- System Log 6 tracks Transaction 2