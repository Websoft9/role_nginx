Ansible Role: Nginx
=========

本 Role 用于在PHP运行环境下安装 [Nginx](http://nginx.org/)。

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu18.04 AmazonLinux |
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  |


## Related roles

本 Role 在运行时需要确保已经运行：common。以 LNMP 为例：

```
roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_nginx, tags: "role_nginx"}
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| init_db | 参考下方  | 字典 | 否 |
| init_application | [...]   | 字典 | 否 |

注意：
1. init_application 和 init_application 初始化在项目主变量文件中统一修改。
2. 默认数据库管理员密码初始化范例（程序已经自动处理随机密码脚本与其service的先后关系）


## Example

```
- name: LNMP
  hosts: all
  become: yes
  become_method: sudo 
  vars_files:
    - vars/main.yml 

  roles:
    - { role: role_common }
    - { role: role_nginx }
    ...
```

## FAQ


