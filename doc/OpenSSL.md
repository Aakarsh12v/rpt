������������:
> �Խ�CA-->���ɷ���˺Ϳͻ���˽Կ-->����key����csr�ļ�-->����ca֤��server.csr��client.csr����x509֤��-->��key�ļ�����PKCS#8����

ʵ��Ӧ���У�CA��һ�������������Ǳ��ز��Ծ�û��Ҫȥ��������ģ������Լ�����һ��CA��
> CA ӵ��һ��֤�飨�ں���Կ��˽Կ�������ϵĹ����û�ͨ����֤ CA ��ǩ�ִӶ����� CA ���κ��˶����Եõ� CA ��֤�飨����Կ����������֤����ǩ����֤�顣
����û���õ�һ�������Լ���֤�飬��Ӧ���� CA ������롣�� CA ���������ߵ���ݺ󣬱�Ϊ������һ����Կ������ CA ���ù�Կ�������ߵ������Ϣ����һ�𣬲�Ϊ֮ǩ�ֺ󣬱��γ�֤�鷢�������ߡ�
���һ���û��������һ��֤�����α�������� CA �Ĺ�Կ���Ǹ�֤���ϵ�ǩ�ֽ�����֤��һ����֤ͨ������֤��ͱ���Ϊ����Ч�ġ�֤��ʵ������֤��ǩ֤���أ�CA��ǩ���Ķ��û��Ĺ�Կ����֤��

����CA֮������Ҫ����client��server��֤�飬Ȼ��client��server��֤�鶼���ˣ���������о�ʵ����˫����֤�����ֻ�Ƕ�server���а䷢֤��Ļ����Ǿ��ǵ�����֤��SSL��

## ����OpenSSL
[����Windows��openssl](http://slproweb.com/products/Win32OpenSSL.html) ,��ѹ�ҵ�binĿ¼�е�openssl.exe

## ����CA
```txt
req -new -x509 -keyout ca.key -out ca.crt -days 36500
```
��ʱ��������ļ� ca.key,ca.crt

## ���ɷ���˺Ϳͻ���˽Կ
�����
```txt
genrsa -des3 -out server.key 1024
```
�ͻ���
```txt
genrsa -des3 -out client.key 1024
```

## ����key����csr�ļ�
ע�⣬�������server.csr ���� client.csr��ʾ���󣬹رյ�ǰ���ڣ�Ȼ�����´�openssl.exe����ִ�з����

�����
```txt
req -new -key server.key -out server.csr 
```

�ͻ���
```txt
req -new -key client.key -out client.csr
```

## ����ca֤��server.csr��client.csr����x509֤��
�������û������ ca.key,ca.crt������ͻᱨ����ʾ�Ҳ����ļ�

�����
```txt
x509 -req -days 3650 -in server.csr -CA ca.crt -CAkey ca.key -CAcreateserial -out server.crt
```

�ͻ���
```txt
x509 -req -days 3650 -in client.csr -CA ca.crt -CAkey ca.key -CAcreateserial -out client.crt
```

## ��key�ļ�����PKCS#8����

�����
```txt
pkcs8 -topk8 -in server.key -out pkcs8_server.key -nocrypt
```

�ͻ���
```txt
pkcs8 -topk8 -in client.key -out pkcs8_client.key -nocrypt
```

## ��bin�ļ����£������ļ����Ƴ���
������Ҫע�����sercer�˺�client��ʹ�õ�ca.crtʹ�õ���ͬһ������ζ��ͬһ��CA���а䷢��֤��
```txt
server�ˣ�ca.crt��server.crt��pkcs8_server.key
client�ˣ�ca.crt��client.crt��pkcs8_client.key
```
