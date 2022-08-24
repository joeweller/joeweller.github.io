---
layout: post
title: "NGINX : failed (2: No such file or directory) in /etc/nginx/nginx.conf"
date: 2019-07-19 21:39:02 +0000
categories: debug blog
keywords:
  - nginx
  - configuration
  - linux
  - webserver
  - http
  - no such file or directory
  - symbolic links
  - ln -s
  - ls -la
  - server
description: |
  Tips: solve (2: No such file or directory) configuration errors in NGINX
---

My first configuration of an NGINX server left me high and dry for a while. Coming from an Apache back-ground (where everything is done for you), NGINX felt a little archaic at first.
There was not much help out there for this issue so I will fill in the gap.

The error (in this case) was due to my symbolic link not being created correctly in sites-enabled.
I will go into a little more detail.

`nginx: [emerg] open() "/etc/nginx/sites-enabled/mysite.co.uk" failed (2: No such file or directory) in /etc/nginx/nginx.conf:62`

This is the error (above) was being shown with any of the following commands :

Testing the configuration:

- `$ sudo nginx -t`

Starting or reloading the service:

- `$ sudo service nginx restart`
- `$ sudo nginx -s reload`

`nginx: [emerg] open() "/etc/nginx/sites-enabled/mysite.co.uk" failed (2: No such file or directory) in /etc/nginx/nginx.conf:62`

This message is a bit vague, but there is a subtle hint here. The last path is pointing to the file containing the problem and the appended number correlates to the specific line number in that file.

In my case, `line 62` was:
`include /etc/nginx/sites-enabled/\*;`

I know the syntax of the line is correct because I compared it with the default file included in the installation.

Similar to Apache, the `sites-enabled` directory is meant to store symbolic links of configuration files that are stored in `sites-available`.
Unlike Apache, however, the symbolic links need to be manually created by the admin, as apposed to an Apache command that automatically creates and removes the links when asked.

Navigating to `/etc/nginx/sites-enabled`, I checked the symbolic link using the following command

{% highlight console %}
$ sudo ls -la
$ lrwxrwxrwx 1 root root 32 Jul 19 20:16 mysite.co.uk -> sites-available/mysite.co.uk
{% endhighlight %}

I previously created this link whilst in the /etc/nginx folder using the following command:
{% highlight console %}
$ sudo ln -s sites-available/mysite.co.uk sites-enabled/
{% endhighlight %}

Looking back at the ls output, the local filename is correct, however the file path that it is pointing to isn’t.
The correct path should be: `/etc/nginx/sites-available/mysite.co.uk`

The solution was to simply create a new symbolic link to the configuration file, but using absolute paths instead of being lazy.

{% highlight console %}
$ sudo ln -s /etc/nginx/sites-available/mysite.co.uk /etc/nginx/sites-enabled/
{% endhighlight %}

After this, NGINX complained no more and after a silent reload, instantly served my webpage on the World Wide Web. Nice.

Yes, this was complete user-error spurred from my lack of knowledge of symbolic links, however this is no longer a problem and I can get back to development.

Hopefully this will save someone else loads of time!
