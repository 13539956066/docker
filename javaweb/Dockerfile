
#VERSION 0.0.1

#docker.io/centos    7.4.1708            295a0b2bd8ea        2 months ago        197 MB
FROM 295a0b2bd8ea 

MAINTAINER zhuowenxinog "13539956066@163.com"

#切换镜像目录，进入/usr目录
WORKDIR /usr
#在/usr/下创建jdk目录,用来存放jdk文件
RUN mkdir jdk8
#在/usr/下创建tomcat目录，用来存放tomcat
RUN mkdir tomcat8

#将宿主机的jdk目录下的文件拷至镜像的/usr/jdk目录下
ADD jdk8 /usr/jdk8/
#将宿主机的tomcat目录下的文件拷至镜像的/usr/tomcat目录下
ADD tomcat8 /usr/tomcat8/

#设置环境变量
ENV JAVA_HOME=/usr/jdk8
ENV JRE_HOME=$JAVA_HOME/jre
ENV CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib:$CLASSPATH
ENV PATH=/sbin:$JAVA_HOME/bin:$PATH

#公开端口
EXPOSE 8080
#设置启动命令
ENTRYPOINT ["/usr/tomcat8/bin/catalina.sh","run"]
