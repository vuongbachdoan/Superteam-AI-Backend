
---

# How to deploy API

## Prerequisites
- Install and configure [AWS CLI](https://aws.amazon.com/cli/)
- Install and bootstrap [AWS CDK](https://aws.amazon.com/cdk/)
- Pick a region from the Amazon Bedrock [Supported Regions](https://docs.aws.amazon.com/bedrock/latest/userguide/bedrock-regions.html)

## Deploy APIs

```
npm install
cdk deploy --context allowedip="xxx.xxx.xxx.xxx/32"
```

> Replace the value of allowedip with your public IPv4 address

---

# RAG API cURL Commands

This guide provides syntax, parameter explanations, and examples for testing the RAG APIs using `cURL`.

---

## API Commands

### **1. Set Model (QAHeader.js)**

#### **Syntax**
```bash
curl -X POST BASE_URL -H "Content-Type: application/json" \
-d '{
  "modelId": "MODEL_ID"
}'
```

#### **Parameters**
- `BASE_URL`: The endpoint to set the model.
- `MODEL_ID`: The ID of the model to configure.

#### **Example**
```bash
curl -X POST https://api.example.com/setModel -H "Content-Type: application/json" \
-d '{
  "modelId": "amazon.titan-text-premier-v1:0"
}'
```

---

### **2. Submit URLs (WebUrlsForm.js)**

#### **Syntax**
```bash
curl -X POST BASE_URL -H "Content-Type: application/json" \
-d '{
  "urls": ["URL1", "URL2"],
  "exclusionFilters": ["FILTER1"],
  "inclusionFilters": ["FILTER2"]
}'
```

#### **Parameters**
- `BASE_URL`: The API endpoint for URL submission.
- `urls`: Array of URLs to process.
- `exclusionFilters`: Keywords to exclude URLs.
- `inclusionFilters`: Keywords to include URLs.

#### **Example**
```bash
curl -X POST https://api.example.com/updateUrls -H "Content-Type: application/json" \
-d '{
  "urls": ["https://example.com/page1", "https://example.com/page2"],
  "exclusionFilters": ["remove-this"],
  "inclusionFilters": ["add-that"]
}'
```
