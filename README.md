# localhost
http://192.168.73.128/index.phpy


<?php

$ip = $_SERVER['REMOTE_ADDR'];
$date = date('Y-m-d H:i:s');

$db = new mysqli("localhost", "alaa", "1111", "my_db");

if ($db->connect_error) {
    die("Connection failed: " . $db->connect_error);
}

$sql = "INSERT INTO visits (ip, date) VALUES ('$ip', '$date')";

if ($db->query($sql) === TRUE) {
    echo "Welcome visitor from $ip! You visited at $date.";
} else {
    echo "Error: " . $db->error;
}

$db->close();
?>



