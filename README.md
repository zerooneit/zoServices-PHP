zoServices
=============
This Project is as implementation for [JSON RPC v2.0 Spec](http://www.jsonrpc.org/specification), this helps for implements and usage methods that is in another server, system, programming languages or platform. 

This is Helpful for  transport data without implements  modules or program in other languages.This package Contains the Server and Client's PHP Implementation of zoServices.

##Changelog


###zoServices v1.0

* Support GET and POST Request.
* Adding Custom Exceptions.
* Adding Config Class.
* Adding CORS config.
* Refactoring code.

## Server

###1. Install

To Use Server just copy all content of Server folder to your htdocs folder, where server will manage all requests
if you want to separate **CLASS** folder and **RESPONSE** folder see Advance Configuration.

###2. Configuration

You can define whom class will use as a default class using for request that don't need specify class name, for
default this is configurate to _Main Class_ in response folder, but you can modify the static method _**defaultClass**_
in **zoServicesConfig.class.php** in _**classes**_ folder.

```php
public static function defaultClass(){
	return 'main';
}
```

###3. Advance Configuration.

If you separate **CLASS** folder you will need configure in main page the next configure.
```php
define ( 'CLASS_PATH',                 'PATH to Server Classes');
```
If you separate **RESPONSE** folder you will need configure in main page the next configure.
```php
zoServiceConfigure::set('responses',  'responses_path');
```
###4. TEST Server

For test if you server is configurate correctly, open your favorite browser and input the url where you install
the server and will replay this JSON string.
```javascript
{"id":null,"error":{"code":-32700,"message":"JSON Parser Error in RPC Request"},"jsonrpc":"2.0"}
```

## Client

###1. Install

To Use Client just copy all content of Client folder to your project folder, where server will manage all requests
if you want to separate **CLASS** folder and **RESPONSE** folder see next topic.

###2. Configuration

If you separate CLASS folder you will need configure in **zoServicesClient.inc.php** the next configure.
```php
define ( 'CLASS_PATH',                 'PATH to Server Classes');
```
to configurate wich is the server modify.
```php
zoServiceConfigure::set('server',   'path to server');
```

To Select the way that client comunnicate with server via **Curl (CURL_ENGINE)** or **Socket (SOCKET_ENGINE)**.
```php
zoServiceConfigure::set('server_type', 	CURL_ENGINE);
```


###3. TEST Client

For test configure you client with a previously installed server, include in your project, then when you can use
the client to call remote classes and methods
```php
require_once zoServicesClient.inc.php

and Instance Client Object.
$client = new zoServicesClient();

Calling Method from default class.
$client->test();

Calling Method from Class.
$client->class->method();

Batch
$client->startBatch();
$client->method();
$client->class->method();

//get results
$client->endBatch();
```




##Support

If Found an Issue, doubt or complain related to this project please contact to

[Diego Resendez](mailto:diego.resendez@zero-oneit.com)
Developer and Lead of the Project.


##Donations

If you want to contribute helping to developt this project.
send mail to [Contributions](mailto:contributors@zero-oneit.com) 
