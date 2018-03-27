- Git工具
  - ## 交互式暂存　##
    ```
    $ git add -i/--interactive                    #启用交互式暂存界面
    $ git add -p/--path                         #部分文件暂存

    ```

  - ## 储藏与清理　##
     - ### 储藏　###
      ```
      $ git stash　　　　　　　　　　　　　　　　　 #保存当前工作目录的状态到储藏(包括已暂存和未暂存),默认只会储藏已经在索引中的文件
      $ git stash --keep-index                #保存当前工作目录的状态到储藏(只包括未暂存的部分)
      $ git stash --include-untracked/-u      #保存当前工作目录的状态到储藏(包括未跟踪的文件)
      $ git stash save                        #保存当前工作目录的状态到储藏
      $ git stash list                        #查看堆栈中的储藏
      $ git stash apply                       #从堆栈中应用储藏
      $ git stash pop                         #从堆栈中应用储藏，应用后从堆栈中丢弃储藏
      $ git stash drop                        #从堆栈中删除储藏
      $ git stash --patch                      #交互式的提示哪些改动需要储藏
      $ git stash branch <分支名称>　　　　　　　　#将储藏的内容应用到一个新的分支来工作
      ```

    - ### 清理 ###
      ```
      $ git clean -f -d
      $ git clean -n -d
      $ git clean -n -d -x
      $ git clean -x -i
      ```
