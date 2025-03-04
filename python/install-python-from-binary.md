This doc has commands for installing a Python distribution from binary at RHEL 9.4. In this example, I want to install Python 3.12. 

```shell
sudo dnf install python3.12
```

I tried to choose an specific 3.12 release such as 3.12.6, but dnf didn't support that. I could only chose upto 3.12. 

```
sudo dnf install python3.12
Updating Subscription Management repositories.
Red Hat Enterprise Linux 9 for x86_64 - BaseOS (RPMs)                                      95 kB/s | 4.1 kB     00:00    
Red Hat Enterprise Linux 9 for x86_64 - AppStream (RPMs)                                  104 kB/s | 4.5 kB     00:00    
Dependencies resolved.
==========================================================================================================================
 Package                       Architecture    Version                    Repository                                 Size
==========================================================================================================================
Installing:
 python3.12                    x86_64          3.12.5-2.el9_5.2           rhel-9-for-x86_64-appstream-rpms           29 k
Installing dependencies:
 libnsl2                       x86_64          2.0.0-1.el9                rhel-9-for-x86_64-appstream-rpms           33 k
 mpdecimal                     x86_64          2.5.1-3.el9                rhel-9-for-x86_64-appstream-rpms           88 k
 python3.12-libs               x86_64          3.12.5-2.el9_5.2           rhel-9-for-x86_64-appstream-rpms          9.7 M
 python3.12-pip-wheel          noarch          23.2.1-4.el9               rhel-9-for-x86_64-appstream-rpms          1.5 M

Transaction Summary
==========================================================================================================================
Install  5 Packages

Total download size: 11 M
Installed size: 44 M
Is this ok [y/N]: y
Downloading Packages:
(1/5): libnsl2-2.0.0-1.el9.x86_64.rpm                                                     385 kB/s |  33 kB     00:00    
(2/5): mpdecimal-2.5.1-3.el9.x86_64.rpm                                                   945 kB/s |  88 kB     00:00    
(3/5): python3.12-pip-wheel-23.2.1-4.el9.noarch.rpm                                        11 MB/s | 1.5 MB     00:00    
(4/5): python3.12-3.12.5-2.el9_5.2.x86_64.rpm                                             446 kB/s |  29 kB     00:00    
(5/5): python3.12-libs-3.12.5-2.el9_5.2.x86_64.rpm                                         50 MB/s | 9.7 MB     00:00    
--------------------------------------------------------------------------------------------------------------------------
Total                                                                                      38 MB/s |  11 MB     00:00     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                  1/1 
  Installing       : python3.12-pip-wheel-23.2.1-4.el9.noarch                                                         1/5 
  Installing       : mpdecimal-2.5.1-3.el9.x86_64                                                                     2/5 
  Installing       : libnsl2-2.0.0-1.el9.x86_64                                                                       3/5 
  Installing       : python3.12-3.12.5-2.el9_5.2.x86_64                                                               4/5 
  Installing       : python3.12-libs-3.12.5-2.el9_5.2.x86_64                                                          5/5 
  Running scriptlet: python3.12-libs-3.12.5-2.el9_5.2.x86_64                                                          5/5 
  Verifying        : libnsl2-2.0.0-1.el9.x86_64                                                                       1/5 
  Verifying        : mpdecimal-2.5.1-3.el9.x86_64                                                                     2/5 
  Verifying        : python3.12-pip-wheel-23.2.1-4.el9.noarch                                                         3/5 
  Verifying        : python3.12-3.12.5-2.el9_5.2.x86_64                                                               4/5 
  Verifying        : python3.12-libs-3.12.5-2.el9_5.2.x86_64                                                          5/5 
Installed products updated.

Installed:
  libnsl2-2.0.0-1.el9.x86_64               mpdecimal-2.5.1-3.el9.x86_64              python3.12-3.12.5-2.el9_5.2.x86_64 
  python3.12-libs-3.12.5-2.el9_5.2.x86_64  python3.12-pip-wheel-23.2.1-4.el9.noarch 

Complete!
```
