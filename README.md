# Arewa Wise API Documentation


_API Requests_

_Buy Data_

- _URL:_ `http://localhost:8080/api/data/index.php`
- _Method:_ `POST`
- _Parameters:_

    - `network`: 1
    - `mobile_number`: `09066947271`
    - `plan`: 319
    - `Ported_number`: `true`

```
$token = '2a3fb8f841d94158ae2c199fa5e223b7268069aa8ce12202fb';
$mobileNumber = '09066947271';
$portedNumber = true;
```
## Buy Data
```
$curl = curl_init();
curl_setopt_array($curl, [
    CURLOPT_URL => 'http://localhost:8080/api/data/index.php',
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_ENCODING => '',
    CURLOPT_MAXREDIRS => 10,
    CURLOPT_TIMEOUT => 0,
    CURLOPT_FOLLOWLOCATION => true,
    CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
    CURLOPT_CUSTOMREQUEST => 'POST',
    CURLOPT_POSTFIELDS => json_encode([
        'network' => 1,
        'mobile_number' => $mobileNumber,
        'plan' => 319,
        'Ported_number' => $portedNumber
    ]),
    CURLOPT_HTTPHEADER => [
        'ArewaWiseToken: ' . $token,
        'Content-Type: application/json'
    ],
]);
$dataResponse = curl_exec($curl);
curl_close($curl);
```

## Buy Airtime

_Buy Airtime_

- _URL:_ `http://localhost:8080/api/airtime/index.php`
- _Method:_ `POST`
- _Parameters:_

    - `network`: 1
    - `amount`: 100.00
    - `mobile_number`: `09066947271`
    - `Ported_number`: `true`
    - `airtime_type`: `VTU`

_Example Code_

```
$curl = curl_init();
curl_setopt_array($curl, [
    CURLOPT_URL => 'http://localhost:8080/api/airtime/index.php',
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_ENCODING => '',
    CURLOPT_MAXREDIRS => 10,
    CURLOPT_TIMEOUT => 0,
    CURLOPT_FOLLOWLOCATION => true,
    CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
    CURLOPT_CUSTOMREQUEST => 'POST',
    CURLOPT_POSTFIELDS => json_encode([
        'network' => 1,
        'amount' => 100.00,
        'mobile_number' => $mobileNumber,
        'Ported_number' => $portedNumber,
        'airtime_type' => 'VTU'
    ]),
    CURLOPT_HTTPHEADER => [
        'ArewaWiseToken: ' . $token,
        'Content-Type: application/json'
    ],
]);
$airtimeResponse = curl_exec($curl);
curl_close($curl);
```

### Using single function 

*API Requests*

*Buy Data*

- *URL:* `http://localhost:8080/api/data/index.php`
- *Method:* `POST`
- *Parameters:*

    - `network`: 1
    - `mobile_number`: `09066947271`
    - `plan`: 319
    - `Ported_number`: `true`

*Buy Airtime*

- *URL:* `http://localhost:8080/api/airtime/index.php`
- *Method:* `POST`
- *Parameters:*

    - `network`: 1
    - `amount`: 100.00
    - `mobile_number`: `09066947271`
    - `Ported_number`: `true`
    - `airtime_type`: `VTU`

*Example Code*

```
$token = '2a3fb8f841d94158ae2c199fa5e223b7268069aa8ce12202fb';
$mobileNumber = '09066947271';
$portedNumber = true;

function sendRequest($url, $params) {
    $curl = curl_init();
    curl_setopt_array($curl, [
        CURLOPT_URL => $url,
        CURLOPT_RETURNTRANSFER => true,
        CURLOPT_ENCODING => '',
        CURLOPT_MAXREDIRS => 10,
        CURLOPT_TIMEOUT => 0,
        CURLOPT_FOLLOWLOCATION => true,
        CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
        CURLOPT_CUSTOMREQUEST => 'POST',
        CURLOPT_POSTFIELDS => json_encode($params),
        CURLOPT_HTTPHEADER => [
            'ArewaWiseToken: ' . $GLOBALS['token'],
            'Content-Type: application/json'
        ],
    ]);
    $response = curl_exec($curl);
    curl_close($curl);
    return $response;
}

// Send requests
$dataResponse = sendRequest('http://localhost:8080/api/data/index.php', [
    'network' => 1,
    'mobile_number' => $mobileNumber,
    'plan' => 319,
    'Ported_number' => $portedNumber
]);

$airtimeResponse = sendRequest('http://localhost:8080/api/airtime/index.php', [
    'network' => 1,
    'amount' => 100.00,
    'mobile_number' => $mobileNumber,
    'Ported_number' => $portedNumber,
    'airtime_type' => 'VTU'
]);
```

Feel Free Contact Us for More Clarifications!
