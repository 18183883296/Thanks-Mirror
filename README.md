# Thanks-Mirror

本项目灵感来自：[package-manager-proxy-settings](https://github.com/comwrg/package-manager-proxy-settings)，该项目分享的是包管理器配置代理的方法，这里分享的是包管理器直接可用，质量好，速度快的镜像，以及一些其他常用软件，系统镜像的国内镜像。

在此，对那些提供公共仓库镜像的企业或组织，致以感谢🫡！

Gitee：[https://gitee.com/eryajf/Thanks-Mirror](https://gitee.com/eryajf/Thanks-Mirror)

GitHub：[https://github.com/eryajf/Thanks-Mirror](https://github.com/eryajf/Thanks-Mirror)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**目录**

- [Package-Mirror](#package-mirror)
  - [Go](#go)
  - [Npm](#npm)
  - [Pip](#pip)
  - [Maven](#maven)
  - [Yum](#yum)
  - [Homebrew](#homebrew)
- [Software-Mirror](#software-mirror)
  - [Docker](#docker)
  - [Kubernetes](#kubernetes)
  - [Jenkins](#jenkins)
  - [ElasticSearch](#elasticsearch)
  - [Logstash](#logstash)
  - [Kibana](#kibana)
  - [Filebeat](#filebeat)
  - [MySQL](#mysql)
  - [MariaDB](#mariadb)
  - [MongoDB](#mongodb)
  - [Redis](#redis)
  - [PostgreSQL](#postgresql)
  - [Golang](#golang)
  - [Node](#node)
  - [Python](#python)
  - [Zabbix](#zabbix)
  - [Grafana](#grafana)
  - [Apache](#apache)
  - [Nginx](#nginx)
- [System-Mirror](#system-mirror)
  - [CentOS](#centos)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Package-Mirror

以往工作中经历过建设企业内部私服的经历，私服的建设离不开国内一些优秀的镜像代理，这里记录下来，以供大家参考。

`注意：`假如所有的镜像都已经被本地nexus私服代理，那么对应的地址为`nexus.eryajf.net/repository/***/`。(这只是个域名示例，不代表实际可用！)

### Go

#### Configuration

如果go版本用的`go1.11`或者`go1.12`，需进行如下配置：

```sh
export GO111MODULE=on
export GOPROXY="http://nexus.eryajf.net/repository/go/"
```

如果使用 `go1.13`以上的版本则可以用如下配置：

```sh
export GOPROXY="http://nexus.eryajf.net/repository/go/"
GONOPROXY="gitlab.eryajf.net"
GONOSUMDB="gitlab.eryajf.net"
GOPRIVATE="gitlab.eryajf.net"
GOSUMDB="sum.golang.google.cn"
```

关于如上两个版本配置差异，以及配置参数详解可参考：[https://wiki.eryajf.net/pages/4941.html](https://wiki.eryajf.net/pages/4941.html)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/goproxy/](https://mirrors.aliyun.com/goproxy/)
- Proxy-cn
  - [https://goproxy.cn](https://goproxy.cn)
- Proxy-io
  - [https://proxy.golang.com.cn](https://proxy.golang.com.cn)
- Baidu
  - [https://goproxy.bj.bcebos.com/](https://goproxy.bj.bcebos.com/)
- [Tencent](https://mirrors.cloud.tencent.com/help/go.html)
  - [https://mirrors.cloud.tencent.com/go/](https://mirrors.cloud.tencent.com/go/)
- HUAWEI
  - [https://repo.huaweicloud.com/repository/goproxy/](https://repo.huaweicloud.com/repository/goproxy/)
  

其中`GOSUMDB`在国内可用的两个镜像分别如下：

- Google
  - [https://sum.golang.google.cn/](https://sum.golang.google.cn/)
- sumdb-io
  - [https://gosum.io/](https://gosum.io/)

### Npm

#### Configuration

配置`npm`代理，需进行如下配置：

```
# npm配置
$ echo 'registry=http://nexus.eryajf.net/repository/npm' > ~/.npmrc
# 查看
$ npm config get registry
http://nexus.eryajf.net/repository/npm

# yarn配置
$ echo 'registry "http://nexus.eryajf.net/repository/npm"' > ~/.yarnrc
# 查看
$ yarn config get registry
http://nexus.eryajf.net/repository/npm
```

#### Mirrors

- Taobao

  - [https://registry.npm.taobao.org](https://registry.npm.taobao.org)

    但是请注意如下一个消息：

    - [淘宝 npm 域名即将切换 && npmmirror 重构升级](https://zhuanlan.zhihu.com/p/465424728?spm=a2c6h.24755359.0.0.6d444dccyRLxN8)：即原来的淘宝npm域名将停止解析，因此所有依赖此域名的都需要进行更改。
      - 域名切换规则：
        - [http://npm.taobao.org](http://npm.taobao.org/)=> [http://npmmirror.com](http://npmmirror.com/)
        - [http://registry.npm.taobao.org](http://registry.npm.taobao.org/)=> [http://registry.npmmirror.com](http://registry.npmmirror.com/)

- HUAWEI

  - [https://repo.huaweicloud.com/repository/npm/](https://repo.huaweicloud.com/repository/npm/)

- [Tencent](https://mirrors.cloud.tencent.com/help/npm.html)

  - [http://mirrors.cloud.tencent.com/npm/](http://mirrors.cloud.tencent.com/npm/)

- 浙江大学

  - [http://mirrors.zju.edu.cn/npm/](http://mirrors.zju.edu.cn/npm/)

- 南京邮电

  - [https://mirrors.njupt.edu.cn/nexus/repository/npm/](https://mirrors.njupt.edu.cn/nexus/repository/npm/)

- npmjs

  - https://registry.npmjs.org

### Pip

#### Configuration

配置`Python`代理，需进行如下配置：

```shell
$ mkdir ~/.pip

$ cat > ~/.pip/pip.conf << EOF
[global]
timeout = 60
trusted-host =  nexus.eryajf.net
index-url = http://nexus.eryajf.net/repository/pypi/simple
EOF
```

`注意：`通常在配置文件后边，我们会添加一个`simple`。

#### Mirrors

目前代理外部私仓有：

- Aliyun
  - http://mirrors.aliyun.com/pypi/
- douban
  - http://pypi.douban.com/
- 清华
  - https://pypi.tuna.tsinghua.edu.cn/
- 163
  - [https://mirrors.163.com/pypi](https://mirrors.163.com/pypi)
- HUAWEI
  - [https://repo.huaweicloud.com/repository/pypi](https://repo.huaweicloud.com/repository/pypi)
- Tencent
  - https://mirrors.cloud.tencent.com/pypi/
- 北大
  - [https://mirrors.pku.edu.cn/pypi/](https://mirrors.pku.edu.cn/pypi/)
  
- 南阳理工
  - [https://mirror.nyist.edu.cn/pypi/](https://mirror.nyist.edu.cn/pypi/)

- 大连东软
  - [http://mirrors.neusoft.edu.cn/pypi/web/](http://mirrors.neusoft.edu.cn/pypi/web/)


### Maven

#### Configuration

Java系的工具版本规范如下：

- `JDK：`1.8.0_292
- `MVN：`3.3.9

配置Maven代理，需进行如下配置：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">
  <localRepository>~/.m2/repository</localRepository>
  <pluginGroups>
  </pluginGroups>
  <proxies>
  </proxies>

  <servers>
    <server>
      <id>releases</id>
      <username>username</username>
      <password>password</password>
    </server>
    <server>
      <id>snapshots</id>
      <username>username</username>
      <password>password</password>
   </server>
  </servers>

  <mirrors>
    <mirror>
      <id>nexus-eryajf</id>
      <mirrorOf>*</mirrorOf>
      <name>Nexus osc</name>
      <url>http://nexus.eryajf.net/repository/maven/</url>
    </mirror>
  </mirrors>

  <profiles>
    <profile>
      <id>developer</id>
    <activation>
      <jdk>jdk-1.8</jdk>
    </activation>
    <repositories>
    <repository>
      <id>nexus-eryajf-local</id>
      <name>local private nexus</name>
      <url>http://nexus.eryajf.net/repository/maven/</url>
    <releases>
      <enabled>true</enabled>
    </releases>
    <snapshots>
      <enabled>true</enabled>
      <updatePolicy>always</updatePolicy>
    </snapshots>
    </repository>
    </repositories>
    <pluginRepositories>
    <pluginRepository>
      <id>nexus-eryajf</id>
      <name>local private nexus</name>
      <url>http://nexus.eryajf.net/repository/maven/</url>
    <releases>
      <enabled>true</enabled>
    </releases>
    <snapshots>
      <enabled>true</enabled>
    </snapshots>
    </pluginRepository>
    </pluginRepositories>
    </profile>
  </profiles>

  <activeProfiles>
    <activeProfile>developer</activeProfile>
  </activeProfiles>
</settings>
```

#### Mirrors

- HUAWEI
  - https://repo.huaweicloud.com/repository/maven/

- Maven Central Repository
  - https://repo1.maven.org/maven2/
- [Aliyun](https://developer.aliyun.com/mvn/guide)
  - http://maven.aliyun.com/nexus/content/groups/public/

- Tencent
  - [https://mirrors.cloud.tencent.com/maven/](https://mirrors.cloud.tencent.com/maven/)

- 南京邮电
  - [https://mirrors.njupt.edu.cn/nexus/repository/maven-central](https://mirrors.njupt.edu.cn/nexus/repository/maven-central)

- Apache Maven
  - https://repo.maven.apache.org/maven2
  - https://repository.apache.org/content/groups/snapshots
  - https://repository.apache.org/content/groups/staging/
  - https://repository.apache.org/content/groups/public/

- confluent
  - http://packages.confluent.io/maven/

- cloudera
  - http://repo.hortonworks.com/content/repositories/releases

- jboss
  - https://repository.jboss.org/nexus/content/groups/public

### Yum

#### Configuration

如果`CentOS`服务器要接入私服`yum`源，则清空本地 `/etc/yum.repos.d`的内容，添加如下内容：

```sh
$ cat >> /etc/yum.repos.d/nexus.repo << 'EOF'
[nexus]
name=Nexus Repository
baseurl=http://nexus.eryajf.net/repository/yum/$releasever/os/$basearch/
enabled=1
gpgcheck=0

[nexus-local]
name=Nexus Repository
baseurl=http://nexus.eryajf.net/repository/eryajf-yum-local/
enabled=1
gpgcheck=0
EOF
```

然后执行如下命令：

```sh
yum clean all
yum makecache
```

#### Mirrors

目前代理外部源：

- Aliyun
  - [https://mirrors.aliyun.com/centos/](https://mirrors.aliyun.com/centos/)
- HUAWEI
  - [https://repo.huaweicloud.com/centos/](https://repo.huaweicloud.com/centos/)
- Tencent
  - https://mirrors.cloud.tencent.com/centos/
- 北京交通
  - [https://mirror.bjtu.edu.cn/centos/](https://mirror.bjtu.edu.cn/centos/)
- 东北大学
  - http://mirror.neu.edu.cn/centos/
- 兰州大学
  - https://mirror.lzu.edu.cn/centos/
- 清华
  - https://mirrors.tuna.tsinghua.edu.cn/centos/
- 华中科技大学
  - https://mirrors.ustc.edu.cn/centos/
- 浙江大学
  - http://mirrors.zju.edu.cn/centos/
- souhu
  - http://mirrors.sohu.com/centos/
- 163：
  - http://mirrors.163.com/centos/

### Homebrew

#### Configuration

如果你使用了zsh，那么配置方式如下：

```sh
echo 'export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"' >> ~/.zshrc
echo 'export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"' >> ~/.zshrc
echo 'export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles"' >> ~/.zshrc

source ~/.zshrc
brew update
```

参考：[Homebrew 替换国内镜像源](https://www.frankindev.com/2020/05/15/replace-homebrew-source/)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/homebrew/](https://mirrors.aliyun.com/homebrew/)
- Tencent
  - [https://mirrors.cloud.tencent.com/homebrew/](https://mirrors.cloud.tencent.com/homebrew/)
- 清华：
  - https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/

## Software-Mirror

还有一些软件，直接通过官方下载比较困难，也整理出方便下载的国内优质镜像。

### Docker

#### Official

- https://docs.docker.com/engine/install/

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/docker-ce](https://developer.aliyun.com/mirror/docker-ce)
- Tencent
  - [https://mirrors.cloud.tencent.com/docker-ce/](https://mirrors.cloud.tencent.com/docker-ce/)
- HUAWEI
  - [https://repo.huaweicloud.com/docker-ce/](https://repo.huaweicloud.com/docker-ce/)
- 北大
  - [https://mirrors.pku.edu.cn/docker-ce/](https://mirrors.pku.edu.cn/docker-ce/)
  
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/docker-ce/](https://mirrors.tuna.tsinghua.edu.cn/docker-ce/)
- 中科大
  - [https://mirrors.ustc.edu.cn/docker-ce/](https://mirrors.ustc.edu.cn/docker-ce/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/docker-ce/](https://mirrors.nwsuaf.edu.cn/docker-ce/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/docker-ce/](http://mirrors.zju.edu.cn/docker-ce/)

### Kubernetes

#### Official

- [https://kubernetes.io/releases/download/](https://kubernetes.io/releases/download/)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/kubernetes](https://developer.aliyun.com/mirror/kubernetes)
- Tencent
  - [https://mirrors.cloud.tencent.com/kubernetes/](https://mirrors.cloud.tencent.com/kubernetes/)
- HUAWEI
  - [https://repo.huaweicloud.com/kubernetes/](https://repo.huaweicloud.com/kubernetes/)
- 北大
  - [https://mirrors.pku.edu.cn/kubernetes/](https://mirrors.pku.edu.cn/kubernetes/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/kubernetes/](https://mirrors.tuna.tsinghua.edu.cn/kubernetes/)
- 中科大
  - [https://mirrors.ustc.edu.cn/kubernetes/](https://mirrors.ustc.edu.cn/kubernetes/)

### Jenkins

#### Official

- 安装包：[https://www.jenkins.io/zh/download/](https://www.jenkins.io/zh/download/)
- 插件：[https://plugins.jenkins.io/](https://plugins.jenkins.io/)

#### Mirrors

- Aliyun
  - 安装包：[https://mirrors.aliyun.com/jenkins/war/](https://mirrors.aliyun.com/jenkins/war/)
  - 插件：[https://mirrors.aliyun.com/jenkins/plugins/](https://mirrors.aliyun.com/jenkins/plugins/)
  
- Tencent
  - 安装包：[https://mirrors.cloud.tencent.com/jenkins/war/](https://mirrors.cloud.tencent.com/jenkins/war/)
  - 插件：[https://mirrors.cloud.tencent.com/jenkins/plugins/](https://mirrors.cloud.tencent.com/jenkins/plugins/)
- HUAWEI

  - 安装包：[https://repo.huaweicloud.com/jenkins/war/](https://repo.huaweicloud.com/jenkins/war/)
  - 插件：[https://repo.huaweicloud.com/jenkins/plugins/](https://repo.huaweicloud.com/jenkins/plugins/)
- 中科大
  - 安装包：[https://mirrors.ustc.edu.cn/jenkins/war/](https://mirrors.ustc.edu.cn/jenkins/war/)
  - 插件：[https://mirrors.ustc.edu.cn/jenkins/plugins/](https://mirrors.ustc.edu.cn/jenkins/plugins/)

- 清华
  - 安装包：[https://mirrors.tuna.tsinghua.edu.cn/jenkins/war/](https://mirrors.tuna.tsinghua.edu.cn/jenkins/war/)
  - 插件：[https://mirrors.tuna.tsinghua.edu.cn/jenkins/plugins/](https://mirrors.tuna.tsinghua.edu.cn/jenkins/plugins/)

### GitLab-ce

#### Official

- [https://packages.gitlab.com/gitlab/gitlab-ce](https://packages.gitlab.com/gitlab/gitlab-ce)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/gitlab-ce/](https://mirrors.aliyun.com/gitlab-ce/)
- Tencent
  - [https://mirrors.cloud.tencent.com/gitlab-ce/](https://mirrors.cloud.tencent.com/gitlab-ce/)

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/](https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/)

### GitLab-runner

#### Official

- [https://docs.gitlab.com/runner/install/](https://docs.gitlab.com/runner/install/)

#### Mirrors

- Tencent
  - [https://mirrors.cloud.tencent.com/gitlab-runner/](https://mirrors.cloud.tencent.com/gitlab-runner/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/gitlab-runner/](https://mirrors.tuna.tsinghua.edu.cn/gitlab-runner/)

### ElasticSearch

#### Official

- [https://www.elastic.co/cn/downloads/elasticsearch](https://www.elastic.co/cn/downloads/elasticsearch)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- Aliyun
  - [https://mirrors.aliyun.com/elasticstack/](https://mirrors.aliyun.com/elasticstack/)
  
- HUAWEI
  - [https://repo.huaweicloud.com/elasticsearch/](https://repo.huaweicloud.com/elasticsearch/)
- Tencent
  - [https://mirrors.cloud.tencent.com/elasticstack/](https://mirrors.cloud.tencent.com/elasticstack/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/elasticstack/](https://mirrors.tuna.tsinghua.edu.cn/elasticstack/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/elasticstack/](http://mirrors.njupt.edu.cn/elasticstack/)

### Logstash

#### Official

- [https://www.elastic.co/cn/downloads/logstash](https://www.elastic.co/cn/downloads/logstash)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- HUAWEI
  - [https://repo.huaweicloud.com/logstash/](https://repo.huaweicloud.com/logstash/)


### Kibana

#### Official

- [https://www.elastic.co/cn/downloads/kibana](https://www.elastic.co/cn/downloads/kibana)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- HUAWEI
  - [https://repo.huaweicloud.com/kibana/](https://repo.huaweicloud.com/kibana/)

### Filebeat

#### Official

- [https://www.elastic.co/cn/downloads/beats/filebeat](https://www.elastic.co/cn/downloads/beats/filebeat)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- HUAWEI
  - [https://repo.huaweicloud.com/filebeat/](https://repo.huaweicloud.com/filebeat/)

### MySQL

#### Official

- [https://dev.mysql.com/downloads/repo/yum/](https://dev.mysql.com/downloads/repo/yum/)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/mysql](https://developer.aliyun.com/mirror/mysql)
- HUAWEI
  - [https://repo.huaweicloud.com/mysql/Downloads/](https://repo.huaweicloud.com/mysql/Downloads/)
- Tencent
  - [https://mirrors.cloud.tencent.com/mysql/](https://mirrors.cloud.tencent.com/mysql/)
- Souhu
  - [http://mirrors.sohu.com/mysql/](http://mirrors.sohu.com/mysql/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/mysql/](https://mirrors.tuna.tsinghua.edu.cn/mysql/)
- 中科大
  - [https://mirrors.ustc.edu.cn/mysql-ftp/Downloads/](https://mirrors.ustc.edu.cn/mysql-ftp/Downloads/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/mysql/](https://mirror.nyist.edu.cn/mysql/)

### MariaDB

#### Official

- [https://mariadb.org/download/](https://mariadb.org/download/?spm=a2c6h.13651104.0.0.3b4d3553pZDrq9&t=mariadb&p=mariadb&r=10.6.7)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/mariadb](https://developer.aliyun.com/mirror/mariadb)
- Tencent
  - [https://mirrors.cloud.tencent.com/mariadb/](https://mirrors.cloud.tencent.com/mariadb/)
- HUAWEI
  - [https://repo.huaweicloud.com/mariadb/](https://repo.huaweicloud.com/mariadb/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/mariadb/](https://mirrors.tuna.tsinghua.edu.cn/mariadb/)
- 中科大
  - [https://mirrors.ustc.edu.cn/mariadb/](https://mirrors.ustc.edu.cn/mariadb/)

### Percona

#### Official

- [https://www.percona.com/downloads/](https://www.percona.com/downloads/)

#### Mirrors

- Tencent
  - [https://mirrors.cloud.tencent.com/percona/](https://mirrors.cloud.tencent.com/percona/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/percona/](https://mirrors.tuna.tsinghua.edu.cn/percona/)
- 中科大
  - [https://mirrors.ustc.edu.cn/percona/](https://mirrors.ustc.edu.cn/percona/)

### MongoDB

#### Official

- [https://www.mongodb.com/try/download/community](https://www.mongodb.com/try/download/community)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/mongodb](https://developer.aliyun.com/mirror/mongodb)
- Tencent
  - [https://mirrors.cloud.tencent.com/mongodb/](https://mirrors.cloud.tencent.com/mongodb/)
- 163
  - [http://mirrors.163.com/mongodb/](http://mirrors.163.com/mongodb/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/mongodb/](https://mirrors.tuna.tsinghua.edu.cn/mongodb/)

### Redis

#### Official

- [https://redis.io/download/](https://redis.io/download/)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/redis/](https://repo.huaweicloud.com/redis/)

### PostgreSQL

#### Official

- [https://www.postgresql.org/download/](https://www.postgresql.org/download/)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/postgresql/](https://mirrors.aliyun.com/postgresql/)
  
- Tencen
  - [https://mirrors.cloud.tencent.com/postgresql/](https://mirrors.cloud.tencent.com/postgresql/)
- HUAWEI
  - [https://repo.huaweicloud.com/postgresql/](https://repo.huaweicloud.com/postgresql/)

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/postgresql/](https://mirrors.tuna.tsinghua.edu.cn/postgresql/)

- 中科大
  - [https://mirrors.ustc.edu.cn/postgresql/](https://mirrors.ustc.edu.cn/postgresql/)

- 浙江大学
  - [http://mirrors.zju.edu.cn/postgresql/](http://mirrors.zju.edu.cn/postgresql/)

- 南阳理工
  - [https://mirror.nyist.edu.cn/postgresql/](https://mirror.nyist.edu.cn/postgresql/)


### Golang

#### Official

- [https://go.dev/dl/](https://go.dev/dl/)

#### Mirrors

- Go语言中文网
  - [https://studygolang.com/dl](https://studygolang.com/dl)
- Aliyun
  - [https://mirrors.aliyun.com/golang/](https://mirrors.aliyun.com/golang/)
- Proxy-io
  - [https://gomirrors.org/](https://gomirrors.org/)
- 中科大
  - [https://mirrors.ustc.edu.cn/golang/](https://mirrors.ustc.edu.cn/golang/)

### Node

#### Official

- [https://nodejs.org/zh-cn/download/](https://nodejs.org/zh-cn/download/)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/nodejs-release/](https://mirrors.aliyun.com/nodejs-release/)
- HUAWEI
  - [https://repo.huaweicloud.com/nodejs/](https://repo.huaweicloud.com/nodejs/)
- Tencent
  - [https://mirrors.cloud.tencent.com/nodejs-release/](https://mirrors.cloud.tencent.com/nodejs-release/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/nodejs-release/](https://mirrors.tuna.tsinghua.edu.cn/nodejs-release/)
- 中科大
  - [https://mirrors.ustc.edu.cn/node/](https://mirrors.ustc.edu.cn/node/)

### Python

#### Official

- [https://www.python.org/downloads/](https://www.python.org/downloads/)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/python/](https://repo.huaweicloud.com/python/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/python/](https://mirror.bjtu.edu.cn/python/)
- 中科大
  - [https://mirrors.ustc.edu.cn/node/](https://mirrors.ustc.edu.cn/node/)

### Zabbix

#### Official

- [https://www.zabbix.com/cn/download](https://www.zabbix.com/cn/download)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/zabbix](https://mirrors.aliyun.com/zabbix)
- HUAWEI
  - [https://repo.huaweicloud.com/zabbix/](https://repo.huaweicloud.com/zabbix/)
- Tencent
  - [https://mirrors.cloud.tencent.com/zabbix/](https://mirrors.cloud.tencent.com/zabbix/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/zabbix/](https://mirrors.tuna.tsinghua.edu.cn/zabbix/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/zabbix/](http://mirrors.njupt.edu.cn/zabbix/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/zabbix/](https://mirrors.nwsuaf.edu.cn/zabbix/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/zabbix/](https://mirror.nyist.edu.cn/zabbix/)

### Grafana

#### Official

- [https://grafana.com/grafana/download](https://grafana.com/grafana/download)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/grafana](https://developer.aliyun.com/mirror/grafana)
- HUAWEI
  - [https://repo.huaweicloud.com/grafana/](https://repo.huaweicloud.com/grafana/)
- Tencent
  - [https://mirrors.cloud.tencent.com/grafana/](https://mirrors.cloud.tencent.com/grafana/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/grafana/](https://mirrors.tuna.tsinghua.edu.cn/grafana/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/grafana/](https://mirrors.nwsuaf.edu.cn/grafana/)

### Apache

#### Official

- [https://httpd.apache.org/download.cgi](https://httpd.apache.org/download.cgi)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/apache](https://developer.aliyun.com/mirror/apache)
- HUAWEI
  - [https://repo.huaweicloud.com/apache/](https://repo.huaweicloud.com/apache/)
- Tencent
  - [https://mirrors.cloud.tencent.com/apache/](https://mirrors.cloud.tencent.com/apache/)
- Souhu
  - [http://mirrors.sohu.com/apache/](http://mirrors.sohu.com/apache/)
- 北大
  - [https://mirrors.pku.edu.cn/apache/](https://mirrors.pku.edu.cn/apache/)
  
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/apache/](https://mirrors.tuna.tsinghua.edu.cn/apache/)
- 中科大
  - [https://mirrors.ustc.edu.cn/apache/](https://mirrors.ustc.edu.cn/apache/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/apache/](https://mirror.bjtu.edu.cn/apache/)

### Nginx

#### Official

- [http://nginx.org/en/download.html](http://nginx.org/en/download.html)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/nginx/](https://repo.huaweicloud.com/nginx/)
- Souhu
  - [http://mirrors.sohu.com/nginx](http://mirrors.sohu.com/nginx)
- 中科大
  - [https://mirrors.ustc.edu.cn/nginx/](https://mirrors.ustc.edu.cn/nginx/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/nginx/](https://mirrors.nwsuaf.edu.cn/nginx/)

### OpenResty

#### Official

- [https://openresty.org/cn/download.html](https://openresty.org/cn/download.html)

#### Mirrors

- Tencent
  - [https://mirrors.cloud.tencent.com/openresty/](https://mirrors.cloud.tencent.com/openresty/)
- HUAWEI
  - [https://repo.huaweicloud.com/openresty/](https://repo.huaweicloud.com/openresty/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/openresty/](https://mirrors.tuna.tsinghua.edu.cn/openresty/)
- 中科大
  - [https://mirrors.ustc.edu.cn/openresty/](https://mirrors.ustc.edu.cn/openresty/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/openresty/](https://mirrors.nwsuaf.edu.cn/openresty/)

### Ceph

#### Official

- [https://docs.ceph.com/en/quincy/install/get-packages/](https://docs.ceph.com/en/quincy/install/get-packages/)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/ceph](https://developer.aliyun.com/mirror/ceph)
- Tencent
  - [https://mirrors.cloud.tencent.com/ceph/](https://mirrors.cloud.tencent.com/ceph/)
  
- HUAWEI
  - [https://repo.huaweicloud.com/ceph/](https://repo.huaweicloud.com/ceph/)
- 163
  - [http://mirrors.163.com/ceph/](http://mirrors.163.com/ceph/)

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/ceph/](https://mirrors.tuna.tsinghua.edu.cn/ceph/)

- 重庆大学
  - [https://mirrors.cqu.edu.cn/ceph/](https://mirrors.cqu.edu.cn/ceph/)

- 中科大
  - [https://mirrors.ustc.edu.cn/ceph/](https://mirrors.ustc.edu.cn/ceph/)

## System-Mirror

系统镜像，又大又远，更需要找到好用优秀的国内镜像。

### CentOS

尽管CentOS不再更新了，但它仍旧并且还将持续是国内企业系统主力军。

可能官方考虑到下载困难的问题，官方也列出了距离使用者更近的镜像列表，可谓贴心。

#### Official

- [https://www.centos.org/download/](https://www.centos.org/download/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/centos)
  - [https://mirrors.aliyun.com/centos/](https://mirrors.aliyun.com/centos/)
- Tencent
  - [https://mirrors.cloud.tencent.com/centos/](https://mirrors.cloud.tencent.com/centos/)
- HUAWEI
  - [https://repo.huaweicloud.com/centos/](https://repo.huaweicloud.com/centos/)
- 163
  - [http://mirrors.163.com/centos/](http://mirrors.163.com/centos/)
- Souhu
  - [http://mirrors.sohu.com/centos/](http://mirrors.sohu.com/centos/)
- 北大
  - [https://mirrors.pku.edu.cn/centos/](https://mirrors.pku.edu.cn/centos/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/centos/](https://mirrors.tuna.tsinghua.edu.cn/centos/)
- 中科大
  - [https://mirrors.ustc.edu.cn/centos/](https://mirrors.ustc.edu.cn/centos/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/centos/](http://mirrors.zju.edu.cn/centos/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/centos/](https://mirror.nyist.edu.cn/centos/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/centos/](https://mirror.lzu.edu.cn/centos/)
- 东北大学
  - [http://mirror.neu.edu.cn/centos/](http://mirror.neu.edu.cn/centos/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/centos/](http://mirrors.neusoft.edu.cn/centos/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/centos/](http://ftp.sjtu.edu.cn/centos/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/centos/](https://mirror.bjtu.edu.cn/centos/)
- 大连理工
  - [http://mirror.dlut.edu.cn/centos/](http://mirror.dlut.edu.cn/centos/)
- 首都在线
  - [http://mirrors.yun-idc.com/centos/](http://mirrors.yun-idc.com/centos/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/centos/](http://mirrors.njupt.edu.cn/centos/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/centos/](https://mirrors.nwsuaf.edu.cn/centos/)


### CentOS-altarch

ARM架构下的CentOS镜像。

#### Official

- [https://www.centos.org/download/](https://www.centos.org/download/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/centos-altarch)
  - [https://developer.aliyun.com/mirror/centos-altarch](https://developer.aliyun.com/mirror/centos-altarch)
- Tencent
  - [https://mirrors.cloud.tencent.com/centos-altarch/](https://mirrors.cloud.tencent.com/centos-altarch/)
- HUAWEI
  - [https://repo.huaweicloud.com/centos-altarch/](https://repo.huaweicloud.com/centos-altarch/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/centos-altarch/](https://mirrors.tuna.tsinghua.edu.cn/centos-altarch/)
- 中科大
  - [https://mirrors.ustc.edu.cn/centos-altarch/](https://mirrors.ustc.edu.cn/centos-altarch/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/centos-altarch/](https://mirror.lzu.edu.cn/centos-altarch/)

### Ubuntu

#### Official

- 官方镜像：[https://ubuntu.com/download](https://ubuntu.com/download)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/ubuntu)
  - [https://mirrors.aliyun.com/ubuntu/](https://mirrors.aliyun.com/ubuntu/)
- Tencent
  - [https://mirrors.cloud.tencent.com/ubuntu/](https://mirrors.cloud.tencent.com/ubuntu/)
- HUAWEI
  - [https://repo.huaweicloud.com/ubuntu/](https://repo.huaweicloud.com/ubuntu/)
- 163
  - [http://mirrors.163.com/ubuntu/](http://mirrors.163.com/ubuntu/)
- Souhu
  - [http://mirrors.sohu.com/ubuntu/](http://mirrors.sohu.com/ubuntu/)
- 北大
  - [https://mirrors.pku.edu.cn/ubuntu/](https://mirrors.pku.edu.cn/ubuntu/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/ubuntu/](https://mirrors.tuna.tsinghua.edu.cn/ubuntu/)
- 中科大
  - [https://mirrors.ustc.edu.cn/ubuntu/](https://mirrors.ustc.edu.cn/ubuntu/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/ubuntu/](http://mirrors.zju.edu.cn/ubuntu/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/ubuntu/](https://mirror.lzu.edu.cn/ubuntu/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/ubuntu/](http://mirrors.neusoft.edu.cn/ubuntu/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/ubuntu/](http://ftp.sjtu.edu.cn/ubuntu/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/ubuntu/](https://mirror.bjtu.edu.cn/ubuntu/)
- 大连理工
  - [http://mirror.dlut.edu.cn/ubuntu/](http://mirror.dlut.edu.cn/ubuntu/)
- 首都在线
  - [http://mirrors.yun-idc.com/ubuntu/](http://mirrors.yun-idc.com/ubuntu/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/ubuntu/](http://mirrors.njupt.edu.cn/ubuntu/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/ubuntu/](https://mirror.nyist.edu.cn/ubuntu/)

### Debian

#### Official

- 官方镜像：[https://www.debian.org/mirror/](https://www.debian.org/mirror/)
- 全球镜像：[https://www.debian.org/mirror/list](https://www.debian.org/mirror/list)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/debian)
  - [https://mirrors.aliyun.com/debian/](https://mirrors.aliyun.com/debian/)
- Tencent
  - [https://mirrors.cloud.tencent.com/debian/](https://mirrors.cloud.tencent.com/debian/)
- HUAWEI
  - [https://repo.huaweicloud.com/debian/](https://repo.huaweicloud.com/debian/)
- 163
  - [http://mirrors.163.com/debian/](http://mirrors.163.com/debian/)
- Souhu
  - [http://mirrors.sohu.com/debian/](http://mirrors.sohu.com/debian/)
- 北大
  - [https://mirrors.pku.edu.cn/debian/](https://mirrors.pku.edu.cn/debian/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/debian/](https://mirrors.tuna.tsinghua.edu.cn/debian/)
- 中科大
  - [https://mirrors.ustc.edu.cn/debian/](https://mirrors.ustc.edu.cn/debian/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/debian/](http://mirrors.zju.edu.cn/debian/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/debian/](https://mirror.lzu.edu.cn/debian/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/debian/](http://mirrors.neusoft.edu.cn/debian/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/debian/](http://ftp.sjtu.edu.cn/debian/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/debian/](https://mirror.bjtu.edu.cn/debian/)
- 大连理工
  - [http://mirror.dlut.edu.cn/debian/](http://mirror.dlut.edu.cn/debian/)
- 首都在线
  - [http://mirrors.yun-idc.com/debian/](http://mirrors.yun-idc.com/debian/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/debian/](http://mirrors.njupt.edu.cn/debian/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/debian/](https://mirror.nyist.edu.cn/debian/)

### Deepin

#### Official

- 官方镜像：[https://www.deepin.org/zh/download/](https://www.deepin.org/zh/download/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/deepin)
  - [https://mirrors.aliyun.com/deepin/](https://mirrors.aliyun.com/deepin/)
- HUAWEI
  - [https://repo.huaweicloud.com/deepin/](https://repo.huaweicloud.com/deepin/)
- 163
  - [http://mirrors.163.com/deepin/](http://mirrors.163.com/deepin/)
- Souhu
  - [http://mirrors.sohu.com/deepin/](http://mirrors.sohu.com/deepin/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/deepin/](https://mirrors.tuna.tsinghua.edu.cn/deepin/)
- 中科大
  - [https://mirrors.ustc.edu.cn/deepin/](https://mirrors.ustc.edu.cn/deepin/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/deepin/](http://mirrors.zju.edu.cn/deepin/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/deepin/](https://mirror.lzu.edu.cn/deepin/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/deepin/](http://ftp.sjtu.edu.cn/deepin/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/deepin/](http://mirrors.njupt.edu.cn/deepin/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/deepin/](https://mirror.nyist.edu.cn/deepin/)

### Fedora

#### Official

- 官方镜像：[https://getfedora.org/en/server/download/](https://getfedora.org/en/server/download/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/fedora)
  - [https://mirrors.aliyun.com/fedora/](https://mirrors.aliyun.com/fedora/)
- Tencent
  - [https://mirrors.cloud.tencent.com/fedora/](https://mirrors.cloud.tencent.com/fedora/)
  
- HUAWEI
  - [https://repo.huaweicloud.com/fedora/](https://repo.huaweicloud.com/fedora/)
- 163
  - [http://mirrors.163.com/fedora/](http://mirrors.163.com/fedora/)
- Souhu
  - [http://mirrors.sohu.com/fedora/](http://mirrors.sohu.com/fedora/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/fedora/](https://mirrors.tuna.tsinghua.edu.cn/fedora/)
- 中科大
  - [https://mirrors.ustc.edu.cn/fedora/](https://mirrors.ustc.edu.cn/fedora/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/fedora/](http://mirrors.zju.edu.cn/fedora/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/fedora/](https://mirror.lzu.edu.cn/fedora/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/fedora/](http://ftp.sjtu.edu.cn/fedora/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/fedora/](http://mirrors.njupt.edu.cn/fedora/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/fedora/](https://mirror.nyist.edu.cn/fedora/)

### Gentoo

#### Official

- 官方镜像：[https://www.gentoo.org/downloads/](https://www.gentoo.org/downloads/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/gentoo)
  - [https://mirrors.aliyun.com/gentoo/](https://mirrors.aliyun.com/gentoo/)
- Tencent
  - [https://mirrors.cloud.tencent.com/gentoo/](https://mirrors.cloud.tencent.com/gentoo/)
  
- HUAWEI
  - [https://repo.huaweicloud.com/gentoo/](https://repo.huaweicloud.com/gentoo/)
- 163
  - [http://mirrors.163.com/gentoo/](http://mirrors.163.com/gentoo/)
- Souhu
  - [http://mirrors.sohu.com/gentoo/](http://mirrors.sohu.com/gentoo/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/gentoo/](https://mirrors.tuna.tsinghua.edu.cn/gentoo/)
- 中科大
  - [https://mirrors.ustc.edu.cn/gentoo/](https://mirrors.ustc.edu.cn/gentoo/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/gentoo/](http://mirrors.zju.edu.cn/gentoo/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/gentoo/](https://mirror.lzu.edu.cn/gentoo/)

### kali

#### Official

- [https://www.kali.org/get-kali/](https://www.kali.org/get-kali/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/kali)
  - [https://mirrors.aliyun.com/kali/](https://mirrors.aliyun.com/kali/)
- Tencent
  - [https://mirrors.cloud.tencent.com/kali/](https://mirrors.cloud.tencent.com/kali/)
- HUAWEI
  - [https://repo.huaweicloud.com/kali/](https://repo.huaweicloud.com/kali/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/kali/](https://mirrors.tuna.tsinghua.edu.cn/kali/)
- 中科大
  - [https://mirrors.ustc.edu.cn/kali/](https://mirrors.ustc.edu.cn/kali/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/kali/](http://mirrors.zju.edu.cn/kali/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/kali/](https://mirror.nyist.edu.cn/kali/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/kali/](http://mirrors.neusoft.edu.cn/kali/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/kali/](https://mirror.bjtu.edu.cn/kali/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/kali/](http://mirrors.njupt.edu.cn/kali/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/kali/](https://mirrors.nwsuaf.edu.cn/kali/)


### Opensuse

#### Official

- [https://get.opensuse.org/zh-CN/tumbleweed/](https://get.opensuse.org/zh-CN/tumbleweed/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/opensuse)
  - [https://mirrors.aliyun.com/opensuse/](https://mirrors.aliyun.com/opensuse/)
- Tencent
  - [https://mirrors.cloud.tencent.com/opensuse/](https://mirrors.cloud.tencent.com/opensuse/)
- HUAWEI
  - [https://repo.huaweicloud.com/opensuse/](https://repo.huaweicloud.com/opensuse/)
- Souhu
  - [http://mirrors.sohu.com/opensuse/](http://mirrors.sohu.com/opensuse/)
- 北大
  - [https://mirrors.pku.edu.cn/opensuse/](https://mirrors.pku.edu.cn/opensuse/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/opensuse/](https://mirrors.tuna.tsinghua.edu.cn/opensuse/)
- 中科大
  - [https://mirrors.ustc.edu.cn/opensuse/](https://mirrors.ustc.edu.cn/opensuse/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/opensuse/](http://mirrors.zju.edu.cn/opensuse/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/opensuse/](https://mirror.lzu.edu.cn/opensuse/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/opensuse/](http://ftp.sjtu.edu.cn/opensuse/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/opensuse/](https://mirror.bjtu.edu.cn/opensuse/)
- 首都在线
  - [http://mirrors.yun-idc.com/opensuse/](http://mirrors.yun-idc.com/opensuse/)



最后，欢迎大家补充优秀的镜像，让我们一起建设好这个仓库！