---
title: Linux - �û�����
categories:
  - Linux
tags:
  - Linux
---

Linux �û�����

<!--more-->

## �û����������ļ�

�������ļ���

    �û���Ϣ�ļ���/etc/passwd

    �����ļ���/etc/shadow


    �û����ļ���/etc/group

    �û��������ļ���/etc/gshadow


    ���û���Ĭ�����ã�

        �û������ļ���/etc/login.defs

                        PASS_MIN_LEN    ���볤��Ҫ��
                        
                        UID_MIN         ��СUID
                        UID_MAX         ���UID

                        CREATE_HOME     �Ƿ񴴽�����Ŀ¼

                      /etc/default/useradd

                        GROUP=100
                        HOME=/home
                        INACTIVE=-1         �Ƿ񼤻�
                        EXPIRE=             ����ʱ��
                        SHELL=/bin/bash
                        SKEL=/etc/skel
                        CREATE_MAIL_SPOOL=yes

        ģ�������ļ���λ��/etc/skelĿ¼�£���Ŀ¼�µĶ��������ļ�������ӵ��û�������︴���ļ������û�������Ŀ¼��

    ��¼��Ϣ��/etc/motd

                    message of the day

                    �ɹ���¼֮����ʾ����Ϣ

              /etc/issue

                    �û���¼֮ǰ��ʾ����ʾ��Ϣ��Ĭ��Ϊϵͳ�İ汾��Ӳ��ƽ̨

��/etc/passwd�ļ���ʽ��

    ÿһ�б�ʾһ���û����ж����оͱ�ʾ�ж��ٸ��û���

        $cat /etc/passwd

        root:x:0:0:root:/root:/bin/bash
        bin:x:1:1:bin:/bin:/sbin/nologin
        daemon:x:2:2:daemon:/sbin:/sbin/nologin
        adm:x:3:4:adm:/var/adm:/sbin/nologin
        lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
        sync:x:5:0:sync:/sbin:/bin/sync
        shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
        halt:x:7:0:halt:/sbin:/sbin/halt
        mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
        uucp:x:10:14:uucp:/var/spool/uucp:/sbin/nologin
        operator:x:11:0:operator:/root:/sbin/nologin
        games:x:12:100:games:/usr/games:/sbin/nologin
        gopher:x:13:30:gopher:/var/gopher:/sbin/nologin
        ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin
        nobody:x:99:99:Nobody:/:/sbin/nologin
        vcsa:x:69:69:virtual console memory owner:/dev:/sbin/nologin
        saslauth:x:499:76:Saslauthd user:/var/empty/saslauth:/sbin/nologin
        postfix:x:89:89::/var/spool/postfix:/sbin/nologin
        sshd:x:74:74:Privilege-separated SSH:/var/empty/sshd:/sbin/nologin
        ssy:x:500:500::/home/ssy:/bin/bash
        mysql:x:27:27:MySQL Server:/var/lib/mysql:/bin/false

    ʹ��ð�ŷָ���7�����֣������������ǣ�

        �û���      �û���¼ϵͳʱʹ�õ��û���

        ����        ����λ��ע�ⲻ������

        UID         �û���ʶ��

        GID         ȱʡ���ʶ�ţ�һ���û����������ڶ���飬�������ȱʡ����

        ������Ϣ    �������û�ȫ�����������ţ���Ŀ�����Ϣ

        ����Ŀ¼    �û���¼ϵͳ���ȱʡĿ¼

        Shell       �û�ʹ�õ�Shell��Ĭ��Ϊbash��д�����û����޷���¼ϵͳ

    Ϊʲô������λ��

        ��/etc/passwd�б������û���Ϣ���ܶ�������Ҫ��ȡ��Щ��Ϣ�����Ȩ��������-rw-r--r--���������˶���rȨ�ޣ��������뱣��������κ��˶����Գ����ƽ����룬��ȫ�Բ��á�

        ���ڵ�UNIX����������λ��������ġ�

ͳ������

    wc -l /etc/passwd

��DES��MD5��

    DES

        �ϰ汾��UNIXʹ��DES���ܣ�DESֻ����ǰ8λ

    MD5

        ���볤�Ȳ��̶���������ȹ̶�

        ���򲻿��棬û��ͨ������õ�����

���û����͡�

    Linux�û���Ϊ���֣�

        �����û�    ��root,UID=0��

            ����˵root���ǳ����û�������UIDΪ0���û����ǳ����û�����Ȩ�޺�rootһ����

        α�û�      ��UID 1-499��

        ��ͨ�û�    ��UID 500-60000��

��α�û���

    1��α�û���ϵͳ�ͳ���������

        bin��daemon��shutdown��halt�ȣ��κ�LinuxϵͳĬ�϶�����Щα�û�

        mail��news��games��apache��ftp��mysql��sshd�ȣ���Linuxϵͳ�Ľ������
    
    2��α�û�ͨ������Ҫ���޷���¼ϵͳ

    3������û������Ŀ¼

���û��顿

    ÿ���û�����������һ���û���

    ÿ���û�����԰�������û�

    ͬһ�û�����û����и��鹲�е�Ȩ��

    windows��Ƕ���飬linuxû��

��/etc/shadow�ļ���ʽ��

    root:$6$F7yJ4iBQ$oEGgf0eA2zkGoyx3Ac0ChoJ7HuDiRq5td9rXsGGGybHMNN15uBh8OETOPVRlNDqnkRBWwlcqQT7n5wor0d5b21:17306:0:99999:7:::
    bin:*:17246:0:99999:7:::
    daemon:*:17246:0:99999:7:::
    adm:*:17246:0:99999:7:::
    lp:*:17246:0:99999:7:::
    sync:*:17246:0:99999:7:::
    shutdown:*:17246:0:99999:7:::
    halt:*:17246:0:99999:7:::
    mail:*:17246:0:99999:7:::
    uucp:*:17246:0:99999:7:::
    operator:*:17246:0:99999:7:::
    games:*:17246:0:99999:7:::
    gopher:*:17246:0:99999:7:::
    ftp:*:17246:0:99999:7:::
    nobody:*:17246:0:99999:7:::
    vcsa:!!:17306::::::
    saslauth:!!:17306::::::
    postfix:!!:17306::::::
    sshd:!!:17306::::::
    ssy:$6$DYQuZnbf$MqHan9/bBE0mCkhfxWivu1JeEWYv.NgUaWXQXL/ccBIO7Mkjb2flsv6uCUOAbrlQtfbAISo4gl.EQA0Gohl5m0:17306:0:99999:7:::
    mysql:!!:17308::::::

    ʹ��ð�ŷָ���9�����֣������������ǣ�

        �û���                  �û���¼ϵͳʱʹ�õ��û���

        ����                    ��������

        ���һ���޸�ʱ��        �û����һ���޸��������������linux�ĵ�����1970.1.1Ϊ��׼

        ��Сʱ����            �����޸�����֮�����С������Ĭ��0��ʾ���޶�

        ���ʱ����            ���뱣����Ч�����������Ĭ��Ϊ99999��

        ����ʱ��                ��ϵͳ��ʼ���浽����ʧЧ��������Ĭ��7��

        �˺�����ʱ��            �˺�����ʱ�䣬����������ȡ�û����δ��¼

        ʧЧʱ��                ����ʧЧ�ľ�������

        ��־                    һ�㲻ʹ��

    /etc/shadow�ļ��е����뱻ɾ�������û�����Ҫ�������뼴�ɵ�¼ϵͳ

    /etc/shadow�ļ�Ȩ�ޣ�-r--------����ֻ��root��rȨ�ޣ��Ƚϰ�ȫ

��/etc/passwd��/etc/shadow�е�����ת����

    linux���������룬�����Ƚ�����д��/etc/passwd�е�����λ��Ȼ��ʹ��pwconv���������ת�뵽/etc/shadow�ļ���ϵͳ�Զ���ɴ˹���

    ʹ��pwunconv����ɽ�����ת����������/etc/shadow�ļ�ת��/etc/passwd�ļ�

    pwconv  ��  password convert

��/etc/group�ļ���ʽ��

    root:x:0:
    bin:x:1:bin,daemon
    daemon:x:2:bin,daemon
    sys:x:3:bin,adm
    adm:x:4:adm,daemon
    tty:x:5:
    disk:x:6:
    lp:x:7:daemon
    mem:x:8:
    kmem:x:9:
    wheel:x:10:
    mail:x:12:mail,postfix
    uucp:x:14:
    man:x:15:
    games:x:20:
    gopher:x:30:
    video:x:39:
    dip:x:40:
    ftp:x:50:
    lock:x:54:
    audio:x:63:
    nobody:x:99:
    users:x:100:
    floppy:x:19:
    vcsa:x:69:
    utmp:x:22:
    utempter:x:35:
    cdrom:x:11:
    tape:x:33:
    dialout:x:18:
    saslauth:x:76:
    postdrop:x:90:
    postfix:x:89:
    fuse:x:499:
    sshd:x:74:
    ssy:x:500:
    mysql:x:27:

    ʹ��ð�ŷָ���4�����֣������������ǣ�

        ����                    �û���¼ʱ���ڵ���

        ������                  һ�㲻ʹ��

        GID                     ���ʶ��

        �����û��б�            ���ڸ���������û��б�

��/etc/gshadow�ļ���ʽ��

    root:::
    bin:::bin,daemon
    daemon:::bin,daemon
    sys:::bin,adm
    adm:::adm,daemon
    tty:::
    disk:::
    lp:::daemon
    mem:::
    kmem:::
    wheel:::
    mail:::mail,postfix
    uucp:::
    man:::
    games:::
    gopher:::
    video:::
    dip:::
    ftp:::
    lock:::
    audio:::
    nobody:::
    users:::
    floppy:!::
    vcsa:!::
    utmp:!::
    utempter:!::
    cdrom:!::
    tape:!::
    dialout:!::
    saslauth:!::
    postdrop:!::
    postfix:!::
    fuse:!::
    sshd:!::
    ssy:!::
    mysql:!::

    ʹ��ð�ŷָ���4�����֣������������ǣ�

        ����                    �û���¼ʱ���ڵ���


���ֹ�����û���

    1���ֱ���/etc/passwd��/etc/group��/etc/shadow�ļ������һ�ʼ�¼

    2�������û�����Ŀ¼��������Ŀ¼��������Ϊ��Ӧ�û�

    3�����û�����Ŀ¼������Ĭ�ϵ������ļ�����/etc/skelĿ¼�¸��������ļ�

    4�������û���ʼ����


## �û���������


��SetUID��


����



����


## �û����������


����


����



����


## ��������û�


����


����



����


## �û���Ȩ


����


����



����


