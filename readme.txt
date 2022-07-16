D:\docker-data\docker-desktop-data    docker数据目录，镜像的目录
D:\docker-data\wsl	wsl系统目录，linux子系统Ubuntu-20.04
D:\docker-data\docker-desktop	docker目录


修改Docker盘位操作

1、查看状态
 C:\Users\Administrator> wsl --list -v
          NAME                         STATE           VERSION
* docker-desktop               Stopped         2
  docker-desktop-data    Stopped         2

2、备份已有的数据
PS C:\Users\Administrator> wsl --export docker-desktop-data "F:\Docker\wsl\data\docker-desktop-data.tar"

3、删除旧数据(数据未备份前请谨慎操作)
C:\Users\Administrator> wsl --unregister docker-desktop-data
正在注销...
C:\Users\Administrator> wsl --list -v
  NAME              STATE           VERSION
* docker-desktop    Stopped         2

4、 导入数据到新盘
 C:\Users\Administrator> wsl --import docker-desktop-data "F:\Docker\wsl\data" "F:\Docker\wsl\data\docker-desktop-data.tar" --version 2
 C:\Users\Administrator> wsl --list -v
          NAME                        STATE           VERSION
* docker-desktop              Stopped         2
  docker-desktop-data    Stopped         2