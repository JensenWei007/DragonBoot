# DragonBoot

尝试在 DragonOS 上实现 LinuxBoot 所做的事~

--- 

## 开发情况

- [x] x86_64架构支持
- [x] u-root 根文件系统支持
- [x] u-root 使用 kexec 切换到 Linux 内核
- [ ] 多架构支持
- [ ] 更完善的 kexec 执行流程
- [ ] 更多的 kexec 系列系统调用, 如 kexec_file_load()

## 项目 release 成果

当前此项目只在一个环境在测试通过, 测试日期为 2025.10.20, 如未在下方标注特定版本，则为默认测试日期时的最新版本。

测试使用的特定软件版本为：

- OS: Ubuntu 22.04
- go: 1.24.6 amd64
- Linux kernel(for kexec): 6.15.4

## 项目使用流程

### 基本运行环境

项目构建需要基本的运行环境, 一般来说, DragonOS 的构建环境可以基本满足此项目的构建要求, 如遇到缺少软件包等情况, 使用 apt install 安装即可。

### Go 环境支持

项目需要 Go 语言环境支持, 你可以通过命令检查是否有 Go 语言环境: 

```bash
go version
```

如果没有获取到版本, 可以使用下面的脚本安装, 仅支持 x86_64 架构, 版本固定为已经过测试的 1.24.6:

```bash
sudo ./go_install.sh
```

安装完成后可以使用 `go version` 查看是否可以正常找到.

### u-root 构建


