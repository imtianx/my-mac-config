# my-mac-config
some configurations ,tools and softwares for  my macbook pro  in the developement

## install
### [常用软件安装](install_note.md)

## using
### [docker 使用](docker.md)

## Git LFS 使用
```
brew install git-lfs
git lfs install
git lfs track "backup/*"
// or git add .gitattributes
```

## MAC command

```
// 开启未知来源
sudo spctl --master-disable
```

## Clash 配置

clash for windows 配置 parsers
```yaml
parsers: # array
  - reg: ^[a-zA-z]+://[^\s]* # 正则匹配 url 
    yaml:
      prepend-proxy-groups:
        - name: 'chatgpt'
          type: select
          proxies:
            - '🌐 国外流量'
      prepend-rules:
        - DOMAIN-SUFFIX,unisat.io,chatgpt
        - DOMAIN-SUFFIX,openai.com,chatgpt
      commands:
        - proxy-groups.chatgpt.proxies=[]proxyNames|美国  # 过滤美国节点
```




## 参考
1. 强迫症的 Mac 设置指南 [macdao/ocds-guide-to-setting-up-mac](https://github.com/macdao/ocds-guide-to-setting-up-mac)
2. [macOS 上有哪些值得推荐的常用软件？](https://www.zhihu.com/question/19550256)
3. [10 个实用技巧，让 Finder 带你飞](https://sspai.com/post/27403)
