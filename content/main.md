---
weight: 10
title: API Reference
---

# Introduction

Welcome to the Computer Science API! You can use our API to access various Computer Science-related endpoints, which can provide information on a wide range of topics related to computer science and technology within our database.

We offer programming language bindings in Shell, PHP, and JavaScript! You can find code examples in the dark area on the right-hand side, and you can switch between programming languages using the tabs in the top right corner.

**This example API documentation page was created with [DocuAPI](https://github.com/bep/docuapi/), a multilingual documentation theme for the static site generator [Hugo](http://gohugo.io/).**

# Authentication

> To authorize, use this code:

```php
<?php

$apiEndpoint = 'api_endpoint_here';
$authorizationHeader = 'Authorization: meowmeowmeow';

$ch = curl_init($apiEndpoint);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [$authorizationHeader]);

$response = curl_exec($ch);

if (curl_errno($ch)) {
    echo 'Error: ' . curl_error($ch);
}

curl_close($ch);

?>

```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
```

> Make sure to replace `meowmeowmeow` with your API key.

Uses Token to allow access to the API. You can generate a new Token at our [developer portal](http://example.com/developers).

Expects for the API key to be included in all API requests to the server in a header that looks like the following:"

`Authorization: iniadalahtoken`

<aside class="notice">
You must replace <code>iniadalahtoken</code> with your personal Token.
</aside>
