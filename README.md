# McpeUtils

Utils for the game Minecraft PE, written in PHP 7.2.

## Query example

``` php
<?php

include "src/mcpe/Query.php";

//Server IP address
$ip = "0.0.0.0";
//Server port
$port = 19132;

//Timeout
$timeout = 5;

use mcpe\Query;
use stdClass;

$query = new \mcpe\Query($ip, $port, $timeout);

// Connect
$query->connect();

// Query info(stdClass)
$queryInfo = $query->getQueryInfo();

// Ping info(stdClass)
$pingInfo = $query->getPingInfo();

// Ping and query info(stdClass)
$fullInfo = $query->getInfo();


// Dump full info
var_dump($fullInfo);

?>
```

## Rcon example
``` php
<?php

include "src/mcpe/Rcon.php";

$rcon = new \mcpe\Rcon("127.0.0.1", 19132);

$rcon->connect();
$rcon->authorize("mytoppassword");

echo $rcon->sendCommand("help");

```
