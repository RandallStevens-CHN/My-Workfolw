# My-Workfolw
github workflow的学习
## 创建步骤
  1.在仓库中  .github/workflows/ 目录下创建workflow
 
 
  2.具体配置
     name: learn-github-actions （在action中显示的workflow名，可选）
     on: [push]                 （触发器，可配置多个）
     jobs:                       （定义jobs 可多个）
     check-bats-version:         （job名）      
     runs-on: ubuntu-latest       (指定运行的机器)
     steps:                       （workflow步骤）
        - uses: actions/checkout@v3
        - uses: actions/setup-node@v3
          with:
            node-version: '14'
        - run: npm install -g bats
        - run: bats -v
       
  3.说明
      支持的触发器很多有多种 见 https://docs.github.com/cn/actions/using-workflows/events-that-trigger-workflows#schedule
      常用的：
        schedule  按时间触发
        

