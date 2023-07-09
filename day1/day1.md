## Day1
#### As a devops/sys admin, we need to work with the ```os``` module a lot

The ```os``` module provides a portable way of using operating system-dependent functionality. In addition, it allows us to interact with the underlying operating system in different ways to **automate tasks** (e.g., creating/removing directories, check if the file/directory exists, etc.).


- To print the current working directory, use os.getcwd(). This is similar to pwd command in Linux.
```
>>> os.getcwd()
'/home/paarth/.vscode'
```

- To change path/current working directory os.chdir(< directory to change >). This is similar to the cd command in Linux.
```
os.chdir(<directory to change>)
>>> os.chdir("/tmp")# To verify your path now
>>> os.getcwd()
'/tmp'
```

- To print/list files in the current directory(it return a list) use os.listdir() . It’s similar to the ls -l command in Linux.
```
$ ls -ltr
-rw-rw-r--. 1 cloud_user cloud_user       0 Mar  8  2019 secret.txt
-rw-rw-r--. 1 cloud_user cloud_user       0 Mar  8  2019 reports.csv
-rw-rw-r--. 1 cloud_user cloud_user       0 Mar  8  2019 Junk.txt
-rw-rw-r--. 1 cloud_user cloud_user       0 Mar  8  2019 code_ideas.odt>>> os.listdir()
['aristotle_politics.txt', 'cicero_disputations.txt', 'plato_republic.txt', 'secret.txt', 'Junk.txt', 'code_ideas.odt', 'reports.csv']

```
>***NOTE:*** If you are not providing any path, it will take the current directory. But you can always pass the path as an input, e.g.,/etc. In this case.

```
>>> os.listdir(path)>>> os.listdir("/etc")
['fonts', 'crypttab', 'mtab', 'pki', 'rpm', 'yum.repos.d', 'yum', 'libuser.conf', 'audit', 'centos-release', 'rsyslog.d', 'issue', 'binfmt.d', 'issue.net', 'modules-load.d', 'os-release', 'security', 'tuned', 'redhat-release', 'DIR_COLORS', 'vimrc', 'system-release', 'sestatus.conf', 'fstab', 'system-release-cpe', 'tmpfiles.d', 'aliases', 'rc.local', 'bashrc', 'systemd', 'csh.cshrc', 'udev', 'csh.login', 'machine-id', 'environment', 'NetworkManager', 'exports', 'nsswitch.conf.bak', 'filesystems', 'inittab', 'group', 'adjtime', 'gshadow', 'networks', 'host.conf', 'cron.monthly', 'hosts', 'shadow-', 'hosts.allow', 'ppp', 'gconf', 'hosts.deny', 'rwtab', 'pulse', 'inputrc', 'nfsmount.conf', 'motd', 'rwtab.d', 'passwd', 'statetab', 'printcap', 'statetab.d', 'profile', 'profile.d', 'sysctl.conf', 'protocols', 'cron.hourly', 'securetty', 'cron.weekly', 'services', 'anacrontab', 'shadow', 'crontab', 'shells', 'X11', 'bash_completion.d', 'opt', 'pm', 'skel', 'sysconfig', 'xdg', 'xinetd.d', 'terminfo', 'default', 'polkit-1', 'ld.so.conf', 'ld.so.conf.d', 'my.cnf', 'nsswitch.conf', 'passwd-', 'dconf', 'rpc', 'cloud', 'ld.so.cache', 'ssh', 'man_db.conf', 'libaudit.conf', 'popt.d', 'alternatives', 'chkconfig.d', 'gnupg', 'avahi', 'init.d', 'rc.d', 'cron.d', 'rc0.d', 'cron.deny', 'rc1.d', 'grub.d', 'rc2.d', 'dnsmasq.conf', 'rc3.d', 'dnsmasq.d', 'rc4.d', 'updatedb.conf', 'rc5.d', 'dracut.conf', 'rc6.d', 'aliases.db', 'GREP_COLORS', 'libnl', 'gcrypt', 'pkcs11', 'wpa_supplicant', 'magic', 'sasl2', 'groff', 'ssl', 'dbus-1', 'samba', 'request-key.conf', 'request-key.d', 'kernel', 'virc', 'iproute2', 'selinux', 'gss', 'dracut.conf.d', 'krb5.conf', 'openldap', 'DIR_COLORS.256color', 'idmapd.conf', 'grub2.cfg', 'DIR_COLORS.lightbgcolor', 'rsyslog.conf', 'login.defs', 'pam.d', '.pwd.lock', 'logrotate.d', 'my.cnf.d', 'prelink.conf.d', 'sgml', 'group-', 'gshadow-', 'sysctl.d', 'yum.conf', 'netconfig', 'dhcp', 'xml', 'e2fsck.conf', 'exports.d', 'mke2fs.conf', 'depmod.d', 'modprobe.d', 'cron.daily', 'logrotate.conf', 'favicon.png', 'kdump.conf', 'makedumpfile.conf.sample', 'firewalld', 'audisp', 'postfix', 'chrony.conf', 'chrony.keys', 'rsyncd.conf', 'sudo-ldap.conf', 'sudo.conf', 'sudoers', 'sudoers.d', 'vconsole.conf', 'localtime', 'locale.conf', 'hostname', 'resolv.conf', 'grub.conf', 'plymouth', 'asound.conf', 'oddjob', 'oddjobd.conf', 'oddjobd.conf.d', 'gtk-2.0', 'libreport', 'UPower', 'udisks2', 'gdm', 'nanorc', 'wgetrc', 'mime.types', 'mailcap', 'ghostscript', 'centos-release-upstream', 'tcsd.conf', 'gssproxy', 'python', 'geoclue', 'la_version', '.updated', 'xrdp', 'amazon', 'init', 'subgid', 'subuid', 'nsswitch.conf.rpmnew', 'krb5.conf.d', 'GeoIP.conf', 'bluetooth', 'sysctl.conf.rpmnew', 'iscsi', 'chrony.keys.rpmnew', 'nfs.conf', 'kernel-reinstall-count', 'zprofile', 'bash.bashrc', 'rvmrc', 'libblockdev', 'multipath', 'lvm', 'trusted-key.key', 'glvnd', 'fuse.conf', 'egl', 'flatpak', 'libpaper.d', 'papersize', 'ImageMagick-6']
```

