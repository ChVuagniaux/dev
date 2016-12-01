# Docker dev image

## PHP
Start a ready for dev docker image on your PCs with PHP 7, composer, PHPUnit & vim  
 
`chvuagniaux/dev:php-7` -  [The Dockerfile](php-7/Dockerfile)  

```
docker run -it chvuagniaux/dev:php-7
```

Need to run command with the user id 33 (www-data) ?
```
root@9b49a0499d62:/# su www-data
www-data@9b49a0499d62:/$
```

