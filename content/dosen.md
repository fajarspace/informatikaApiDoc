---
weight: 11
title: Dosen
---

# Dosen

## Get All Dosen

```php
<?php
$apiUrl = 'https://informatikaupb.com/api/dosen';

$ch = curl_init($apiUrl);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);

if ($response === false) {
    echo 'Error: ' . curl_error($ch);
} else {
    $data = json_decode($response, true);
    print_r($data);
}
curl_close($ch);
?>
```

```python
import requests

api_url = 'https://informatikaupb.com/api/dosen'

response = requests.get(api_url)

if response.status_code == 200:
    data = response.json()
    print(data)
else:
    print(f'Error: {response.status_code}')

```

```javascript
const apiUrl = "https://informatikaupb.com/api/dosen";

fetch(apiUrl)
  .then((response) => {
    if (!response.ok) {
      throw new Error(`Error: ${response.status}`);
    }
    return response.json();
  })
  .then((data) => {
    // Proses data dosen di sini
    console.log(data);
  })
  .catch((error) => {
    console.error(error);
  });
```

> Kode Status: 200 OK

```json
[
  {
    "uuid": "16f1ea02-29b6-48f5-a24d-f3a92d4e72c7",
    "nidn": "0421117604",
    "nama": "Abdul Halim Anshor, S.Kom., M.Kom.",
    "email": "abdulhalimanshor@pelitabangsa.ac.id",
    "telp": "",
    "linkwa": ""
  },
  {
    "uuid": "e586d81d-999b-40c6-a635-6d816f8f4a33",
    "nidn": "0412068909",
    "nama": "Aceng Badruzzaman, S. Pd. I, M. Ag.",
    "email": "aceng_badruzzaman@pelitabangsa.ac.id",
    "telp": "",
    "linkwa": ""
  }
]
```

This endpoint retrieves all dosen.

### HTTP Request

`GET https://informatikaupb.com/api/dosen`

### Parameter Path

| Parameter | Description                                               |
| --------- | --------------------------------------------------------- |
| UUID      | (String, required) - ID unik yang mengidentifikasi dosen. |

### Parameter Query

Anda dapat menggunakan parameter query untuk memilih data yang ingin Anda ambil.

| Parameter | Description                                                                     |
| --------- | ------------------------------------------------------------------------------- |
| nama      | (String, opsional) - Nama dosen yang ingin dicari.                              |
| nidn      | (String, opsional) - NIDN (Nomor Induk Dosen Nasional) dosen yang ingin dicari. |
| email     | (String, opsional) - Alamat email dosen yang ingin dicari.                      |
| telp      | (String, opsional) - Nomor telepon dosen yang ingin dicari.                     |

<!-- <aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside> -->
