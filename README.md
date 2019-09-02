# php-simple-curl
A very simple php curl class

## Usage

- Quick Start and Examples

``` php
use Khazix\Curl;

$url = "http://www.example.com";

$curl = new Khazix();
$curl->get($url);

if ($curl->error){
  echo $curl->error->code;
  echo $curl->error->msg;
} else {
  echo $curl->code;             //Http code like: 200
  var_dump($curl->result);
}
```

- query 

```php
$curl->get($url, ["id"=>1]);
```

- post data

`Content-Type: multipart/form-data;`

```php
$data = ['name'=>'khazix', 'msg'=>'ok'];
$curl->post($url, $data);
```

- post form data  

`Content-Type: multipart/form-data;`

```php
$curl->post($url, $data, 'form');
```

- post json data 

`Content-Type: application/json;`

```php
$curl->post($url, $data, 'json');
```

- post xml data

`Content-Type: text/xml;`

```php
$curl->post($url, $data, 'xml');
```

- upload file data 

`Content-Type: multipart/form-data;`

``` php
  $data = [
      'file' => '/path/to/logfile',
      'type' => 'log file',
  ];

  $curl->post($url, $data, 'file');
```

- put data

``` php
$curl->put($url, $data);
```

- delete data

``` php
$curl->delete($url, ['id'=>3]);
```

- set User Agent

``` php
$curl->setHeader(['User-Agent: Mozilla/5.0']);
$curl->get($url);
```

- set curl Option

```php
$curl->setOption(['CURLOPT_VERBOSE'=>true]);
$curl->get($url);
```
