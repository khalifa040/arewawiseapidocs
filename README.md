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

*Decoded response*

We have two different responses, failed, success and failed.

*Error response*

This happens when user balance is insufficient, invalid API key etc.

```php

Array
(
  [error] => Array
    (
      [0] => Error message here
    )
)

```

*Successful response*

This response either success or failed and it happens when phone number is not available in the chosen network (MTN etc)

*Successful Response*
```
Array
(
  [user] => 178640
  [network] => 1
  [plan] => 7
  [data_type] => SME
  [mobile_number] => 0813000005
  [Status] => successful
  [medium] => API
  [payment_medium] => MAIN WALLET
  [create_date] => 2024-09-22T07:03:16.824
  [balance_before] => 42091.6
  [balance_after] => 41833.6
  [plan_amount] => 258.0
  [Ported_number] => true
  [refund] => false
  [ident] => Data16708541227624309319
  [customer_ref] => 
  [provider_source] => MYMTNAPP
  [api_response] => Dear Customer, You have successfully shared 1GB Data to 234810000045. Your SME data balance is 45090.06GB expires 28/10/2024. Thankyou
  [automation] => others
  [retry_count] => 0
  [payload] => null
)
```

*Failed Response*
```
Array
(
  [user] => 178640
  [network] => 1
  [plan] => 7
  [data_type] => SME
  [mobile_number] => 08134000005
  [Status] => failed
  [medium] => API
  [payment_medium] => MAIN WALLET
  [create_date] => 2024-09-22T07:03:16.824
  [balance_before] => 42091.6
  [balance_after] => 41833.6
  [plan_amount] => 258.0
  [Ported_number] => true
  [refund] => false
  [ident] => Data16708541227624309319
  [customer_ref] => 
  [provider_source] => MYMTNAPP
  [api_response] => This is not Airtel phone number
  [automation] => others
  [retry_count] => 0
  [payload] => null
)
```


_Data API Price_

```php
https://arewawisedata.com.ng/api/dataplan/index.php
```

*Response*

```php
Array
(
    [0] => Array
        (
            [plan_id] => 1
            [network] => 1
            [plan_type] => monthly
            [month_validate] => 30
            [plan] => 1GB
            [api_price] => 500
            [network_title] => MTN
        )
    [1] => Array
        (
            [plan_id] => 2
            [network] => 2
            [plan_type] => daily
            [month_validate] => 1
            [plan] => 500MB
            [api_price] => 200
            [network_title] => Glo
        )
)
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
