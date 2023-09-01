---
weight: 11
title: Dosen
---

# Dosen

## Get All Dosen

```php
<?php

require_once 'path/to/auth.php';

$api = authorize("meowmeowmeow");

$result = $api->getdosen();

?>
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.dosen.get()
```

```shell
curl "http://example.com/api/dosen"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let dosen = api.dosen.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all dosen.

### HTTP Request

`GET https://informatikaupb.com/api/dosen`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include dosen that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>
