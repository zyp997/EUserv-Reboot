## 启用前，请先进入.github/workflows的action.yml文件，点击小铅笔删除第3行“ON”前的“#”，再右侧点击start commit保存。默认每天检查！可自行修改时间。

# EUserv_extend
使用Github Action自动续期EUserv免费IPv6 VPS脚本

## 说明

自动获取账号内所有的VPS项目，并检测是否需要续期，需要续期会自动续期。

## 使用说明

1、Fork 本仓库，然后点击你的仓库右上角的 Settings，找到 Secrets 这一项，添加两个秘密环境变量`USERNAME`和`PASSWORD`。支持同时添加多个帐户，数据之间用单个空格 ` ` 隔开即可，帐户名和帐户密码需一一对应。**之前是用半角逗号分割的，更换成空格后，更新脚本后记得修改原变量的值**

```
USERNAME: 你的EUserv账户邮箱或Customer ID 第二个账户
PASSWORD: 第一个账户密码 第二个账户密码
```

2、设置好环境变量后点击你的仓库上方的 Actions 选项，点击 `I understand...` 按钮确认在 Fork 的仓库上启用 GitHub Actions 。

3、最后在你这个 Fork 的仓库内随便改点什么（比如给 README 文件删掉或者增加几个字符）提交一下手动触发一次 GitHub Actions 就可以了 **（重要！！！请不要向本仓库提交无关的PR，请在你自己Fork的仓库上提交。测试发现在 Fork 的仓库上 GitHub Actions 的定时任务不会自动执行，必须要手动触发一次后才能正常工作）** 。

4、仓库内包含的 GitHub Actions 配置文件会在每天国际标准时间 0点50分。自动执行检查账号的脚本文件，如果检查到有需要续期的VPS，会自动续期，你也可以通过 `Push` 操作手动触发执行（建议修改脚本执行时间）。

**注意：** 为了实现某个帐户访问出错时不中断程序继续尝试下一个，除非特殊情况，GitHub Actions 的状态可能将永远是“通过”（显示绿色的✔），请自行检查 GitHub Actions 日志 `Auto renew` 项的输出确定程序执行情况。

## 其他说明

若使用Github Actions运行本脚本，将会公开你的账号中VPS个数以及VPS的ID（**Contract**）

## 参考（及本文档）

hostloc-auto-get-points: https://github.com/inkuang/hostloc-auto-get-points  MIT License
