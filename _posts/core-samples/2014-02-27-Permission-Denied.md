---
layout: post
category : Problem
tagline:
tags : [error, git]
---
{% include JB/setup %}

今天在往openshift上传修改时，碰到一个问题，下面把解决过程描述一下。
###错误信息
在添加了一些修改, 准备push到openshift的时候出现了一个错误：

    Permission denied (publickey,gssapi-keyex,gssapi-with-mic). fatal: Could not read from remote repository.

<!-- more -->

###解决方法

可能跟同一个git连接有两个远程repo有关，因为本地还有一些上传到github上的文件夹，当时上传时也出现同样问题，后来修改了ssh的public key。在网上搜索了半天，大部分都说了和ssh的public key有关，于是寻找openshift的ssh配置问题,果然通过

    rhc setup

重新设置ssh的pulic key后问题解决。
