---
title: Linux - �ļ�ϵͳ����
categories:
  - Linux
tags:
  - Linux
---

Linux �ļ�ϵͳ����

<!--more-->

���ļ�ϵͳ���ɡ�

/usr/bin /bin	��������û�����ִ�е�����
/usr/sbin /sbin ���ֻ��root����ִ�е�����
/home �û�ȱʡ����Ŀ¼
/proc �����ļ�ϵͳ����ŵ�ǰ�ڴ澵��ȱʡ�Ǳ������ڴ澵���еģ�
/dev ����豸�ļ�
/lib ���ϵͳ������������Ĺ����
/lost+found ���һЩ��ϵͳ����ļ����
/tmp �����ʱ�ļ�������Ϊ��
/etc ���ϵͳ�����ļ�������ϵͳʱ��Ҫ����Ŀ¼
/var �������������䶯���ļ������ʼ�����־�ļ����ƻ������
/usr ��������������ֲ�ҳ ������c:\windows
/mnt ��ʱ�ļ�ϵͳ(���̡����̡�u��)�İ�װ��
/boot �ں��ļ����Ծٳ����ļ�����λ�ã�����ϵͳʱ��Ҫ����Ŀ¼
/usr/local ����������װĿ¼��������c��\programe files

df �鿴linnux�ķ������
	-h
	-m
du �鿴�ļ���Ŀ¼��С
	-h
	-s Ŀ¼
fsck e2fsck(file system check) ����޸��ļ�ϵͳ�����û�ģʽִ��
	e2fsck -p �Զ��޸�
	fsck -y �Զ��޸�
file �ж��ļ�����

�豸����
block deivce ���豸������̣����Ϊb
charset device �ַ����豸�����ӡ�������Ϊc

���ع���
mount /dev/cdrom /mnt/cdrom
df
cd /mnt/cdrom
ls /mnt/cdrom

ж�ع���
unmount /mnt/cdrom ��ʱ����ʾ�豸æ���統ǰ��λ��/mnt/cdrom��
��
eject ��ж��ͬʱ�ᵯ���������

�������ʽ��ԭ��

�����Ӳ�̺󣬼���Ƿ���ȷʶ��
dmesg | grep sdb

���ַ���(fdisk)
fdisk -l /dev/sdb �����Ӳ����Ϣ
fdisk /dev/sdb ����
	m ����
	p ��ӡ������
	n ����·���
		e ��չ����
		p �����������4������������ӷ���ʱ����ָ���ļ�ϵͳ���ͣ�Ĭ��Ϊlinux��idΪ83
	t �ı��ļ�ϵͳ����
	d ɾ������
	w ��������д����̱��沢�˳����������򲻻���Ч
	q ��������������˳�

�����ļ�ϵͳ(mkfs)
	mkfs.ext3 /dev/sdb1
���Թ���(mount)
	mkdir /web
	mount /dev/sdb1 /web
д�������ļ�(/etc/fstab)
vi /etc/fstab
---------------------------------------
���������/���	���ص�	�ļ�ϵͳ	ȱʡ����	�Ƿ���(1��/0)		���˳��0�����,1���ȼ��,2���⣩
Label=/		/	ext3		defaults	1			1
/dev/sdb1	/web	ext3		defaults	1			2

e2label /dev/sdb1 apache ���Ӿ��

�������
