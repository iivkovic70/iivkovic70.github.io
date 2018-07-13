---
layout: post
title:  "How to change Office 365 update path"
date:   2018-07-02 09:22:47 +0200
categories: Microsoft Office 365 O365
---

You have installed Office 365 on number of clients and for some reason you want to change location from which you update your machines

There are at least 3 ways to achieve this

### 1. Running **setup.exe**

### 2. Change through **GPO**

### 3. Changing **REGistry** keys

{% highlight ruby %}
HKLM\SOFTWARE\Microsoft\Office\ClickToRun\Configuration

UpdateUrl = \\yourServer\YourUpdateLocation
{% endhighlight %}
I hope you know how to download update files via ODT but just to make sure what should be in **update** folder.
Inside of that mentioned folder (value) there should be Office folder ... inside of it Data folder and then files v32.cab, then v32_16.something and the folder with 16.0 something name etc. 