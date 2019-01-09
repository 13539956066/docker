#VERSION 0.0.1

# /home/helloword 我的主机目录路径
FROM 1e1148e4cc2c 

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


# 绑定命令 构建
# docker build -t centos7_jdk8_tomcat8 .

# 绑定命令 构建
# docker build -t centos7_jdk8_tomcat8 .

# 执行命令 从新运行给个新名称
# docker run -d -p 8080:8080 --name zhuotomcat8 centos7_jdk8_tomcat8:latest

#  docker run -d -p 8080:8080 -v /home/webapps:/usr/tomcat8/webapps --name mytomcat8 centos7_jdk8_tomcat8:latest


# 参考这 这个mysql 不是用这个的
 