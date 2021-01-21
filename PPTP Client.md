## һ��Windows 10�ͻ���
#### 1.1 ������ > �����INTERNET > VPN > ���VPN����

![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/1.png)
#### 1.2 ��д VPN��Ϣ�������

![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/2.png)
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/3.png)
#### 1.3 �Ҽ�����VPN�������
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/4.png)
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/5.png)
## ����Ubuntu / Linux�ͻ���
#### 2.1 ��װpptp�ͻ���
```
sudo apt-get install pptp-linux
```
#### 2.2 ��ʼ��һ������ͨ����mypptp
- mypptp����ͨ������
- `xxx.xxx.xxx.xxx`��pptp����˵�ip��ַ ����ʵ�������д
- �û����������ɷ�����ṩ
```
sudo pptpsetup --create mypptp --server xxx.xxx.xxx.xxx --username �û��� --password ���� --encrypt --start
```
#### 2.3 ָ��ִ�гɹ����ʾ��
```
Using interface ppp0
Connect: ppp0 <--> /dev/pts/2

CHAP authentication succeeded
MPPE 128-bit stateless compression enabled
local  IP address 192.168.0.234
remote IP address 192.168.0.1
```
#### 2.4 �鿴�����Ƿ�ɹ�
```
ip addr show
```
## ���������Ų�
#### 3.1 Windows 10 ����VPN���޷�������
###### 3.1.1 �򿪿������ > �����Internet > ����͹������� > �����������������
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/6.png)

###### 3.1.2 ѡ��VPN > �Ҽ� > ����
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/7.png)
###### 3.1.3 ������Զ��������ʹ��Ĭ�����ء�ȡ�������������
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/8.png)
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/9.png)
###### 3.1.4  ��VPN���ý���Ͽ����Ӻ��������Ϳ�����
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/10.png)
#### 3.2 Windows 10 ����VPN���޷����������ҵ�������޷�����
###### 3.2.1  �ҵ�rasphone.pbk�ļ��ü��±��򿪣��ļ�·������
- �ڴ�֮ǰһ��Ҫ��`��ʾ�����ļ�`����Ȼ���Ҳ�����
- ·���е�Mr.zhangΪ�Լ����Ե��û���
-  `����ж��VPN���ü��±���ÿ��VPN������VPN���֣�ȷ��`
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/11.png)
###### 3.2.2  ����`IpPrioritizeRemote`�ؼ��֣�Ĭ��Ϊ1����Ϊ0�����漴��
![���������ͼƬ����](https://raw.githubusercontent.com/zhangyunxin1/PPTP-/main/images/12.png)
#### 3.3 Ubuntu / Linux�ͻ����޷�pingͨ�����ͻ���
###### 3.3.1 ���·��
- `192.168.0.0/24`��Ҫ����ʵ�ʵ�`ppp0` ip��ȷ������������ppp0��ip��192.168.0.234
```
route add -net 192.168.0.0/24  dev ppp0
```
###### 3.3.2 ���·�ɳ���������������
- ɾ��·��
```
route del -net 192.168.0.0/24  dev ppp0
```
