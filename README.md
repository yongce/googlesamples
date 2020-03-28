# Google Samples Repo

本git库用于聚合有价值的Android官方Samples，便于跟踪其代码和状态，用 **repo** 工具来管理。

repo工具的介绍和使用方法，参见官方文档： https://source.android.com/setup/develop/repo

## 下载代码

下载本项目：
```
$ mkdir googlesamples
$ cd googlesamples
$ repo init -u repo init -u https://github.com/yongce/googlesamples
$ repo sync
$ repo start master --all
```

更新代码：
```
$ repo sync
$ repo start master --all    ---> 按需进行
```

### 关于墙的问题

repo命令本身是一个python脚本，它需要下载回来一个拥有更多python脚本的git库才能工作（包括查看 repo的命令行帮助文档）。默认情况下，repo会使用 **clone.bundle** 模式去下载这个git库（在repo sync下载其它git库时也会 **尝试** 用clone.bundle模式）。而repo命令在下载clone.bundle时，只支持 http/https 代理（git工具支持 socks5 代理）。因此，如果需要翻墙才能访问Google服务（如这里的repo脚本的git库），在使用repo工具，则需要设置代理。例如：

```
alias exportHttpProxy='export HTTP_PROXY=127.0.0.1:1087 && export HTTPS_PROXY=127.0.0.1:1087 && export http_proxy=127.0.0.1:1087 && export https_proxy=127.0.0.1:1087'
alias exportGitProxy='export ALL_PROXY=socks5://127.0.0.1:1080'
```

如果你只有socks5代理，而没有http/https代理，也是有办法的，只需要在执行 **repo init** 命令时，加上 **--no-clone-bundle** 参数即可。例如：

```
repo init -u https://github.com/yongce/googlesamples --no-clone-bundle
```

## 项目列表

Android官方Samples主要存放在 https://github.com/android 和 https://github.com/googlesamples 这两个帐户下面。

### 质量与性能

* Customize lint rules： https://github.com/googlesamples/android-custom-lint-rules
* Auto Test Samples 1： https://github.com/android/testing-samples
* Auto Test Samples 2： https://github.com/googlesamples/android-testing-templates
* Performance Samples: https://github.com/android/performance-samples

### 系统与架构

* Architecture Components: https://github.com/android/architecture-components-samples
* Architecture Samples: https://github.com/android/architecture-samples
* Runtime Permissions： https://github.com/googlesamples/easypermissions
* Storage Samples: https://github.com/android/storage-samples
* Security Samples: https://github.com/android/security-samples
* Dynamic Feature Modules: https://github.com/googlesamples/android-dynamic-code-loading
* NDK Samples: https://github.com/android/ndk-samples

### UI

* UI Samples Repo: https://github.com/android/user-interface-samples
* Graphics Samples: https://github.com/android/graphics-samples
* Sunflower illustrating Jetpack: https://github.com/android/sunflower
* Topeka illustrating material Design: https://github.com/android/topeka
* Animation Samples: https://github.com/android/animation-samples
