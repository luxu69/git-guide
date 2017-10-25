<h3 id="articleHeader0">摘要</h3>
<ul>
<li>Git常用命令记录一下。</li>
<li>Pro Git书籍地址: <a href="http://iissnan.com/progit/" target="_blank">Pro Git</a>
</li>
</ul>
<p><span class="img-wrap"><img data-src="./images/tu" src="./images/tu.png" style="cursor: pointer; display: inline;"></span></p>
<p>图解：</p>
<ul>
<li>Workspace： 工作区</li>
<li>Index/Stage：暂存区</li>
<li>Repository：仓库区（或本地仓库）</li>
<li>Remote：远程仓库</li>
</ul>
<h3 id="articleHeader1">命令</h3>
<h4>一、新建代码库</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 在当前目录新建一个Git代码库
$ git init

# 新建一个目录，将其初始化为Git代码库
$ git init [project-name]

# 下载一个项目和它的整个代码历史
$ git clone [url]" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 在当前目录新建一个Git代码库</span>
$ git init

<span class="hljs-comment"># 新建一个目录，将其初始化为Git代码库</span>
$ git init [project-name]

<span class="hljs-comment"># 下载一个项目和它的整个代码历史</span>
$ git <span class="hljs-built_in">clone</span> [url]</code></pre>
<h4>二、配置</h4>
<p>Git的设置文件为.gitconfig，它可以在用户住目录下（全局配置），也可以在项目目录下（项目配置）</p>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 显示当前的Git配置
$ git config --list

# 编辑Git配置文件
$ git config -e [--global]

# 设置提交代码时的用户信息
$ git config [--global] user.name &quot;[name]&quot;
$ git config [--global] user.email &quot;[email address]&quot;" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 显示当前的Git配置</span>
$ git config --list

<span class="hljs-comment"># 编辑Git配置文件</span>
$ git config <span class="hljs-_">-e</span> [--global]

<span class="hljs-comment"># 设置提交代码时的用户信息</span>
$ git config [--global] user.name <span class="hljs-string">"[name]"</span>
$ git config [--global] user.email <span class="hljs-string">"[email address]"</span></code></pre>
<h4>三、增加/删除文件</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 添加指定文件到暂存区
$ git add [file1] [file2] ...

# 添加指定目录到暂存区，包括子目录
$ git add [dir]

# 添加当前目录的所有文件到暂存区
$ git add .

# 添加每个变化前，都会要求确认
# 对于同一个文件的多处变化，可以实现分次提交
$ git add -p

# 删除工作区文件，并且将这次删除放入暂存区
$ git rm [file1] [file2] ...

# 停止追踪指定文件，但该文件会保留在工作区
$ git rm --cached [file]

# 改名文件，并且将这个改名放入暂存区
$ git mv [file-original] [file-renamed]" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 添加指定文件到暂存区</span>
$ git add [file1] [file2] ...

<span class="hljs-comment"># 添加指定目录到暂存区，包括子目录</span>
$ git add [dir]

<span class="hljs-comment"># 添加当前目录的所有文件到暂存区</span>
$ git add .

<span class="hljs-comment"># 添加每个变化前，都会要求确认</span>
<span class="hljs-comment"># 对于同一个文件的多处变化，可以实现分次提交</span>
$ git add -p

<span class="hljs-comment"># 删除工作区文件，并且将这次删除放入暂存区</span>
$ git rm [file1] [file2] ...

<span class="hljs-comment"># 停止追踪指定文件，但该文件会保留在工作区</span>
$ git rm --cached [file]

<span class="hljs-comment"># 改名文件，并且将这个改名放入暂存区</span>
$ git mv [file-original] [file-renamed]</code></pre>
<h4>四、代码提交</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 提交暂存区到仓库区
$ git commit -m [message]

# 提交暂存区的指定文件到仓库区
$ git commit [file1] [file2] ... -m [message]

# 提交工作区自上次commit之后的变化，直接到仓库区
$ git commit -a

# 提交时显示所有diff信息
$ git commit -v

# 使用一次新的commit，替代上一次提交
# 如果代码没有任何新变化，则用来改写上一次commit的提交信息
$ git commit --amend -m [message]

# 重做上一次commit，并包括指定文件的新变化
$ git commit --amend [file1] [file2] ..." title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 提交暂存区到仓库区</span>
$ git commit -m [message]

