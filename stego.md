to retrive info from the jpg 
```
stegseek -sf aa.jpg /usr/share/wordlists/rockyou.txt

StegSeek 0.6 - https://github.com/RickdeJager/StegSeek

[i] Found passphrase: "password"
[i] Original filename: "ss.zip".
[i] Extracting to "aa.jpg.out".


```
this will find password as well as the hinned data 
u can fing the type of file using
```



```file aa.jpg.out
aa.jpg.out: Zip archive data, at least v2.0 to extract, compression method=deflate
```                                                                                    


