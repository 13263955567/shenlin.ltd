��Linux�������̡�

    �̼�Firmware(CMOS/BIOS)->ִ��POST(Power On Self Test)�ӵ��Լ�->��ȡMBR->�Ծٳ���BootLoader(GRUB)->�����ں�->�ں�Kernel->����Ӳ��

                                                                                                                          ->��������init->��ȡ��ִ�������ļ�/etc/inittab


    init�Ĺ�����

        init�������ȡinittab�ļ���ִ��ȱʡ���м��𣬴Ӷ������������̡�

        ��UNIXϵͳ�У�init�ǵ�һ�����Դ��ڵĽ��̣�����PID��Ϊ1������Ҳ������һ�����߼��Ĺ��ܸ���PIDΪ0���ں˵�������Kernel Scheduler�����Ӷ����CPUʱ�� 

    �ں˵��������������CPUʱ��ͽ��̼��л���

    ���ӽ��̣�linux�У���������ֹ���ӽ���Ҳ���뱻��ֹ���������̱���ֹ�����ӽ���������ԭ��û����ֹ�����ӽ��̱���Ϊ�¶����̣�linux��⵽�¶����̺󣬻Ὣ�¶����̵ĸ�����ָ��init���̣�

              ���ӽ��̱���ֹ�󣬸�����û�˽⵽����Ϣ�������Ժ��ӽ���ȡ����ϵ������ӽ��̳�Ϊ��ʬ���̣�linux����Z��Zombie����ʾ��

    MBR��Mater Boot Record ��������¼��λ��0����0��ͷ1����

         MBR��512���ֽ�

             Boot Loader ��446bytes�� �Ծٳ���

             Partition Table ��64bytes�� ������

                   partition1 
                   partition2 
                   partition3 
                   partition4 

             Magic Number��2bytes�� ������־��

    �̼����������Ӳ��֮��

    �̼��ĳ������ã�

        ��ȫ���ã�������BIOS����

        �������Ľ����б�

        ���������ʵ�����˳��

        ��Դ����

        ����ϸ����ʾ

        ��������

    BIOSʱ��

        Ӳ��ʱ�ӣ�linux�г�Ϊhardware clock��ʹ������hwclock�鿴

        ����Ӳ��ʱ��ʱ�䣺hwclock --set --date="9/22/96 16:45:05"

    ���ʱ��

        linuxϵͳ��ʱ�ӣ�ʹ��date����鿴

        �������ʱ��ʱ�䣺date MMDDhhmm[[CC]YY][.ss]����ʽ�� ��������ʱʱ�ַ���������.����

                          date 030821192014.30

    ���ʱ�Ӻ�Ӳ��ʱ�ӵ�ͬ��

        ����ʱ��ͬ������Ҫ��һЩ��Ӧ�ó����ڵ���ʱ��ֵʱ��ʱ�Ӳ�ͬ�����޷��������У�����ʾTime Error

                            һЩ��Ӧ�ó����ʱ���кܸߵ�Ҫ�������绷����ʵ��ͬ�������籸�ݣ���ʱ��Ҫ����������������ʱ����һ�µ�

        ͬ�����hwclock --hctosys         hardware clock to sys����Ӳ��ʱ��ͬ����ϵͳ

                  hwclock --systohc         sys clock to haredware����ϵͳʱ��ͬ����Ӳ��

        NTP��Network Time Protocal�����񣬶��ں�ʵ�ʷ�����ͬ��???

