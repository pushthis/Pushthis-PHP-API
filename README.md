
```//      ____                     __     __     __      _                _        
  //     / __ \  __  __   _____   / /_   / /_   / /_    (_)   _____      (_)  ____ 
  //    / /_/ / / / / /  / ___/  / __ \ / __/  / __ \  / /   / ___/     / /  / __ \
  //   / ____/ / /_/ /  (__  )  / / / // /_   / / / / / /   (__  )  _  / /  / /_/ /
  //  /_/      \__,_/  /____/  /_/ /_/ \__/  /_/ /_/ /_/   /____/  (_)/_/   \____/ 
```

# Pushthis PHP Package
This is a package made for PHP, to interact with the Pushthis RESTful API Network Access Point to send payloads through the network to your client side in real-time! 

# Installing
```sh
composer require pushthis/pushthis
```

# How to use
>Define the package 
```php
require_once("autoload.php");
use Pushthis\Pushthis;
```

> **NOTE** -- if your using any PHP Framework, the following is not required. The framework is already doing it.
```php
require_once("autoload.php"); 
```


> Define your keys and access point
```php
$pushthis = new Pushthis('key', 'secret', 'Access Point');
```

> Single Payload Requests
```php
$pushthis = new Pushthis('key', 'secret', 'Access Point');
$pushthis->send(array(
	'channel' => 'the_chat',
	'event' => 'new_message',
	'username' => 'john_doe',
	'message'  => 'Hello Everyone!'
));
```

> Multi-Payload Requests
```php
$pushthis = new Pushthis('key', 'secret', 'Access Point');
$pushthis->add(array(
	'channel' => 'the_chat',
	'event' => 'new_message',
	'data' => array(
		'username' => 'john_doe',
		'file_name'  => 'Hello Everyone!'
	)
));
$pushthis->add(array(
	'channel' => 'system',
	'event' => 'alert',
	'data' => array(
		'username' => 'john_doe',
		'message'  => 'THE INTERNET IS OFFLINE!'
	)
));
$pushthis->send();
```

> Authorizing Payload Request
```php
$pushthis = new Pushthis('key', 'secret', 'Access Point');
$pushthis->authorize(true, "channel", "socketId");
```

# Indepth Documentation
> Documentation for Pushthis.io can be found at https://pushthis.io/documentation

# Contributors & Honorable Mentions
- Devitgg @ https://github.com/devitgg
- Nhalstead @ https://github.com/nhalstead
