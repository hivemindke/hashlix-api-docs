# 🔓 Decode Hashed Numbers

This endpoint allows you to decode a hashed mobile number (MSISDN), such as those from **M-PESA**, **Airtel**, or **T-Kash**. It’s commonly used for resolving SHA256- or MD5-hashed phone numbers back to their original form—when a match is found in the Hashlix database.

---

## 🌐 Endpoint

```http
POST https://api.hashlix.com/api/v1/msisdn/decrypt/
```

| Header         | Type   | Required | Description                   |
| -------------- | ------ | -------- | ----------------------------- |
| `X-Api-Key`    | string | ✅       | Your service-specific API key |
| `Content-Type` | string | ✅       | Must be `application/json`    |

## 📝 Request Body

```json
{
    "msisdn_hash": "your_hash_here"
}
```

| Field         | Type   | Required | Description                             |
| ------------- | ------ | -------- | --------------------------------------- |
| `msisdn_hash` | string | ✅       | The hashed phone number (SHA256 or MD5) |

## ✅ Success Response

```json
{
    "status": true,
    "status_code": 0,
    "message": "Data found",
    "data": {
        "msisdn": "254712345678",
        "country": "Kenya",
        "carrier": "Safaricom"
    }
}
```

| Field     | Description                   |
| --------- | ----------------------------- |
| `msisdn`  | The original phone number     |
| `country` | Country the number belongs to |
| `carrier` | Mobile network carrier        |

## ❌ Failed Response

```json
{
    "status": false,
    "status_code": 404,
    "message": "No data found.",
    "data": {}
}
```

This typically means the hash does not exist in our database or is not mapped yet.

## 🐍 Python Request Example

=== "Python"

    ```py title='decode.py' linenums='1'
    import requests
    import json

    url = "https://api.hashlix.com/api/v1/msisdn/decrypt/"

    payload = json.dumps({
    "msisdn_hash": "your_hash_here"
    })
    headers = {
    'X-Api-Key': 'your-api-key',
    'Content-Type': 'application/json'
    }
    response = requests.post(url, headers=headers, data=payload)
    print(response.text)
    ```

=== "PHP"

    ```php title='decode.php' linenums='1'
    <?php

    $url = "https://api.hashlix.com/api/v1/msisdn/decrypt/";
    $data = array("msisdn_hash" => "your_hash_here");

    $payload = json_encode($data);

    $ch = curl_init($url);

    curl_setopt($ch, CURLOPT_HTTPHEADER, array(
        'X-Api-Key: your-api-key',
        'Content-Type: application/json'
    ));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $payload);

    $response = curl_exec($ch);
    curl_close($ch);

    echo $response;
    ```

=== "Node.js"

    ```js title='decode.js' linenums='1'
    const axios = require('axios');

    const url = 'https://api.hashlix.com/api/v1/msisdn/decrypt/';

    const payload = {
      msisdn_hash: 'your_hash_here'
    };

    const headers = {
      'X-Api-Key': 'your-api-key',
      'Content-Type': 'application/json'
    };

    axios.post(url, payload, { headers })
      .then(response => {
        console.log(response.data);
      })
      .catch(error => {
        console.error('Error:', error.response?.data || error.message);
      });

    ```

=== "Go"

    ```go title='decode.go' linenums='1'
    package main

    import (
        "bytes"
        "encoding/json"
        "fmt"
        "io"
        "net/http"
    )

    func main() {
        url := "https://api.hashlix.com/api/v1/msisdn/decrypt/"

        payload := map[string]string{"msisdn_hash": "your_hash_here"}
        jsonData, _ := json.Marshal(payload)

        req, _ := http.NewRequest("POST", url, bytes.NewBuffer(jsonData))
        req.Header.Set("X-Api-Key", "your-api-key")
        req.Header.Set("Content-Type", "application/json")

        client := &http.Client{}
        resp, err := client.Do(req)

        if err != nil {
            fmt.Println("Error:", err)
            return
        }
        defer resp.Body.Close()

        body, _ := io.ReadAll(resp.Body)
        fmt.Println(string(body))
    }


    ```
