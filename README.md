UnityCleanEmptyDirectories
==========================

This is an asset that cleans empty directories and corresponding meta files in your project.
I created this asset to solve [empty directories on Unity and Git problem](http://altprog.com/en/2014/10/28/empty-folders-meta-files-unity-3d-and-git/).
You can also install this asset from the [Asset Store](http://u3d.as/content/alt-prog/clean-empty-directories). 

#2019年1月15日22:08:00
https://stackoverflow.com/questions/19151247/ignoring-folder-%20meta-%20files-on-version-control
空文件夹在版本管理中会导致一些问题，这个库呢就专门处理那些空的文件夹，删掉
当然了，肯定是还有其他方法的，比如下面这个，他是在仓库Hook文件夹里面添加规则，这样就保证了文件夹和mate文件绝对的一致性了（就是剑在人在剑亡人亡的那种意思）。
 doitian/unity-git-hooks: Git hooks for Unity3D project https://github.com/doitian/unity-git-hooks

网友的脑洞也是不可小觑的还有这个库也是魔改git hook 解决了 用户gitignore忽略了文件夹遗漏mate文件导致版本控制经常冲突的问题 
 kayy/git-pre-commit-hook-unity-assets: Pre-commit hook script for Unity to check that every folder that just has marked to be ignored in .gitignore has an entry for its meta file to be ignored too. https://github.com/kayy/git-pre-commit-hook-unity-assets
 

附上Unity 版本控制的官方教程，感觉有点老但也值得一瞥~
https://unity3d.com/cn/learn/tutorials/topics/production/mastering-unity-project-folder-structure-version-control-systems


以下是新版第三方版本控制技术支持：

https://docs.unity3d.com/Manual/ExternalVersionControlSystemSupport.html

Todo：
加上一个排除/过滤功能，将还未来得及使用的空文件夹选择性的保留，如果选择保留呢，会在空文件夹中加一个隐藏文件（gitkeep~）注意，加了这个波浪符号的文件Unity不会将它当成资源，如此一来便实现了这个保留文件夹的功能。

测试发现，虽然gitkeep~ 这样的命名方式unity不会识别成资源，但是与此同时，git也不会追踪它了，所以这个文件所在的文件夹对于git来说还是空文件夹，所以还是用下面的方式保留空文件吧：

下面是另一种方式保留空文件夹的方式（.gitkeep）

https://blog.csdn.net/fengchao2016/article/details/52769151

GitIgnore 文件来至于此，但他少了个 `` .vs/ ``

https://github.com/YesAndGames/unity-gitignore/blob/master/.gitignore
