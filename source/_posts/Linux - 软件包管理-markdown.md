�����������������

 һ��RPM������

    RPM��Read hat Package Manage

    RPM��???

    ��������Ƹ�ʽ

        sudo-1.7.2p1-5.e15.i386.rpm

            sudo    �������

            1.7.2p1 �汾��

            5.e15   ���к�,release

            i386    Ӳ��ƽ̨

    ��װ�����

        rpm -ivh sudo-1.7.2p1-5.e15.i386.rpm
        
        rpm -i install
            -v ��ϸ��Ϣ
            -h ����
            --excludedocs ����װ������е��ĵ��ļ�
            --prefix=PATH ���������װ����PATHָ����·���£��������RPM��װ���Ѱ����˰�װĿ¼��Ϣ��������ı䰲װĿ¼
            --test	  ֻ�԰�װ���в��ԣ�����ʵ�ʰ�װ
            --replacepkgs ������Ѱ�װ�����ǰ�װ
            --replacefiles Ҫ��װ�����������һ���ļ����ڰ�װ���������ʱ����װ�ˣ�����ʾconflicts with file xxx��ʹ�ô�ѡ���滻�ļ�
            --nodeps ��������������������������������ϵǿ�ư�װ�����ܿ�����ȱ��������ϵ�����¿��԰�װ���޷����У�

    ж�����

        �����������������ƣ���ж��ʱʹ�õ������������

        rpm -e sudo

            e��ʾerase

        rpm -e --nodeps samba

            ��������������Ҫж�ص������������ϵ��ж��ʱ�������ʾ��Ϣ��ʹ��--nodeps��ǿ��ж�أ�no dependencies��

    ���������

        rpm
            -Uvh [���������]     Upgrade

    У�������

        rpm -V [�����]     V��ʾVerify

        �������װ��ÿһ���ļ���û���������ģ�����ʾ�κ���Ϣ������

        #rpm -V sudo

        #S.5....T   c /etc/sudoers

            5 �ļ���MD5У��ֵ
            S �ļ���С
            L �����ļ�
            T ���������ʱ��
            D �豸�ļ�
            U �ļ����û�
            G �ļ����û���
            M �ļ���Ȩ��

        md5sum����Ϊ�ļ�����MD5ֵ

            md5sum /etc/services

    �鿴����Ƿ���

        rpm -q samba
                ��ѯsamba����Ƿ��Ѱ�װ

            -qa ��ѯ�����Ѱ�װ�������

                -qa | grep samba
                    ���Һ�samba��ص������Ѱ�װ�����

            -qf [�ļ�·��]  ��ѯ�ļ����������

            -qi [�����]    ��ѯ�Ѱ�װ�����������Ϣ
            -qip [�������] ��ѯ��δ��װ�����������Ϣ,p��ʾpackage

            -ql [�����]    ��ѯ�Ѱ�װ���������ϵͳ�а�װ����Щ���ļ�
            -qlp [�������] ��ѯδ��װ�����������ϵͳ�а�װ��Щ���ļ�

            -qd [�����]    ��ѯ�Ѱ�װ�İ����������ĵ���λ��
            -qdp [�������]    ��ѯδ��װ�İ����������ĵ���λ��

            -qc [�����]    ��ѯ�Ѱ�װ�İ����������ļ���λ��
            -qcp [�������]    ��ѯδ��װ�İ����������ļ���λ��
	

	������ļ���ȡ

		��ѹ�����ļ�����ǰĿ¼
		rpm2cpio initscripts-8.45.30-2.el5.centeros.i386.rpm | cpio -idv

		��ѹָ���ļ�����ǰĿ¼
		rpm2cpio initscripts-8.45.30-2.el5.centeros.i386.rpm | cpio -idv ./etc/ininttab


 ����YUM������

    ����Yum�ĺô���

        RPM��������ϵ�Ƚ��鷳��yum�Զ�����������������ϵ
        ��������������


    YUM������

        yum info [�����]	��ȡ�����Ϣ
        yum install [�����]
        yum update [�����]
        yum remove [�����]	ж�����

        yum list | grep sudo
        yum list | more       �г�yumԴ�ϵ����������
        yum -C search xxx       �ڱ��ػ����в��������Ϣ

        yum check-update    ���ɸ��µ����
        yum check-update    [�����]

        yum makecache           ����yumԴ���������Ϣ������

        yum -help
        man yum

    ����YUMԴ

        1������yumԴ����Ŀ¼
            cd /etc/yum.repos.d

        2������ϵͳ�Դ���yumԴ
            mv CentOS-Base.repo CentOS-Base.repo.bk

        3������163���׵�yumԴ��
            wget http://mirrors.163.com/.help/CentOS6-Base-163.repo

        4������yumԴ��ִ���±��������yum���ã�ʹ����������Ч
            yum makecache

��Դ�������װ��
    
    Դ������й㷺��������
    Դ����������ɰ���Ҫ�޸Ĵ���
    �ܶ�֪����������°汾����Դ������������Ƕ����ư�
	Դ��������в���ע��ƽ̨���ͣ���i386��alpha��
	Դ�����һ��Ϊ.tar.gz��.biz2��ѹ���ļ�
	Դ�������������ư���ר�ŵ�ж�����ж��ʱ�����ж�صĺܸɾ�����������Լ�ָ��Դ������İ�װ·��
	Դ�������װ�����ж�ط������رս��̣�ɾ���������Ŀ¼

    1����ѹ���

        #tar -zxvf proftpd-1.3.3d.tar.gz
        #tar -jxvf proftpd-1.3.3d.tar.bz2
        #cd proftpd-1.3.3d

    2�����ã�configure�ǿ�ִ�еĽű��ļ���λ�ڽ�ѹ��Ŀ¼�ִ�к��ռ�ϵͳ��Ϣ������makefile�ļ���Ϊ�����ı���make��׼��

        #./configure --prefix=/usr/local/proftpd

    3�����룬��Դ�������Ϊ�������ļ�

        #make

    4����װ�����������ļ��������ļ����Ƶ�ָ��Ŀ¼�� 

        #make install

	proftpd���ص�ַ��www.proftpd.org
    vsfptd

��Դ�������ж�ء�

    �ر�����Ľ���

        kill `pgrep proftpd`;

    �������Ŀ¼ɾ��

        rm -rf /usr/local/proftpd

���ű���װ��

    Դ�������װ�ϸ��ӣ�һЩ������������ýű���װ�ķ�ʽ һ��Ϊshell�ű� �� javaScript��д

	Ӧ�þ�����webmin OpenOffice

	#tar-xzvf webmin-1.530.tar.gz
    #cd webmin-1.530
	#vi README
	#./setup.sh

	www.webmin.com

���ű���װ�����ж�ء�

    �ڽ�ѹ��İ�װ����һ����ж�ؽű�

��Զ�̹���

    �����з�ʽ��Putty,secureCRT,XShell

    ͼ�ν��棺Win C,X Manager

    �������webmin

��APT������

    linux����������redhatϵ�� �� debianϵ��

    �����������

        apt-cache search

    �������Ϣ��

        apt-cache show

    ��װ�������

        apt-get install
        apt-get -f install  �޸���װ
        apt-get reinstall

    ɾ����

        apt-get remove
        apt-get -purge remove   ж��ʱ�����������ļ�
        apt-get autoremove  ж��ʱ�Զ����������ϵ

    �������Դ��

        apt-get update

    �����Ѱ�װ����

        apt-get upgrade






