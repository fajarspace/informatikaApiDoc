---
weight: 12
title: Get a Specific Dosen
---

## Get a Specific Dosen

```php
<?php
$uuid = "abc123"; // Ganti dengan UUID yang sesuai
$url = "https://informatikaupb.com/api/dosen/" . $uuid . "?nama=true&nidn=true&email=true&telp=true&linkwa=true";

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);

$response = curl_exec($ch);
curl_close($ch);

if ($response) {
    $data = json_decode($response, true);
    if (isset($data['error'])) {
        echo "Error: " . $data['error'];
    } else {
        echo "Nama Dosen: " . $data['nama'];
        echo "NIDN: " . $data['nidn'];
        echo "Email: " . $data['email'];
        echo "Telepon: " . $data['telp'];
        echo "Link WhatsApp: " . $data['linkwa'];
    }
} else {
    echo "Gagal menghubungi API";
}
?>

```

```python
import requests

uuid = "abc123" # Ganti dengan UUID yang sesuai
url = f"https://informatikaupb.com/api/dosen/{uuid}?nama=true&nidn=true&email=true&telp=true&linkwa=true"

response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    print("Nama Dosen:", data["nama"])
    print("NIDN:", data["nidn"])
    print("Email:", data["email"])
    print("Telepon:", data["telp"])
    print("Link WhatsApp:", data["linkwa"])
elif response.status_code == 404:
    print("Dosen tidak ditemukan")
else:
    print("Gagal menghubungi API")
```

```javascript
const axios = require("axios");

const uuid = "abc123"; // Ganti dengan UUID yang sesuai
const url = `https://informatikaupb.com/api/dosen/${uuid}?nama=true&nidn=true&email=true&telp=true&linkwa=true`;

axios
  .get(url)
  .then((response) => {
    const data = response.data;
    console.log("Nama Dosen:", data.nama);
    console.log("NIDN:", data.nidn);
    console.log("Email:", data.email);
    console.log("Telepon:", data.telp);
    console.log("Link WhatsApp:", data.linkwa);
  })
  .catch((error) => {
    if (error.response && error.response.status === 404) {
      console.log("Dosen tidak ditemukan");
    } else {
      console.error("Gagal menghubungi API:", error.message);
    }
  });
```

> Kode Status: 200 OK

```json
{
  "uuid": "dfe8c8b4-23a4-42ed-8aae-42ed8aae42ee",
  "nidn": "0401099001",
  "nama": "Edora, S.Pd., M.Pd.",
  "email": "edora@pelitabangsa.ac.id",
  "telp": "",
  "linkwa": ""
}
```

> Kode Status: 404 Not Found

```json
{
  "msg": "Dosen tidak ditemukan"
}
```

API ini digunakan untuk mengambil data dosen berdasarkan UUID (Universally Unique Identifier).

<!-- <aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->

### HTTP Request

`GET https://informatikaupb.com/api/dosen/{uuid}`

### Parameter Path

| Parameter | Description                                               |
| --------- | --------------------------------------------------------- |
| UUID      | (String, required) - ID unik yang mengidentifikasi dosen. |

### Parameter Query

Anda dapat menggunakan parameter query untuk memilih data yang ingin Anda ambil.

| Parameter | Description                                                                                            |
| --------- | ------------------------------------------------------------------------------------------------------ |
| nama      | (Boolean, opsional) - Jika diatur ke true, akan mengembalikan nama dosen                               |
| nidn      | (Boolean, opsional) - Jika diatur ke true, akan mengembalikan NIDN (Nomor Induk Dosen Nasional) dosen. |
| email     | (Boolean, opsional) - Jika diatur ke true, akan mengembalikan alamat email dosen.                      |
| telp      | (Boolean, opsional) - Jika diatur ke true, akan mengembalikan nomor telepon dosen.                     |
| linkwa    | (Boolean, opsional) - Jika diatur ke true, akan mengembalikan link WhatsApp dosen.                     |
