# ROS Installs

此软件源包含了小强相关的rosinstall文件。方便用户通过wstool工具对自己的工作空间进行管理。比如软件的更新。恢复出厂软件设置等等。

## 文件说明

|文件|说明|
|:--|:--|
|xq4-pro.rosintall | 小强XQ4 Pro 工作空间文件|
|mini.rosinstall | 小强 mini 工作空间文件|
|xq5.rosinstall |小强 XQ5 工作空间文件|

## 如何使用

### 创建工作空间

```bash
mkdir -p catkin_ws/src
cd catkin_ws/src
wstool init
```

如上操作会在 catkin_ws/src 文件夹内创建一个.rosinstall文件。这个文件是wstool工具用来记录工作空间的软件信息的文件。catkin_ws为示例的工作空间路径。

### 添加rosintall文件

```bash
cd ~/Documents
git clone https://github.com/bluewhalerobot/xiaoqiang-rosinstall.git
cd catkin_ws/src
# 此处以xiaoqiang xq4 pro 的工作空间为例。请根据你的版本选择不同的rosintall文件
wstool merge ~/Documents/xiaoqiang-rosinstall/xq4-pro.rosinstall
```

以上操作会将对应的rosintall文件内容添加到本地工作空间的rosinstall文件中。
添加rosinstall只需要第一次执行。如果已经添加过了，之后就不需要再添加了。

### 更新软件

```bash
wstool status
wstool update
```

如果有更新失败的软件包，说明本地文件发生了更改。如果想要获取到原版的小强程序可以直接把本地软件包删除。然后再次运行 `wstool update`。

### 查看自己修改过哪些文件

```bash
wstool status
```

此指令会列出小强工作空间中左右被修改的文件。