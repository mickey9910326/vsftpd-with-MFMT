# vsftpd-with-MFMT

Just let vsftpd support MFMT.

This project make vsftpd supprot "MFMT" command which defined in  
[The "MFMT", "MFCT", and "MFF" Command Extensions for FTP](https://www.ietf.org/archive/id/draft-somers-ftp-mfxx-04.txt).

And the other things is just like vsftpd.

## How do i trust this project

This project is forked from commit c1e4348d2fa5a44d59e62a999bf304361998ae7e in git@salsa.debian.org:mentors.debian.net-team/vsftpd.git

https://salsa.debian.org/mentors.debian.net-team/vsftpd

Use tool to compare it. And install it with source.

```text
curl https://security.appspot.com/downloads/vsftpd-3.0.3.tar.gz --output vsftpd-3.0.3.tar.gz
tar xvf vsftpd-3.0.3.tar.gz
git clone https://github.com/mickey9910326/vsftpd-with-MFMT
diff --brief -r vsftpd-with-MFMT vsftpd-3.0.3
diff -r vsftpd-with-MFMT vsftpd-3.0.3 >> diff.txt
```

```text
Only in vsftp-with-MFMT: .git
Files vsftp-with-MFMT/features.c and vsftpd-3.0.3/features.c differ
Files vsftp-with-MFMT/ftpcodes.h and vsftpd-3.0.3/ftpcodes.h differ
Files vsftp-with-MFMT/postlogin.c and vsftpd-3.0.3/postlogin.c differ
Only in vsftp-with-MFMT: readme.md
```

## Install with source

### 1. backup your vsftpd.conf

```text
cp /etc/vsftpd.conf ~/vsftpd.conf
```

### 2. build and install it

```text
sudo apt-get install dpkg
sudo apt-get install devscripts
sudo apt-get build-dep vsftpd
debuild -b -uc -us
sudo apt-get remove vsftpd
sudo dpkg -i ../vsftpd_3.0.3-9build1_amd64.deb
```

## Dev Note

Here is my developing and code tracing note in chinese.

https://hackmd.io/do9g4_mGQN2EaiJRkhfEIw
