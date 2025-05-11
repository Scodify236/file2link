# Image Upload API Documentation

Base URL: `https://abcd.com`

## Endpoints

### Upload Image
Upload an image to Internet Archive and get its access URL.

**URL:** `/upload`  
**Method:** `POST`  
**Content-Type:** `multipart/form-data`

#### Request Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| file | File | The image file to upload (supported formats: jpg, jpeg, png, gif) |

#### Success Response
**Code:** 200 OK  
**Content Example:**
```json
{
    "success": true,
    "access_url": "https://archive.org/download/shop_proj/550e8400-e29b-41d4-a716-446655440000.jpg",
    "item_id": "shop_proj",
    "original_filename": "example.jpg",
    "unique_filename": "550e8400-e29b-41d4-a716-446655440000.jpg",
    "metadata": {
        "title": "Shop Project Image - example.jpg",
        "mediatype": "image",
        "collection": "opensource",
        "description": "Original filename: example.jpg",
        "creator": "Shop Project Uploader",
        "date": "2024-03-14",
        "licenseurl": "https://creativecommons.org/licenses/by/4.0/",
        "subject": ["shop", "project", "images"],
        "original_filename": "example.jpg"
    }
}
```

#### Error Response
**Code:** 400 Bad Request  
**Content Example:**
```json
{
    "error": "No file part"
}
```

**Code:** 500 Internal Server Error  
**Content Example:**
```json
{
    "error": "Upload failed"
}
```

## Rate Limiting
The API implements rate limiting to prevent abuse. Please contact the administrator for rate limit information.

## Authentication
Currently, no authentication is required to use the API.

## Examples

### cURL
```bash
curl -X POST \
  https://abcd.com/upload \
  -H 'Content-Type: multipart/form-data' \
  -F 'file=@/path/to/image.jpg'
```

### Python
```python
import requests

url = "https://abcd.com/upload"
files = {'file': open('image.jpg', 'rb')}
response = requests.post(url, files=files)
print(response.json())
```

### JavaScript
```javascript
const formData = new FormData();
formData.append('file', fileInput.files[0]);

fetch('https://abcd.com/upload', {
    method: 'POST',
    body: formData
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
``` 