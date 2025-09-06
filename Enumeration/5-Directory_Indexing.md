# Directory Indexing

Directory indexing is a function of the web server that allows you to view the contents of a directory in the web accessible path.

Viewing the contents of a directory allows an attacker to gather a lot of information about the installation such as installed plugins and themes without the need to brute force the paths.

To check for directory indexing you can browse to folder locations and see if you get a response that includes "Index Of" and a list of folders / files. Common locations to check would be:

```
/wp-content/
/wp-content/uploads/
/wp-content/plugins/
/wp-content/themes/
/uploads/
/images/
```

If you can browse /wp-content/plugins/ - the enumeration of plugins and versions becomes much easier.

If you can not browse these endpoints, just right click any photo on the site and click "Open in new tab". If the indexing avaible you can find the real endpoint.

Example:

![Directory_Indexing](./img/directory_indexing.png)