<span class="hljs-comment"># 提交暂存区的指定文件到仓库区</span>
$ git commit [file1] [file2] ... -m [message]

<span class="hljs-comment"># 提交工作区自上次commit之后的变化，直接到仓库区</span>
$ git commit <span class="hljs-_">-a</span>

<span class="hljs-comment"># 提交时显示所有diff信息</span>
$ git commit -v

<span class="hljs-comment"># 使用一次新的commit，替代上一次提交</span>
<span class="hljs-comment"># 如果代码没有任何新变化，则用来改写上一次commit的提交信息</span>
$ git commit --amend -m [message]

<span class="hljs-comment"># 重做上一次commit，并包括指定文件的新变化</span>
$ git commit --amend [file1] [file2] ...</code></pre>
<h4>五、分支</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 列出所有本地分支
$ git branch

# 列出所有远程分支
$ git branch -r

# 列出所有本地分支和远程分支
$ git branch -a

# 新建一个分支，但依然停留在当前分支
$ git branch [branch-name]

# 新建一个分支，并切换到该分支
$ git checkout -b [branch]

# 新建一个分支，指向指定commit
$ git branch [branch] [commit]

# 新建一个分支，与指定的远程分支建立追踪关系
$ git branch --track [branch] [remote-branch]

# 切换到指定分支，并更新工作区
$ git checkout [branch-name]

# 切换到上一个分支
$ git checkout -

# 建立追踪关系，在现有分支与指定的远程分支之间
$ git branch --set-upstream [branch] [remote-branch]

# 合并指定分支到当前分支
$ git merge [branch]

# 选择一个commit，合并进当前分支
$ git cherry-pick [commit]

# 删除分支
$ git branch -d [branch-name]

# 删除远程分支
$ git push origin --delete [branch-name]
$ git branch -dr [remote/branch]" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 列出所有本地分支</span>
$ git branch

<span class="hljs-comment"># 列出所有远程分支</span>
$ git branch -r

<span class="hljs-comment"># 列出所有本地分支和远程分支</span>
$ git branch <span class="hljs-_">-a</span>

<span class="hljs-comment"># 新建一个分支，但依然停留在当前分支</span>
$ git branch [branch-name]

<span class="hljs-comment"># 新建一个分支，并切换到该分支</span>
$ git checkout -b [branch]

<span class="hljs-comment"># 新建一个分支，指向指定commit</span>
$ git branch [branch] [commit]

<span class="hljs-comment"># 新建一个分支，与指定的远程分支建立追踪关系</span>
$ git branch --track [branch] [remote-branch]

<span class="hljs-comment"># 切换到指定分支，并更新工作区</span>
$ git checkout [branch-name]

<span class="hljs-comment"># 切换到上一个分支</span>
$ git checkout -

<span class="hljs-comment"># 建立追踪关系，在现有分支与指定的远程分支之间</span>
$ git branch --set-upstream [branch] [remote-branch]

<span class="hljs-comment"># 合并指定分支到当前分支</span>
$ git merge [branch]

<span class="hljs-comment"># 选择一个commit，合并进当前分支</span>
$ git cherry-pick [commit]

<span class="hljs-comment"># 删除分支</span>
$ git branch <span class="hljs-_">-d</span> [branch-name]

<span class="hljs-comment"># 删除远程分支</span>
$ git push origin --delete [branch-name]
$ git branch -dr [remote/branch]</code></pre>
<h4>六、标签</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 列出所有tag
$ git tag

# 新建一个tag在当前commit
$ git tag [tag]

# 新建一个tag在指定commit
$ git tag [tag] [commit]

# 删除本地tag
$ git tag -d [tag]

# 删除远程tag
$ git push origin :refs/tags/[tagName]

# 查看tag信息
$ git show [tag]

# 提交指定tag
$ git push [remote] [tag]

# 提交所有tag
$ git push [remote] --tags

# 新建一个分支，指向某个tag
$ git checkout -b [branch] [tag]" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 列出所有tag</span>
$ git tag

<span class="hljs-comment"># 新建一个tag在当前commit</span>
$ git tag [tag]

<span class="hljs-comment"># 新建一个tag在指定commit</span>
$ git tag [tag] [commit]

<span class="hljs-comment"># 删除本地tag</span>
$ git tag <span class="hljs-_">-d</span> [tag]

<span class="hljs-comment"># 删除远程tag</span>
$ git push origin :refs/tags/[tagName]

<span class="hljs-comment"># 查看tag信息</span>
$ git show [tag]

<span class="hljs-comment"># 提交指定tag</span>
$ git push [remote] [tag]

<span class="hljs-comment"># 提交所有tag</span>
$ git push [remote] --tags

<span class="hljs-comment"># 新建一个分支，指向某个tag</span>
$ git checkout -b [branch] [tag]</code></pre>
<h4>七、查看信息</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 显示有变更的文件
$ git status

# 显示当前分支的版本历史
$ git log

# 显示commit历史，以及每次commit发生变更的文件
$ git log --stat

# 搜索提交历史，根据关键词
$ git log -S [keyword]

# 显示某个commit之后的所有变动，每个commit占据一行
$ git log [tag] HEAD --pretty=format:%s

# 显示某个commit之后的所有变动，其&quot;提交说明&quot;必须符合搜索条件
$ git log [tag] HEAD --grep feature

# 显示某个文件的版本历史，包括文件改名
$ git log --follow [file]
$ git whatchanged [file]

# 显示指定文件相关的每一次diff
$ git log -p [file]

# 显示过去5次提交
$ git log -5 --pretty --oneline

# 显示所有提交过的用户，按提交次数排序
$ git shortlog -sn

# 显示指定文件是什么人在什么时间修改过
$ git blame [file]

# 显示暂存区和工作区的差异
$ git diff

# 显示暂存区和上一个commit的差异
$ git diff --cached [file]

# 显示工作区与当前分支最新commit之间的差异
$ git diff HEAD

# 显示两次提交之间的差异
$ git diff [first-branch]...[second-branch]

# 显示今天你写了多少行代码
$ git diff --shortstat &quot;@{0 day ago}&quot;

# 显示某次提交的元数据和内容变化
$ git show [commit]

# 显示某次提交发生变化的文件
$ git show --name-only [commit]

# 显示某次提交时，某个文件的内容
$ git show [commit]:[filename]

# 显示当前分支的最近几次提交
$ git reflog
" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 显示有变更的文件</span>
$ git status

<span class="hljs-comment"># 显示当前分支的版本历史</span>
$ git <span class="hljs-built_in">log</span>

<span class="hljs-comment"># 显示commit历史，以及每次commit发生变更的文件</span>
$ git <span class="hljs-built_in">log</span> --stat

<span class="hljs-comment"># 搜索提交历史，根据关键词</span>
$ git <span class="hljs-built_in">log</span> -S [keyword]

<span class="hljs-comment"># 显示某个commit之后的所有变动，每个commit占据一行</span>
$ git <span class="hljs-built_in">log</span> [tag] HEAD --pretty=format:%s

<span class="hljs-comment"># 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件</span>
$ git <span class="hljs-built_in">log</span> [tag] HEAD --grep feature

<span class="hljs-comment"># 显示某个文件的版本历史，包括文件改名</span>
$ git <span class="hljs-built_in">log</span> --follow [file]
$ git whatchanged [file]

<span class="hljs-comment"># 显示指定文件相关的每一次diff</span>
$ git <span class="hljs-built_in">log</span> -p [file]

<span class="hljs-comment"># 显示过去5次提交</span>
$ git <span class="hljs-built_in">log</span> -5 --pretty --oneline

<span class="hljs-comment"># 显示所有提交过的用户，按提交次数排序</span>
$ git shortlog -sn

<span class="hljs-comment"># 显示指定文件是什么人在什么时间修改过</span>
$ git blame [file]

<span class="hljs-comment"># 显示暂存区和工作区的差异</span>
$ git diff

<span class="hljs-comment"># 显示暂存区和上一个commit的差异</span>
$ git diff --cached [file]

<span class="hljs-comment"># 显示工作区与当前分支最新commit之间的差异</span>
$ git diff HEAD

<span class="hljs-comment"># 显示两次提交之间的差异</span>
$ git diff [first-branch]...[second-branch]

<span class="hljs-comment"># 显示今天你写了多少行代码</span>
$ git diff --shortstat <span class="hljs-string">"@{0 day ago}"</span>

<span class="hljs-comment"># 显示某次提交的元数据和内容变化</span>
$ git show [commit]

<span class="hljs-comment"># 显示某次提交发生变化的文件</span>
$ git show --name-only [commit]

<span class="hljs-comment"># 显示某次提交时，某个文件的内容</span>
$ git show [commit]:[filename]

