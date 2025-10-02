# MoMo Transaction API Documentation

## Base URL  
http://localhost:8000

## Authentication
Type: Basic Authentication
Format: Authorization: Basic <base64(username:password)>
Example:
# For admin:password123
Authorization: Basic YWRtaW46cGFzc3dvcmQxMjM=

Demo Credentials:
| Username | Password    |
|----------|-------------|
| admin    | password123 |
| user1    | mypassword  |
| testuser | test123     |

## Endpoints

### 1. GET /transactions
Get all transactions.

curl -u admin:password123 http://localhost:8000/transactions

Query Parameters (Optional):
- limit - Number of results to return
- offset - Number of results to skip

#### 200 OK
{
  "success": true,
  "count": 2,
  "transactions": [
    { "id": 1, "body": "You sent 5000 RWF...", "amount": 5000 }
  ]
}

#### 401 Unauthorized

{ "error": "Unauthorized" }

### 2. GET /transactions/{id}
Get one transaction by ID.

curl -u admin:password123 http://localhost:8000/transactions/1

#### 200 OK

{
  "success": true,
  "transaction": {
    "id": 1,
    "body": "You have sent 5000 RWF to John...",
    "amount": 5000.0,
    "transaction_type": "payment",
    "date": "2024-01-15"
  }
}

#### 404 Not Found
{
  "error": "Not Found",
  "message": "Transaction with ID 1 not found",
  "code": 404
}

---

### 3. POST /transactions
Create new transaction.

curl -u admin:password123 -X POST http://localhost:8000/transactions \
  -H "Content-Type: application/json" \
  -d '{
    "body": "You sent 3000 RWF to Jane Doe", "amount": 3000, "transaction_type": "payment"}'

Request Body (Required):
{
  "body": "Transaction SMS text"
}

#### 201 Created
{
  "success": true,
  "message": "Transaction created successfully",
  "transaction": {
    "id": 128,
    "body": "You sent 3000 RWF to Jane Doe",
    "amount": 3000,
    "transaction_type": "payment"
  }
}

#### 400 Bad Request

{
  "error": "Bad Request",
  "message": "Transaction body is required",
  "code": 400
}

### 4. PUT /transactions/{id}
Update existing transaction.

curl -u admin:password123 -X PUT http://localhost:8000/transactions/1 \
  -H "Content-Type: application/json" \
  -d '{
    "body": "Updated transaction text",
    "amount": 6000
  }'

#### 200 OK
{ "success": true, "id": 1, "amount": 6000 }

#### 404 Not Found
{
  "error": "Not Found",
  "message": "Transaction with ID 1 not found",
  "code": 404
}

### 5. DELETE /transactions/{id}
Delete transaction.

curl -u admin:password123 -X DELETE http://localhost:8000/transactions/1

#### 200 OK
{
  "success": true,
  "message": "Transaction deleted successfully",
  "transaction": {
    "id": 1,
    "body": "You sent 5000 RWF...",
    "amount": 5000.0
  }
}

#### 404 Not Found
{
  "error": "Not Found",
  "message": "Transaction with ID 1 not found",
  "code": 404
}

## HTTP Status Codes

| Code | Meaning                        |
|------|--------------------------------|
| 200  | OK - Request successful        |
| 201  | Created - Resource created     |
| 400  | Bad Request - Invalid input    |
| 401  | Unauthorized - Auth failed     |
| 404  | Not Found - Resource not found |
| 500  | Internal Server Error          |

## Some Testing Examples Without Query Parameters

curl -u admin:password123 http://localhost:8000/transactions
curl -u admin:wrongpassword http://localhost:8000/transactions

### Example With Query Parameters

curl -u admin:password123 "http://localhost:8000/transactions?limit=10&offset=0"

## Security Limitations

Current Implementation: Basic Authentication

Problems:
1. Base64 encoding can be easily decoded
2. No Expiration, credentials valid forever
3. Same header can be reused
4. Credentials sent in plain text

Better Alternatives: Use HTTPS, JWT, or OAuth2 for real-world apps.

