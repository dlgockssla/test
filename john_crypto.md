# Cryptogragpy

***

## HEEEEEEERE'S Johnny!

### problem

> Okay, so we found some important looking files on a linux computer. Maybe they can be used to get a password to the process. Connect with `nc 2018shell.picoctf.com 42165`. Files can be found here: [passwd](https://2018shell.picoctf.com/static/0cae99a3ebd7de5e0547e1ff8da980a0/passwd) [shadow](https://2018shell.picoctf.com/static/0cae99a3ebd7de5e0547e1ff8da980a0/shadow).

![image-20190402034607245](/Users/LeeHaeChan/Library/Application Support/typora-user-images/image-20190402034607245.png)

![image-20190402034628823](/Users/LeeHaeChan/Library/Application Support/typora-user-images/image-20190402034628823.png)

* What is passwd & shadow (in Unix)
  - 서버가 사용자의 계정을 검증할 때 /etc/passwd . 나도 있음

![image-20190402052732278](/Users/LeeHaeChan/Library/Application Support/typora-user-images/image-20190402052732278.png)

​	- 서버가 사용자의 비밀번호를 검증할 때 /etc/shadow. 나한테는 없었음

![image-20190402052906628](/Users/LeeHaeChan/Library/Application Support/typora-user-images/image-20190402052906628.png)



### solution

> #### password cracking (with 'John the Ripper' tool)
>
> input
>
> ~~~shell
> $ unshadow passwd shadow > crack.db
> $ john -show crack.db
> ~~~

​		output

> ~~~
> root:password1:0:0:root:/root:/bin/bash
> 
> 1 password hash cracked, 0 left
> ~~~
>
> 



source)

<https://m.blog.naver.com/PostView.nhn?blogId=hacking560&logNo=90182280590&proxyReferer=https%3A%2F%2Fwww.google.com%2F>

<https://www.cyberciti.biz/faq/unix-linux-password-cracking-john-the-ripper/>