- To create a file, use os.mknod().
``` 
# To create a fileos.mknod(<file name>)>>> os.mknod("testfile")# Verify it
>>> os.listdir()
['aristotle_politics.txt', 'cicero_disputations.txt', 'plato_republic.txt', 'secret.txt', 'Junk.txt', 'code_ideas.odt', 'reports.csv', 'testfile']
```
   
-  To create a directory os.mkdir().
```
# To create a directoryos.mkdir(<directory name>)>>> os.mkdir("mytest")# To verify it
>>> os.listdir()
['aristotle_politics.txt', 'cicero_disputations.txt', 'plato_republic.txt', 'secret.txt', 'Junk.txt', 'code_ideas.odt', 'reports.csv', 'mytest']

```
But now, let say we want to go one level deep, i.e., both test3 and test4 don’t exist; if we are trying to create a directory recursively, it will not work; to do that, we need to use os.makedirs().

```
>>> os.mkdir("test3/test4")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
FileNotFoundError: [Errno 2] No such file or directory: 'test3/test4'>>> os.makedirs("test3/test4")
```

- To print, all the environment variables use os.environ. This is similar to the env command in Linux.

```
$ env
XDG_SESSION_ID=9
rvm_bin_path=/usr/local/rvm/bin
HOSTNAME=cddebed89c1c.mylabserver.com
GEM_HOME=/usr/local/rvm/gems/ruby-2.4.1
TERM=xterm-256color
SHELL=/bin/bash
HISTSIZE=100000
IRBRC=/usr/local/rvm/rubies/ruby-2.4.1/.irbrc
OLDPWD=/home/cloud_user
MY_RUBY_HOME=/usr/local/rvm/rubies/ruby-2.4.1
USER=cloud_user

_system_type=Linux
rvm_path=/usr/local/rvm
rvm_prefix=/usr/local
MAIL=/var/spool/mail/cloud_user
PATH=/usr/local/rvm/gems/ruby-2.4.1/bin:/usr/local/rvm/gems/ruby-2.4.1@global/bin:/usr/local/rvm/rubies/ruby-2.4.1/bin:/usr/local/bin:/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/usr/local/rvm/bin:/home/cloud_user/.local/bin:/home/cloud_user/bin
PWD=/home/cloud_user/Documents
LANG=en_US.UTF-8
_system_arch=x86_64
_system_version=7
HISTCONTROL=ignoredups
rvm_version=1.29.3 (latest)
SHLVL=1
HOME=/home/cloud_user
LOGNAME=cloud_user
GEM_PATH=/usr/local/rvm/gems/ruby-2.4.1:/usr/local/rvm/gems/ruby-2.4.1@global
XDG_DATA_DIRS=/home/cloud_user/.local/share/flatpak/exports/share:/var/lib/flatpak/exports/share:/usr/local/share:/usr/share
LESSOPEN=||/usr/bin/lesspipe.sh %s
XDG_RUNTIME_DIR=/run/user/1002
RUBY_VERSION=ruby-2.4.1
_system_name=CentOS
_=/bin/env>>> os.environ
environ({'XDG_SESSION_ID': '9', 'rvm_bin_path': '/usr/local/rvm/bin', 'HOSTNAME': 'cddebed89c1c.mylabserver.com', 'GEM_HOME': '/usr/local/rvm/gems/ruby-2.4.1', 'TERM': 'xterm-256color', 'SHELL': '/bin/bash', 'HISTSIZE': '100000', 'IRBRC': '/usr/local/rvm/rubies/ruby-2.4.1/.irbrc', 'OLDPWD': '/home/cloud_user', 'MY_RUBY_HOME': '/usr/local/rvm/rubies/ruby-2.4.1', 'USER': 'cloud_user', 'LS_COLORS': ,'_system_type': 'Linux', 'rvm_path': '/usr/local/rvm', 'rvm_prefix': '/usr/local', 'MAIL': '/var/spool/mail/cloud_user', 'PATH': '/usr/local/rvm/gems/ruby-2.4.1/bin:/usr/local/rvm/gems/ruby-2.4.1@global/bin:/usr/local/rvm/rubies/ruby-2.4.1/bin:/usr/local/bin:/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/usr/local/rvm/bin:/home/cloud_user/.local/bin:/home/cloud_user/bin', 'PWD': '/home/cloud_user/Documents', 'LANG': 'en_US.UTF-8', '_system_arch': 'x86_64', '_system_version': '7', 'HISTCONTROL': 'ignoredups', 'rvm_version': '1.29.3 (latest)', 'SHLVL': '1', 'HOME': '/home/cloud_user', 'LOGNAME': 'cloud_user', 'GEM_PATH': '/usr/local/rvm/gems/ruby-2.4.1:/usr/local/rvm/gems/ruby-2.4.1@global', 'XDG_DATA_DIRS': '/home/cloud_user/.local/share/flatpak/exports/share:/var/lib/flatpak/exports/share:/usr/local/share:/usr/share', 'LESSOPEN': '||/usr/bin/lesspipe.sh %s', 'XDG_RUNTIME_DIR': '/run/user/1002', 'RUBY_VERSION': 'ruby-2.4.1', '_system_name': 'CentOS', '_': '/bin/python3'})
```

