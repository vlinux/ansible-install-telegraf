# Telegraf-Ansible批量部署监控Docker,LinuxOS:crescent_moon:

> ### 确保提前在Ansible执行主机上做好免密钥登录

### 1、下载所需文件:arrow_double_down:

下载Ansible部署文件：

```bash
# git clone https://github.com/vlinux/ansible-install-telegraf.git
# cd ansible-install-telegraf
```

### 2、根据环境修改Ansible文件:confused:

修改hosts文件,根据规划修改对应IP

```bash
# vi hosts
...
```

默认使用rsa进行密钥加密,如有不同,请修改ansible.cfg文件中的私钥路径

```bash
# vi ansible.cfg
# 配置为中控机私钥文件地址
private_key_file = /root/.ssh/id_rsa
```

### 3、一键部署:basketball_man:

```shell
# ansible-playbook -i hosts telegraf_install.yaml
```



## 说在后面

本项目最终采取的监控组件有Prometheus,telegraf,grafana

其实Telegraf跟influxdb的组合才是最nice的

很无奈因为环境的原因

不能使用cAdvisor等exporter,故只好这样东拼西凑,不过这样来监控主机的Docker容器和基础性能倒也不错