��Linux���м���

    ��/etc/inittab�����ļ�������linux�����м���init���̽���ȡinittab�����ļ�������ϵͳ�������趨�ļ����ϡ�

    ��7������0 - halt
                    ���𣨹ػ�???�ô�???������Ҫ��Ĭ�ϵ����м�����Ϊ��ֵ

               1 - Single user mode
                    ���û�ģʽ��������windows�İ�ȫģʽ��ֻ��root���Ե�¼���ô�дS��ʾ

               2 - Multiuser,without NFS
                    ���û�ģʽ��û��NFS�������ʹ������ͺ�3һ��

                    NFS��Network File System�������ļ�ϵͳ��sun��˾�����ķ�������Unix��Linux֮����ļ������򵥵���ȫ�Բʹ�ý���

               3 - Full multiuser mode
                    �����Ķ��û�ģʽ

               4 - unused
                    û��ʹ�ã������Լ���������м��𣬿��Զ���������Щ������

               5 - X11
                    X11��X Window�İ汾�ţ�ͼ�λ��Ķ��û�������

               6 - reboot
                    ��������Ҫ��Ĭ�ϵ����м�����Ϊ��ֵ

               ???ϵͳ��Ĭ�ϼ���

    �鿴��ǰ�����м���runlevel

                ��ʾN 3��N��ʾû���л������м���???

                ��ʾS 3��S��ʾ�л������м���???

    �л����м���init [0123456Ss]

                  telinit [0123456Ss]

                  telinit��init��������

    ��inittab�У�������Ŀ��ȡ���¸�ʽ��

        id:runlevels:action:process

            id����Ŀ�ı�ʶ����1��4λ�ַ�

            run-levels��ָ�����м��𣬿���ָ����������Ϊ�գ����Ǳ�ʾ��ִ�У����Ǳ�ʾ��0��6ÿ�����м���Ҫִ��

            action��ָ������״̬��action����ȡֵ��

                        initdefault��ָ��ϵͳȱʡ���������м���

                        sysinit��ϵͳ����ִ��process��ָ��������

                        wait��ִ��process��ָ������������������������������

                        once��ִ��process��ָ����������ȴ������

                        ctrlaltdel������Ctrl+Alt+Delʱִ��processָ��������

                        powerfail�������ֵ�Դ����ʱִ��processָ����������ȴ������

                        powerokwait������Դ�ָ�ʱִ��processָ��������

                        respawn��һ��processָ����������ֹ�����������и�����

            process��ָ��Ҫ���еĳ��������·��


        �Ƚ������һ�У�������ϵͳ����ʱ��Ĭ�����м���

            id:5:initdefault:


��Linux�����������


    �����ű� /etc/rc.d/rc.sysinit

        /etc/inittab��Ϊsi::sysinit:/etc/rc.d/rc.sysinit        

        �ɼ�����״̬Ϊ�գ�˵�������������м��𣬶���ִ��rc.sysinit�����Լ�����Ҫÿ��ϵͳ����ʱ��ִ�еĽű������Ը����ڴ��ļ����ݺ�

        ���ϵͳ���������������ϵͳ�����������ã�����ϵͳʱ�ӣ��������壬�������ļ�ϵͳ������ϵͳ������Ϣ��־�ļ���

    �����ű� /etc/rc.d/rc

        �ж�ϵͳ�����м���������Ӧ���м���Ŀ¼�еķ�����������Ӧ���м���ĳ�ʼ������

    �����ű� /etc/rc.d/rc[0123456].d        /etc/rc[0123456].d���������ӣ���Ϊ�˺�Unix�����ü���

        �ֱ��Ŷ�Ӧ�����м���ķ������ű��ķ������ӣ����ӵ�init.dĿ¼�е���Ӧ�ű���ls -l /etc/rc.d/rc3.dִ�н��������

            K35smb -> ../init.d/smb
            S55sshd - > ../init.d/sshd

        �ļ���ʽ��Ϊ3�����֣�

            ��ͷ��ĸS��K��S��ͷ�ı�ʾ�ڴ����м���ҪStart������K��ͷ�ı�ʾKill�رգ�ע�ⶼ�Ǵ�д����S��ΪСд���������������ô��ص�ر��Լ�����Ҫ�ķ������д˹��ɣ�����Сдs��ͷ�ľͿ����˽⵽ĳ����ȱʡ����ϵͳ�����ģ��Լ�������Ϊ�˲�����

            �м������35,55��ʾ����/�رյ�˳������ԽСԽ��������

            ����ǽű�������


    �����ܽ᣺

    firmware-->BootLoader(λ��MBR��)-->����init����-->��ȡ/etc/inittab�����ļ�-->�ж�ϵͳ��ȱʡ���м���initDefault-->ִ�нű�/etc/rc.d/rc.sysinit��ʼ��ִ�У������м����޹أ�-->ִ�нű�/etc/rc.d/rc���ж�initDefault-->�������м���������ӦĿ¼/etc/rc.d/rc[0123456].d�µ���S��ͷ�Ľű�-->����usrename,password


    tty

        ctrl+alt+[F1--F6]��������Ӧ��6���ն�

        ctrl+alt+F7 �ص�X Window

    /etc/rc.d/init.d        /etc/init.d�Ǵ�Ŀ¼��������Ŀ¼

        ��Ŀ¼�°����������м���ķ������ű�

        linux��װ�ķ���������ű���λ�ڴ�Ŀ¼

        ֱ�����д�Ŀ¼�µĽű����ᵯ��ʹ�÷�������ʾ��Ϣ�����Դ������ֹ������͹رշ���

            /etc/rc.d/init.d/sshd

            Usage��/etc/rc.d/init.d/sshd {start|stop|restart|reload|condrestart|status}

                reload  ��ʾ���¶�ȡ����������ļ�������Ҫ��������

                condrestart ���ȼ������Ƿ������У�����������������û���������κβ���

    ��������������

        ln -s

            ��һ����������ű��ļ��������ӣ��ŵ���Ӧ�����������Ŀ¼�£���

            ln -s /etc/rc.d/init.d/msg.script /etc/rc.d/rc3.d/S100msg.script

        chkconfig

            chkconfig --list

                ��ʾϵͳ���Ѱ�װ�ķ����ȱʡ��״̬

                chkconfig --list httpd  ֻ��ʾhttpd�������Ϣ

            chkconfig --levels servicename on/off
            chkconfig --level servicename on/off

                ������Ϊservicename�ķ��������м���levels����Ϊon/off��һ�����м���ʹ��ѡ��--level�����ʹ��--levels

                chkconfig --levels 2345 httpd on

        ntsysv

            ntsysv --level 3

            �趨���м���3����������ͼ�ν���

        dmesg

            ��������ڼ�Ĵ���

            dmesg | grep hda

            dmesg | grep eth0

                ���û���ҵ��κ���Ϣ��˵���ں�û������������

        ϵͳ��־ /var/log/messages

            grep syslogd /var/log/messages

                ���ϵͳ��־�����ҿ��ܱ�dmesg���Ե�Ӧ�ó������

            /var/log

                ��Ŀ¼��ŵ�����־�ļ�


��GRUB������Ӧ�á�

    
    GRUB��the GRand Unified Bootloader

    GRUB�������ļ�Ĭ��Ϊ/boot/grub/grub.conf    /etc/grub.confΪ�������ļ���������

    ����ѡ�

        default
    
            ����ȱʡ������ϵͳ��0��ʾ��1����1��ʾ��2��������ϵͳ���б���title�˵��������пɿ���

        timeout

            ����ȱʡ�ȴ�ʱ��

        splashimage

            ����GRUB����ͼƬ�����640x480�ķֱ��ʣ�ɫ��14�����ʱ�Կ�����δ���أ��߷ֱ��ʵ�ͼƬ�ᵼ�±������һƬ

            λ��/boot/grub/splash.xpm.gz

        hiddenmenu

            ���ز˵���ɾ����ѡ������ʾ�˵���

        title

            ����˵�������
        
        root

            ����GRUB�ĸ��豸���ں����ڵķ���

        kernel

            �����ں��ļ�����λ��

        initrd

            ������ؾ����ļ�

    GRUB���

        e���༭��ǰ�������˵���

        c������GRUB��������ģʽ

        b��������ǰ�Ĳ˵���

        d��ɾ����ǰ��

        esc������GRUB�����˵����棬ȡ���Ե�ǰ�˵����������κ��޸�


���������Ϸ���������


    Ӧ��1��root�������룬���뵥�û�ģʽ�������룺

            ��������GRUB���棬��e����༭��ģʽ

                            ��ѡ��kernel�У��ٴΰ�e

                            �����µĽ�������һ�е����λ������ո�����м���ı�ţ����ɽ����Ӧ�����м�����ո�1����ո�s����ʾҪ���뵥�û�ģʽ

                            ���س���b���������������úõ����м���

                            �����뵥�û�ģʽ�ǲ���Ҫ�κ����ܵģ�����ϵͳ��passwd root��Ҳ����Ҫ�����뼴�ɸ���

    Ӧ��2������GRUB���룬�����κ��˿ɽ��뵥�û�ģʽ��

        1��ʹ��GRUB�Դ���grub-md5-crypt ���� ��GRUB���������н�����ʹ��md5crypt�õ�MD5���ܵ������ַ�������xxx

        2������GRUB�����ļ�/boot/grub/grub.conf����title��������һ�У�password --md5 xxxxxxxxxx ��xxxΪ����ʹ������õ������룩

        3����������GRUBʱ�������ǰ�e���б༭��������Ҫ�Ȱ�p����������

    Ӧ��3�������ļ�grub.conf���ô����޸�GRUB

        �����������grub���浫û�в˵���ֻʣ��һ��grub>��ʾ��������취��

        1���鿴grub�����õĲ������ҳ�����

            grub>cat /grub/grub.conf

        2��ȷ�ϴ���󣬽�root,kernel,initrd 3������ʹ����ȷ�ķ�ʽִ��һ�飺

            grub>root(hd0,6)

            grub>kernel(hd0,6)/vmlinuz-2.4.18-14 ro root=LABEL=/

            grub>initrd(hd0,6)/initrd-2.4.18-14.img

        3������

            grub>boot

    Ӧ��4��inittab�ļ��𻵻�ʧ������linux rescueģʽ

            1��BIOS����Ϊ������������Linux��װ�̷ŵ�������ʹ�ù���������

            2�����ְ�װ����󣬸�����ʾ��F5������linux rescueģʽ

            3����boot������linux rescue�����س�

            4��ʹ�ñ��ݵ�inittab.bak�޸�

