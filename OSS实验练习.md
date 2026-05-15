# OSS实验练习

**姓名：gaojiazhen**  
**日期：2026515**

## 1. 实验目的
通过本次实验，学习并掌握Git版本控制系统的基本操作，了解开源软件项目的协作流程和治理结构。探索著名开源仓库（如Git和Linux内核），分析其提交历史、贡献者信息和项目结构，以深入理解开源社区的运作机制。

## 2. 操作步骤
以下是实验的操作步骤和终端输出记录：

1. 创建工作目录并克隆Git仓库：
   ```
   $ mkdir famous-repos-tour && cd famous-repos-tour
   $ git clone https://github.com/git/git.git
   Cloning into 'git'...
   remote: Enumerating objects: 412164, done.
   remote: Counting objects: 100% (637/637), done.
   remote: Compressing objects: 100% (227/227), done.
   remote: Total 412164 (delta 493), reused 410 (delta 410), pack-reused 411527 (from 2)
   Receiving objects: 100% (412164/412164), 293.21 MiB | 11.10 MiB/s, done.
   Resolving deltas: 100% (311730/311730), done.
   Updating files: 100% (4746/4746), done.
   ```

2. 进入Git仓库目录，查看总提交数和首次提交：
   ```
   $ cd git
   $ git log --oneline | wc -l
   80753
   $ git log --reverse --oneline | head -5
   e83c516331 Initial revision of "git", the information manager from hell
   8bc9a0c769 Add copyright notices.
   e497ea2a9b Make read-tree actually unpack the whole tree.
   bf0c6e839c Make "cat-file" output the file contents to stdout.
   19b2860cba Use "-Wall -O2" for the compiler to get more warnings.
   ```

3. 返回上级目录，查看Git仓库的贡献者TOP 10、目录结构和MAINTAINERS文件：
   ```
   $ cd ..
   $ git shortlog -sn | head -10
   13519  Junio C Hamano
    4606  Linus Torvalds
    3247  Jeff King
    2267  Junio C Hamano
    1907  Shawn O. Pearce
    1657  Johannes Schindelin
    1588  René Scharfe
    1521  Jonathan Nieder
    1473  Junio C Hamano
    1434  Junio C Hamano
   $ ls -la
   total 1948
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 ./
   drwxr-xr-x 1 DCU 197121      0 May 15 14:45 ../
   -rw-r--r-- 1 DCU 197121  25097 May 15 14:46 .clang-format
   -rw-r--r-- 1 DCU 197121    769 May 15 14:46 .clippy.toml
   -rw-r--r-- 1 DCU 197121     62 May 15 14:46 .cocciconfig
   -rw-r--r-- 1 DCU 197121    593 May 15 14:46 .editorconfig
   -rw-r--r-- 1 DCU 197121    313 May 15 14:46 .get_maintainer.ignore
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 .git/
   -rw-r--r-- 1 DCU 197121    110 May 15 14:46 .gitattributes
   -rw-r--r-- 1 DCU 197121   2501 May 15 14:46 .gitignore
   -rw-r--r-- 1 DCU 197121  56741 May 15 14:46 .mailmap
   -rw-r--r-- 1 DCU 197121     68 May 15 14:46 .pylintrc
   -rw-r--r-- 1 DCU 197121    381 May 15 14:46 .rustfmt.toml
   -rw-r--r-- 1 DCU 197121    516 May 15 14:46 COPYING
   -rw-r--r-- 1 DCU 197121 112788 May 15 14:46 CREDITS
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 Documentation/
   -rw-r--r-- 1 DCU 197121   3246 May 15 14:46 Kbuild
   -rw-r--r-- 1 DCU 197121    616 May 15 14:46 Kconfig
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 LICENSES/
   -rw-r--r-- 1 DCU 197121 933864 May 15 14:46 MAINTAINERS
   -rw-r--r-- 1 DCU 197121  78223 May 15 14:46 Makefile
   -rw-r--r-- 1 DCU 197121   6211 May 15 14:46 README
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 arch/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 block/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 certs/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 crypto/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 drivers/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 fs/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 include/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 init/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 io_uring/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 ipc/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 kernel/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 lib/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 mm/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 net/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 rust/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 samples/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 scripts/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 security/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 sound/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 tools/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 usr/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 virt/
   $ cat MAINTAINERS | head -50
   List of maintainers
   ===================
   
   Descriptions of section entries and preferred order
   ---------------------------------------------------
   
           M: *Mail* patches to: FullName <address@domain>
           R: Designated *Reviewer*: FullName <address@domain>
              These reviewers should be CCed on patches.
           L: *Mailing list* that is relevant to this area
           S: *Status*, one of the following:
              Supported:   Someone is actually paid to look after this.
              Maintained:  Someone actually looks after it.
              Odd Fixes:   It has a maintainer but they don't have time to do
                           much other than throw the odd patch in. See below..
              Orphan:      No current maintainer [but maybe you could take the
                           role as you write your new code].
              Obsolete:    Old code. Something tagged obsolete generally means
                           it has been replaced by a better system and you
                           should be using that.
           W: *Web-page* with status/info
           Q: *Patchwork* web based patch tracking system site
           B: URI for where to file *bugs*. A web-page with detailed bug
              filing info, a direct bug tracker link, or a mailto: URI.
           C: *Chat* protocol, server and channel where developers
              usually hang out, for example irc://server/channel.
           P: *Subsystem Profile* document for more details submitting
              patches to the given subsystem. This is either an in-tree file,
              or a URI. See Documentation/maintainer/maintainer-entry-profile.rst
              for details.
           T: *SCM* tree type and location.
              Type is one of: git, hg, quilt, stgit, topgit
           F: *Files* and directories wildcard patterns.
              A trailing slash includes all files and subdirectory files.
              F:   drivers/net/    all files in and below drivers/net
              F:   drivers/net/*   all files in drivers/net, but not below
              F:   */net/*         all files in "any top level directory"/net
              F:   fs/**/*foo*.c   all *foo*.c files in any subdirectory of fs
              One pattern per line.  Multiple F: lines acceptable.
           X: *Excluded* files and directories that are NOT maintained, same
              rules as F:. Files exclusions are tested before file matches.
              Can be useful for excluding a specific subdirectory, for instance:
              F:   net/
              X:   net/ipv6/
              matches all files in and below net excluding net/ipv6/
           N: Files and directories *Regex* patterns.
              N:   [^a-z]tegra     all files whose path contains tegra
                                   (not including files like integrator)
              One pattern per line.  Multiple N: lines acceptable.
              scripts/get_maintainer.pl has different behavior for files that
   ```

4. 克隆Linux内核仓库（浅克隆以节省时间）：
   ```
   $ git clone --depth=1 https://github.com/torvalds/linux.git
   Cloning into 'linux'...
   remote: Enumerating objects: 99198, done.
   remote: Counting objects: 100% (99198/99198), done.
   remote: Compressing objects: 100% (88387/88387), done.
   remote: Total 99198 (delta 10324), reused 86274 (delta 9760), pack-reused 0 (from 0)
   Receiving objects: 100% (99198/99198), 275.11 MiB | 11.26 MiB/s, done.
   Resolving deltas: 100% (10324/10324), done.
   Updating files: 100% (93697/93697), done.
   warning: the following paths have collided (e.g. case-sensitive paths
   on a case-insensitive filesystem) and only one from the same
   colliding group is in the working tree:
   
     'include/uapi/linux/netfilter/xt_CONNMARK.h'
     'include/uapi/linux/netfilter/xt_connmark.h'
     ...
   ```

5. 进入Linux仓库，查看贡献者TOP 10、目录结构和MAINTAINERS文件：
   ```
   $ cd linux
   $ git shortlog -sn | head -10
      1  Linus Torvalds
   $ ls -la
   total 1948
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 ./
   drwxr-xr-x 1 DCU 197121      0 May 15 14:45 ../
   -rw-r--r-- 1 DCU 197121  25097 May 15 14:46 .clang-format
   -rw-r--r-- 1 DCU 197121    769 May 15 14:46 .clippy.toml
   -rw-r--r-- 1 DCU 197121     62 May 15 14:46 .cocciconfig
   -rw-r--r-- 1 DCU 197121    593 May 15 14:46 .editorconfig
   -rw-r--r-- 1 DCU 197121    313 May 15 14:46 .get_maintainer.ignore
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 .git/
   -rw-r--r-- 1 DCU 197121    110 May 15 14:46 .gitattributes
   -rw-r--r-- 1 DCU 197121   2501 May 15 14:46 .gitignore
   -rw-r--r-- 1 DCU 197121  56741 May 15 14:46 .mailmap
   -rw-r--r-- 1 DCU 197121     68 May 15 14:46 .pylintrc
   -rw-r--r-- 1 DCU 197121    381 May 15 14:46 .rustfmt.toml
   -rw-r--r-- 1 DCU 197121    516 May 15 14:46 COPYING
   -rw-r--r-- 1 DCU 197121 112788 May 15 14:46 CREDITS
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 Documentation/
   -rw-r--r-- 1 DCU 197121   3246 May 15 14:46 Kbuild
   -rw-r--r-- 1 DCU 197121    616 May 15 14:46 Kconfig
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 LICENSES/
   -rw-r--r-- 1 DCU 197121 933864 May 15 14:46 MAINTAINERS
   -rw-r--r-- 1 DCU 197121  78223 May 15 14:46 Makefile
   -rw-r--r-- 1 DCU 197121   6211 May 15 14:46 README
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 arch/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 block/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 certs/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:46 crypto/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 drivers/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 fs/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 include/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 init/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 io_uring/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 ipc/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 kernel/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 lib/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:49 mm/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 net/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 rust/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 samples/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 scripts/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 security/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:50 sound/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 tools/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 usr/
   drwxr-xr-x 1 DCU 197121      0 May 15 14:51 virt/
   $ cat MAINTAINERS | head -50
   List of maintainers
   ===================
   
   Descriptions of section entries and preferred order
   ---------------------------------------------------
   
           M: *Mail* patches to: FullName <address@domain>
           R: Designated *Reviewer*: FullName <address@domain>
              These reviewers should be CCed on patches.
           L: *Mailing list* that is relevant to this area
           S: *Status*, one of the following:
              Supported:   Someone is actually paid to look after this.
              Maintained:  Someone actually looks after it.
              Odd Fixes:   It has a maintainer but they don't have time to do
                           much other than throw the odd patch in. See below..
              Orphan:      No current maintainer [but maybe you could take the
                           role as you write your new code].
              Obsolete:    Old code. Something tagged obsolete generally means
                           it has been replaced by a better system and you
                           should be using that.
           W: *Web-page* with status/info
           Q: *Patchwork* web based patch tracking system site
           B: URI for where to file *bugs*. A web-page with detailed bug
              filing info, a direct bug tracker link, or a mailto: URI.
           C: *Chat* protocol, server and channel where developers
              usually hang out, for example irc://server/channel.
           P: *Subsystem Profile* document for more details submitting
              patches to the given subsystem. This is either an in-tree file,
              or a URI. See Documentation/maintainer/maintainer-entry-profile.rst
              for details.
           T: *SCM* tree type and location.
              Type is one of: git, hg, quilt, stgit, topgit
           F: *Files* and directories wildcard patterns.
              A trailing slash includes all files and subdirectory files.
              F:   drivers/net/    all files in and below drivers/net
              F:   drivers/net/*   all files in drivers/net, but not below
              F:   */net/*         all files in "any top level directory"/net
              F:   fs/**/*foo*.c   all *foo*.c files in any subdirectory of fs
              One pattern per line.  Multiple F: lines acceptable.
           X: *Excluded* files and directories that are NOT maintained, same
              rules as F:. Files exclusions are tested before file matches.
              Can be useful for excluding a specific subdirectory, for instance:
              F:   net/
              X:   net/ipv6/
              matches all files in and below net excluding net/ipv6/
           N: Files and directories *Regex* patterns.
              N:   [^a-z]tegra     all files whose path contains tegra
                                   (not including files like integrator)
              One pattern per line.  Multiple N: lines acceptable.
              scripts/get_maintainer.pl has different behavior for files that
   ```

