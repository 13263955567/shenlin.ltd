---
title: Linux - HTTPS, SSH, TLS, SSL
categories:
  - Linux
tags:
  - Linux
  - HTTPS
  - SSH
  - TLS
  - SSL
---

��ѯ�Ƿ�װssh
```
rpm -qa | grep ssh
```

����SSH����
```
service sshd restart
```

�鿴�Ƿ�����22�˿�
```
netstat -antp | grep sshd
```

����ssh���񿪻�����
```
chkconfig sshd on 
```

HTTPS=HTTP+SSL/TLS

SSLָ���ǽ���һ��������·�Լ����ʼ�ͨѶ����ʵ�����·�д����������û�б�SSL���ܵġ�
