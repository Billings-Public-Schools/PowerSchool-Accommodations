PowerSchool-Accommodations
==========================

# DEPRICATED - will be moving to an extended schema soon

A simple accommodations screen and alert for admin and teachers.

Installation
------------
The wildcard might conflict with your existing customization. You'll have to merge it in.

In /web_root/admin/students/more2.html you'll need to add a link to the accommodations page. You can restrict who sees the link one of two ways.

 - Add a line that reads as following:

```
~[if.~[f.in;value=~[f.table_info;table=Teachers;*Id=~[x:userid];fn=value;dothisfor=ALL;field=group;fieldtype=INT];in=7,8,9,10,11]=1]<a href="accommodations.html?frn=~(studentfrn)">Accommodations</a><br>[/if]
```
and change the _7,8,9,10,11_ to be a list of the group numbers you want to see the link. (don't forget to keep 9, the administrators group)

 - The other option is to use the same permissions as one of the other default pages. For example, the Special Programs page.

```
~[if.~(studentscreenaccess;specialprograms.html)=1]<a href="accommodations.html?frn=~(studentfrn)">Accommodations</a><br>[/if]
```

Usage
-----
Select a student, click on the accommodations link.

If there is an expiration date or 9/9/9999 the icon will show up on all studnet pages. 9/9/9999 siginifies that the accommodations never expire. In our district, we set this date to be the last day the IEP is in effect.
