---

> http����https����(eg:����֧���ӿڵ���,����΢�Ź��ںŵ���)\
> Զ������(eg:Զ�̰칫)\
> socks5����(eg:�������)\
> ssh����(eg:Զ����������������)

������TCPЭ��֮�ϵ�Э�飺

- HTTPЭ�飺���ı�����Э�飬������ͨ���
- HTTPSЭ�飺��ȫ���ı�����Э�飬����SSL���µ�HTTPЭ��
- FTPЭ�飺�ļ�����Э�飬�����ļ�����
- POP3Э�飺�ʾ�Э�飬���ʼ�ʹ��
- SMTPЭ�飺���ʼ�����Э�飬�������͵����ʼ�
- TelnetЭ�飺Զ�̵�½Э�飬ͨ��һ���ն˵�½������
- SSHЭ�飺��ȫ���Э�飬���ڼ��ܰ�ȫ��½�������ȫ�Բ��TelnetЭ��
- RDPЭ�飺Զ������Э�飬��һ����ͨ����Э�飬���û������ṩ�ն˷���ĵ���
- SOCKSЭ��: ����ǽ��ȫ�Ựת��Э��

![process.png](process.png)

---

## ����

Java����������ⲿ�ļ���classpath���Ӷ�ʵ�ֶ�ȡ�ⲿ�����ļ�

```text
����jar��������ʹ��-Xbootclasspath/a:�������class������ʹ��-cp���

���ַ����ֱ��ǣ�
1. java -Xbootclasspath/a:/etc/hadoop/conf:/etc/hive/conf -jar example.jar
2. java -cp /etc/hadoop/conf:/etc/hive/conf:./example.jar example.Main.class
ע�����
��1��-Xbootclasspath/a:Ҫ��-jar֮ǰ
��2��-Xbootclasspath/a:�ͺ���Ĳ���֮�䲻���пո�
��3��example.Main.class��jar�������࣬Ҫ����Ӧ��jar���ŵ�classpath�����С�
��4���ļ�·��֮��ʹ�÷ָ�����win��Ϊ�ֺţ�linux��Ϊð�ţ�
```

JavafxӲ����Ⱦ���пؼ��������

```text
Javafx���������Ⱦ -Dprism.order=sw
```

## TODO

- [ ] ��Ⱥ��ά�汾
