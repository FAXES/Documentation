- [V2 - Node.Js](#v2---node-js)
- [V2 - Lua](#v2---lua)
- [V2 - PHP](#v2---php)

## Node JS

```js
var options = {
    hostname: 'license.example.com',
    port: 443,
    path: '/api/check/PRODUCT_ID',
    method: 'POST',
    headers: {
         'Content-Type': 'application/x-www-form-urlencoded',
         'Authorization': 'LICENSE_KEY',
    }
};
var req = https.request(options, (res) => {
    res.on('data', (d) => {
        console.log(d);
    });
});
```

## Lua
```lua
local productId = 1;
local licenseKey = 'ABC_123';

PerformHttpRequest("https://license.example.com/api/check/" .. productId, function(errorCode, resultData, resultHeaders)
    local data = json.decode(resultData)
    if data['pass'] then        
        print('^2Authorisation completed!^7')            
    else
        print('^1' .. data.details .. '^7')
        os.exit(0)
    end
end, "POST", "", {
    ["Accept"] = "application/json, text/plain, */*",
    ["User-Agent"] = "*",
    ["Authorization"] = licenseKey
});
```

## PHP

```php
<?php
$url = "https://license.example.com/api/check/9"; // 9 is the product ID
$license = "ABC_123";
$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
$headers = array(
   "Accept: application/json",
   "Content-Type: application/json",
   "authorization: $license",
);
curl_setopt($curl, CURLOPT_HTTPHEADER, $headers);
$resp = curl_exec($curl);
curl_close($curl);
$data = json_decode($resp);
// Example response: {"status":"AUTHORISED","pass":true,"details":"Authorisation completed - https://license.example.com"}
if ($data->pass == true) {
    echo "License Passed";
} else {
    echo "License Failed";
    exit;
};
?>
```

*This file has been updated to remove the V1 API options.*
