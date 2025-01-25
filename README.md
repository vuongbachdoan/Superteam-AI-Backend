### API Documentation

**Endpoint:**  
`https://<sample>.execute-api.us-east-1.amazonaws.com/prod/docs`

---

### Request

**Headers:**  
- `Content-Type`: `application/json`

**Payload:**  
```json
{
    "question": "where is AWS Headquater",
    "modelId": "amazon.titan-text-premier-v1:0"
}
```

---

### Response

```json
{
    "response": "Seattle, Washington",
    "citation": "https://www.aboutamazon.com/news/amazon-offices/the-next-chapter-for-hq2-sustainable-buildings-surrounded-by-nature",
    "sessionId": "44216406-7884-4947-8ccc-dc5e13fdfb24"
}
```

---

### Sample cURL

```bash
curl -X POST API_ENDPOINT \
-H "Content-Type: application/json" \
-d '{
    "question": "where is AWS Headquater",
    "modelId": "amazon.titan-text-premier-v1:0"
}'
```

> Replace API_ENDPOINT with API Gateway Endpoint