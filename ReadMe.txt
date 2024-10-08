# Arewa Wise Data API Documentation

_Msorg API_


_API Requests_

## Buy Data

```php
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://arewawisedata.com.ng/api/data/external.php',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => json_encode(array(
    'network' => 1,
    'mobile_number' => '09066947271',
    'plan' => 319,
    'Ported_number' => true
  )),
  CURLOPT_HTTPHEADER => array(
    'Authorization: Token 2a3fb8f841d94158ae2c199fa5e223b7268069aa8ce12202fb',
    'Content-Type: application/json'
  ),
));
```

*API Requests*

*Buy Data*

- *URL:* `http://localhost:8080/api/data/index.php`
- *Method:* `POST`
- *Parameters:*

    - `network`: 1
    - `mobile_number`: `09066947271`
    - `plan`: 319
    - `Ported_number`: `true`

_Data API Price_

```php
https://arewawisedata.com.ng/api/dataplan/index.php
```
*Buy Airtime*

- *URL:* `http://localhost:8080/api/airtime/index.php`
- *Method:* `POST`
- *Parameters:*

    - `network`: 1
    - `amount`: 100.00
    - `mobile_number`: `09066947271`
    - `Ported_number`: `true`
    - `airtime_type`: `VTU`

*Data API response*

Depends on whether if the request is successfully handled not resolved and if any error occurred including no enough balance or invalid API key.

```php
code here
```

When request is handled the response after decorating should continue this array with Status failed/successful , failed transaction might happen when user enters wrong number.

```php
code here
```

_API Requests For Arewa Wise Native_

## Buy Data

```php
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'http://localhost:8080/api/data/index.php',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => json_encode(array(
    'network' => 1,
    'mobile_number' => '09066947271',
    'plan' => 319,
    'Ported_number' => true
  )),
  CURLOPT_HTTPHEADER => array(
    'ArewaWiseToken: 2a3fb8f841d94158ae2c199fa5e223b7268069aa8ce12202fb',
    'Content-Type: application/json'
  ),
));
```

## Buy Airtime

```php
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'http://localhost:8080/api/airtime/index.php',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => json_encode(array(
    'network' => 1,
    'amount' => 100.00,
    'mobile_number' => '09066947271',
    'Ported_number' => true,
    'airtime_type' => 'VTU'
  )),
  CURLOPT_HTTPHEADER => array(
    'ArewaWiseToken: 2a3fb8f841d94158ae2c199fa5e223b7268069aa8ce12202fb',
    'Content-Type: application/json'
  ),
));
```

### Code Example Using single function 

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

```php
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