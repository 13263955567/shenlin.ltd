NetBios �� SMB����·�ɣ����������ڻ�������

nmbd���̣���������鿴linux������������ļ�
	  ��������ƽ�����ͨ��linux�����������ƶ�����IP������

#ע�͵���˵����Ϣ
;ע�͵���ѡ��

security=ָ����ȫģʽ
	1��share  	��Ȩ����֤
	2��user		ȱʡ�ģ��Ƽ�ʹ�ã���linux��Samba����������֤
	3��server	������������֤��������windows��linux������ʹ��
	4��domain	������������֤��������������windows�������������ʹ��

hosts allow=���������
hosts denny=���Ƶ�����
һ������ǽ�ֹ���ȣ���Samba��������

���Ρ�IP��ַ������

ע������192.168.1.0��samba��дΪ192.168.1.

log file = ��־�ļ�·��

	%mָ���ǽ���������smbd��nmbd

��������޶������֣�
1�������޶�
2���û��޶�


homes��

browseable = no ��Ȩ�޷��ʵ�Ŀ¼���ɼ�����ֻ�ܿ����Լ�������Ŀ¼
writable = no ֻ�� yes �ɶ���д
	Ҳ��дΪwriteable

Linux���ַ���ǽ��
1��Netfilter/Iptables	#iptables -F
2��SELinux		#setsebool -P use_samba_home_dirs on
				      samba_enable_home_dirs 

			 gesebool -a | grep samba

			��ر�SELinux
			 /etc/selinxu/config SELINUX = disabled

iptables -L

�û�������ϵͳ�û�
	apache�п���������û�����Ϊ������ӵ��û���ϵͳ�в�����

����samba��֤����
	smbpasswd -a �û���
		-a��ʾ�������룬û��-a��ʾ�޸�����

����samba

ȷ��smaba�����Ƿ����

samba�鿴���ʵĿͻ�����Ϣ
smbstatus

�鿴��־��Ϣ
cat /var/log/samba


windows�������Ӻ���¼�Ự��
net use

ɾ����������
net use * /delete /y

SSH Secure Shell Client
SSH Secure File Transfer
SecureCRT

-------------------------------------------------------

1��chcon -t samba_share_t /software
2��vi /etc/samba/smb.conf
	д�������ļ�ĩβ

	[������]
	path = ����Ŀ¼��ֻ����һ������Ŀ¼������д�����Ҳ����д�ļ���
	valid users = ָ�����ʹ���Ŀ¼���û�����ָ��������ÿո�ָ�����д��ʾ�����û�
	writable = Ȩ��
3����������
	/etc/rc.d/init.d/smb restart

�û��Ƿ���дȨ�ޣ���Ҫ��
1��samba�Ƿ�����дȨ��
2���û���linuxϵͳ���Ƿ�Թ���Ŀ¼��дȨ��

samba����д���ѡ����ԣ���Ϊû�����ô�ѡ�����ʹ��������������﷨����
testparm
