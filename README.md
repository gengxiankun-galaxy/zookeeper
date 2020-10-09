ZOOKEEPER
=========

通过 ansible 部署在容器下运行的 Zookeeper 服务。

Installation
------------

`ansible-galaxy install gengxiankun.zookeeper`

Role Variables
--------------

variable | description
------------ | -------------
OPT_PATH | 部署目录
ZOOKEEPER_CONTAINER_NAME | zookeeper 容器名称
ZOKKEEPER_DEPLOYMENT_MODE | zookeeper 部署模式，PseudoDistributed、FullyDistributed
ZOOKEEPER_NODE_NUM | zookeeper 节点数
ZOOKEEPER_IMAGE_TAG | zookeeper 镜像版本
ZOOKEEPER_NETWORK | docker network name ，其他依赖 zookeeper 的服务，可通过绑定此网络实现与 zookeeper 的通信（同样容器服务的情况下）
ZOOKEEPER_PORT | zookeeper 服务对外提供服务的端口，会随着节点数递增


Dependencies
------------

- Docker

Example Playbook
----------------

    - hosts: servers
      roles:
        - gengxiankun.hadoop
      vars:
        - OPT_PATH: /opt
        - SRV_PATH: /data/runtime
        - ZOOKEEPER_NODE_NUM: 3
        - ZOOKEEPER_IMAGE_TAG: latest
        - ZOOKEEPER_NETWORK: zookeeper
        - ZOOKEEPER_PORT: 2181

License
-------

BSD

Author Information
------------------

This role was created in 2019 by Xiankun Geng, Learn more about the author's role in [galaxy](https://galaxy.ansible.com/gengxiankun).