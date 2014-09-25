
如果运行下面命令

    env x='() { :;}; echo vulnerable' bash -c 'echo hello'

输出结果为：

    vulnerable
    hello

则有漏洞，需要赶紧修复

运行命令：

    curl https://raw.githubusercontent.com/luofei614/bashfix/master/bashfix|bash 

然后会自动升级，修复bash的漏洞

再运行

    env x='() { :;}; echo vulnerable' bash -c 'echo hello'

如果结果是：

    bash: warning: x: ignoring function definition attempt
    bash: error importing function definition for `x'
    hello

证明漏洞修复
