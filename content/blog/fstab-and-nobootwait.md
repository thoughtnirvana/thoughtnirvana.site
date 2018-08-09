+++
title = "/etc/fstab and nobootwait"
author = "Rahul Kumar"
date = "2013-12-17T13:50:46+02:00"
tags = ["ec2", "ubuntu", "devops", "linux"]
categories = ["linux", "devops"]
+++

Do you know what “nobootwait” does in the following line?

```
/dev/xvdb       /mnt    auto    defaults,nobootwait,comment=cloudconfig 0       2
```

I learnt it the hard way. I had an ubuntu ec2 instance where I added a line to mount an ebs instance. I didn’t know what nobootwait does and I just went with defaults. I don’t exactly recall what happened, but the /dev/whatever I had in /etc/fstab wasn’t found when I rebooted the instance, and ubuntu helpfully stuck to the “manually mount or skip” screen. Except that there is no way to do that while you are booting an ec2 instance.