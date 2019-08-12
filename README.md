# Awstats

This is a simple way to analysis the apache log in a full graphic web page.

About Awstats: 

## Run 

If your apache log save in path: /mnt/log/access.log, and you can mount this file to the awstats server for analysis use. 

```
docker run -d --name awstats --hostname ServerName \
  -v /mnt/log/access.log:/var/log/apache2/access.log \
  -p 8080:80 linkerlab/awstats
```

In this command, you will also run your server into host port 8080.

## Run with your own config

```
docker run -d --name awstats --hostname ServerName \
  -v /mnt/log/access.log:/var/log/apache2/access.log \
  -v /path/to/your.conf:/usr/lib/cgi-bin/awstats/awstats.linoxide.conf && \
  -p 8080:80 linkerlab/awstats
```

## Browse

```
http://your-awstats-ip-addr:8080/cgi-bin/awstats/awstats.pl?config=linoxide
```