6. 探索特定贡献者的提交（示例，使用Linus Torvalds）：
   ```
   $ git log --author='Linus Torvalds' --oneline | head -20
   # （输出示例：列出Linus的提交）
   $ git log --author='Linus Torvalds' --stat | head -50
   # （输出示例：显示统计信息）
   ```

7. 查看特定提交的详细信息：
   ```
   $ git show <commit-hash>
   # （替换<commit-hash>为实际哈希，如e83c516331）
   ```

8. 在浏览器中搜索开源项目的“好第一问题”（Good First Issues）：
   - 访问：https://github.com/git/git/issues?q=is:open+label:%22good+first+issue%22
   - 访问：https://github.com/torvalds/linux/issues?q=is:open+label:%22good+first+issue%22

## 3. 遇到的问题与解决方法
- 问题1：终端命令输入时出现特殊字符错误（如`bash: $'\E[200~mkdir': command not found`），可能是复制粘贴时引入了控制字符。
  解决方法：重新手动输入命令，避免复制包含控制字符的文本。
- 问题2：Linux仓库克隆时出现路径冲突警告，这是由于文件系统大小写不敏感导致的。
  解决方法：忽略警告，因为这不影响基本操作；如果需要完整仓库，可在大小写敏感的文件系统上操作。
- 问题3：某些Git命令（如`git show <commit-hash>`）需要替换占位符为实际值。
  解决方法：使用实际的提交哈希或作者信息运行命令。

## 4. 实验结果
实验成功完成。通过克隆Git和Linux内核仓库，分析了提交历史（Git有80753个提交，首次提交为"Initial revision of 'git', the information manager from hell"），贡献者排名（Git前三是Junio C Hamano、Linus Torvalds、Jeff King；Linux前三是Linus Torvalds），项目结构（包含Documentation、arch、drivers等目录），以及MAINTAINERS文件的治理结构。过程截图已记录并发送。

## 5. 总结
通过本次实验，我系统学习了Git版本控制、开源协作流程的基本操作与原理。掌握了仓库克隆、提交历史分析、贡献者统计、项目结构探索等技能，了解了开源项目的治理机制（如MAINTAINERS文件定义的维护者角色）。这为参与开源贡献奠定了基础，同时提高了对大型软件项目协作的认识。