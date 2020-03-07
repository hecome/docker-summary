FROM centos:7
MAINTAINER He HuiJun

ADD jdk1.8 /usr/local/jdk1.8
ADD entrypoint.sh /entrypoint.sh

ENV  JAVA_HOME=/usr/local/jdk1.8
ENV  PATH  $JAVA_HOME/bin:$PATH
# 修改时区，字符集
RUN yum install kde-l10n-Chinese -y && \
    yum install glibc-common -y && \
    localedef -c -f UTF-8 -i zh_CN zh_CN.utf8 && \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    chmod +x /entrypoint.sh && \
    java -version
ENV LC_ALL zh_CN.utf8

# 添加jar包运行需要的环境

ENTRYPOINT ["/entrypoint.sh"]





