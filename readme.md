# vsftpd-with-MFMT

Just let vsftpd support MFMT.

This project make vsftpd supprot "MFMT" command which defined in  
[The "MFMT", "MFCT", and "MFF" Command Extensions for FTP](https://www.ietf.org/archive/id/draft-somers-ftp-mfxx-04.txt).

And the other things is just like vsftpd.

## How do i trust this project

This project is forked from commit c1e4348d2fa5a44d59e62a999bf304361998ae7e in git@salsa.debian.org:mentors.debian.net-team/vsftpd.git

https://salsa.debian.org/mentors.debian.net-team/vsftpd

Use git diff to compare it. And install it with source.

```text
git diff c1e4348d2fa5a44d59e62a999bf304361998ae7e
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
git clone https://github.com/mickey9910326/vsftpd-with-MFMT
cd vsftpd-with-MFMT
debuild -b -uc -us
sudo apt-get remove vsftpd
sudo dpkg -i ../vsftpd_3.0.3-12build1_amd64.deb
```

### 3. restore conf and start ftp

```text
sudo ~/vsftpd.conf /etc/vsftpd.conf
sudo systemctl status vsftpd
```

## Dev Note

Here is my developing and code tracing note in chinese.

https://hackmd.io/do9g4_mGQN2EaiJRkhfEIw
