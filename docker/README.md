# Nexus3 docker仓库命令行工具

## 修改仓库配置
编辑 **.credentials** 文件, 修改对应的nexus主机、登陆用户名/密码、docker仓库名。


## 构建镜像
`docker build . -t lusyoe/nexus-cli`


## 启动进入容器
`docker run -it --rm lusyoe/nexus-cli bash`


## 操作命令

以下以setup镜像为例，可以替换为自己的镜像名

```
查看仓库中的所有镜像
./nexus-cli image ls

查看setup镜像的所有tag
./nexus-cli image tags -name setup

查看setup镜像指定的tag详细信息，如：大小、layer等
./nexus-cli image info -name setup -tag 9

删除setup镜像指定的tag
./nexus-cli image delete -name setup -tag 9

删除setup镜像所有的版本，仅保留最后4个
./nexus-cli image delete -name setup -keep 4
```