- If we are looking for any specific environment variable, os.environ.get(< variable name >)

```
>>> os.environ.get('LOGNAME')
'cloud_user'
```

- To get the userid use os.getuid() or group id use os.getgid(). It’s similar to the id command in Linux.

```
$ id
uid=1002(cloud_user) gid=1003(cloud_user) groups=1003(cloud_user),10(wheel)>>> os.getuid()
1002
>>> os.getgid()
1003
```

- Remove directory or remove directory recursively use os.rmdir() or remove directory recursively use os.removedirs().

```
>>> os.rmdir("mytest")>>> os.removedirs("test3/test4")
```

- To rename a file use os.rename()

```
# To rename a fileos.rename(< file to rename>, <destination file name >)
>>> os.rename("testfile","testfile1")>>> os.listdir()
['aristotle_politics.txt', 'cicero_disputations.txt', 'plato_republic.txt', 'secret.txt', 'Junk.txt', 'code_ideas.odt', 'reports.csv', 'testfile1']
```

###OS.path

OS Path module is a submodule of os and provides useful functions on pathnames.

- To get the base name or the final component of a pathname, use os.path.basename().

```
>>> os.path.basename("/home/centos")
'centos'
```

- To get the directory component of a pathname os.path.dirname().

```
>>> os.path.dirname("/home/centos")
'/home'
```