<span class="hljs-comment"># 显示当前分支的最近几次提交</span>
$ git reflog
</code></pre>
<h4>八、远程同步</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 下载远程仓库的所有变动
$ git fetch [remote]

# 显示所有远程仓库
$ git remote -v

# 显示某个远程仓库的信息
$ git remote show [remote]

# 增加一个新的远程仓库，并命名 
$ git remote add [shortname] [url]
eg: git remote add origin https://git.coding.net/ghycn/ghycn.coding.com.git

# 取回远程仓库的变化，并与本地分支合并
$ git pull [remote] [branch]

# 上传本地指定分支到远程仓库
$ git push [remote] [branch]

# 强行推送当前分支到远程仓库，即使有冲突
$ git push [remote] --force

# 推送所有分支到远程仓库
$ git push [remote] --all" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 下载远程仓库的所有变动</span>
$ git fetch [remote]

<span class="hljs-comment"># 显示所有远程仓库</span>
$ git remote -v

<span class="hljs-comment"># 显示某个远程仓库的信息</span>
$ git remote show [remote]

<span class="hljs-comment"># 增加一个新的远程仓库，并命名 </span>
$ git remote add [shortname] [url]
eg: git remote add origin https://github.com/luxu69/git-guide.git

<span class="hljs-comment"># 取回远程仓库的变化，并与本地分支合并</span>
$ git pull [remote] [branch]

<span class="hljs-comment"># 上传本地指定分支到远程仓库</span>
$ git push [remote] [branch]

<span class="hljs-comment"># 强行推送当前分支到远程仓库，即使有冲突</span>
$ git push [remote] --force

<span class="hljs-comment"># 推送所有分支到远程仓库</span>
$ git push [remote] --all</code></pre>
<h4>九、撤销</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="# 恢复暂存区的指定文件到工作区
$ git checkout [file]

# 恢复某个commit的指定文件到暂存区和工作区
$ git checkout [commit] [file]

# 恢复暂存区的所有文件到工作区
$ git checkout .

# 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变
$ git reset [file]

# 重置暂存区与工作区，与上一次commit保持一致
$ git reset --hard

# 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变
$ git reset [commit]

# 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致
$ git reset --hard [commit]

# 重置当前HEAD为指定commit，但保持暂存区和工作区不变
$ git reset --keep [commit]

# 新建一个commit，用来撤销指定commit
# 后者的所有变化都将被前者抵消，并且应用到当前分支
$ git revert [commit]

# 暂时将未提交的变化移除，稍后再移入
$ git stash
$ git stash pop" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment"># 恢复暂存区的指定文件到工作区</span>
$ git checkout [file]

<span class="hljs-comment"># 恢复某个commit的指定文件到暂存区和工作区</span>
$ git checkout [commit] [file]

<span class="hljs-comment"># 恢复暂存区的所有文件到工作区</span>
$ git checkout .

<span class="hljs-comment"># 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变</span>
$ git reset [file]

<span class="hljs-comment"># 重置暂存区与工作区，与上一次commit保持一致</span>
$ git reset --hard

<span class="hljs-comment"># 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变</span>
$ git reset [commit]

<span class="hljs-comment"># 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致</span>
$ git reset --hard [commit]

<span class="hljs-comment"># 重置当前HEAD为指定commit，但保持暂存区和工作区不变</span>
$ git reset --keep [commit]

<span class="hljs-comment"># 新建一个commit，用来撤销指定commit</span>
<span class="hljs-comment"># 后者的所有变化都将被前者抵消，并且应用到当前分支</span>
$ git revert [commit]

<span class="hljs-comment"># 暂时将未提交的变化移除，稍后再移入</span>
$ git stash
$ git stash pop</code></pre>
<h4>十、其他</h4>
<div class="widget-codetool" style="display: none;">
      <div class="widget-codetool--inner">
      <span class="selectCode code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="全选"></span>
      <span type="button" class="copyCode code-tool" data-toggle="tooltip" data-placement="top" data-clipboard-text="#生成一个可供发布的压缩包
$ git archive" title="" data-original-title="复制"></span>
      <span type="button" class="saveToNote code-tool" data-toggle="tooltip" data-placement="top" title="" data-original-title="放进笔记"></span>
      </div>
      </div><pre><code class="bash"><span class="hljs-comment">#生成一个可供发布的压缩包</span>
