��ѯ�Ƿ�װssh
rpm -qa | grep ssh

����SSH����
service sshd restart

�鿴�Ƿ�����22�˿�
netstat -antp | grep sshd

����ssh���񿪻�����
chkconfig sshd on 


chkconfig
��ѯ������ϵͳ��������м�����Ϣ
ʵ�ʲ���������Щ���ļ��У�/etc/rc[0-6].d


��������ǰ��@���Ǻ�������