- To join two paths together, use os.path.join().

```
>>> a = os.path.join(“/tmp”, “testhome”)
>>> print(a)
/tmp/testhome
```

- To split the pathname path into a pair, (head, tail) where the tail is the last pathname component and the head is everything leading up to that os.path.split().
```
>>> os.path.split("/etc/tuned/recommend.d")
('/etc/tuned', 'recommend.d')
```

- To return the size, in bytes, of the path os.path.getsize().
```
>>> os.path.getsize("/etc/hosts")
235
```

- To check if the path exists use os.path.exists(). It will return True if the path exists and False if it’s not.
```
>>> os.path.exists("/etc/hosts")
True
>>> os.path.exists("/etc/hostsss")
False
```

- In the same way, you can check the presence of file/directory os.path.isfile(). It will return True if the path exists and False if it’s not.
```
>>> os.path.isfile("/etc/hosts")
True
>>> os.path.isfile("/etc")
False
>>> os.path.isdir("/etc")
True
```


- To check if the given path is a symbolic link, use os.path.islink(). It will return True if the path exists and False if it’s not.
```
>>> os.path.islink("/etc/rc0.d")
True
```


###OS.system

os.system is used to execute operating system commands. Think of it if you want to list a directory, you can use the (os.listdir() command), but you don’t want to memorize functionality provided by the os module and want to use the existing Linux command, you can use the os.system(). The other advantage is if you look at the command output, it returns exit code; if the command executed successfully is zero(0) or non-zero if the command doesn’t execute successfully.

```
>>> os.system("ls")
Desktop  Documents
0
```

>***NOTE:***  You can’t store the command’s output executed by the os.system(). The only thing you can store is the return code. However, as you can see in the below code, it only stores the return code and the ls command output. If you want to store the output of the ls command, you need to use the subprocess module.

```
>>> rt=os.system("ls")
Desktop  Documents
>>> print(rt)
0
```

>***NOTE:*** os.system (which is just a thin wrapper around the POSIX system call) runs the command in a shell launched as a child of the current process

###OS.walk

- To print the directory tree and all the files within that directory tree, we can use os. walk, which is a generator and has a tuple of 3 values
    - directories(dirpath)(The path you have given)
    - directories within that path(dirname)
    - files within that path

```
>>> import os
>>> os.walk("/etc/tuned")
<generator object walk at 0x7f786ea508e0>>>> list(os.walk("/etc/tuned"))
[('/etc/tuned', ['recommend.d'], ['active_profile', 'tuned-main.conf', 'bootcmdline', 'profile_mode']), ('/etc/tuned/recommend.d', [], [])] 
```

Now compare this with the output of ```ls -lR```

```
$ ls -lR /etc/tuned/
/etc/tuned/:
total 16
-rw-r--r--. 1 root root   14 Jun 24 16:11 active_profile
-rw-r--r--. 1 root root 1111 Mar 21  2019 bootcmdline
-rw-r--r--. 1 root root    7 Jun 24 16:11 profile_mode
drwxr-xr-x. 2 root root    6 Feb  2 16:30 recommend.d
-rw-r--r--. 1 root root 1305 Feb  2 16:30 tuned-main.conf/etc/tuned/recommend.d:
total 0
```

OR we can execute this command.

```
>>> for dirname, dirpath, filename in os.walk("/etc/tuned"):
...     print(dirname)
...     print(dirpath)
...     print(filename)
... 
/etc/tuned
['recommend.d']
['active_profile', 'tuned-main.conf', 'bootcmdline', 'profile_mode']
/etc/tuned/recommend.d
```
