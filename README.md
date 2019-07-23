# 2048
2048小游戏
# 项目背景
2048是一个风靡全球的益智类小游戏，通过上下左右控制来合并盘子里的数字，直到盘子里出现2048。

# 依赖库
- linux: apt-get install libncurses5-dev
- Mac: brew install ncurses
- Windows:
    1. 安装编译器MinGW,https://sourceforge.net/projects/mingw-w64/files/mingw-w64/mingw-w64-release/ 下载mingw-w64-install.exe 5.0.4版本,解压到本地目录，例如 C:\mingw64,然后把C:\mingw64\bin 加入到系统设置的路径里,打开命令行控制台输入g++，确认有这个命令以保证安装是成功
    2. 编译pdcurses库,https://sourceforge.net/projects/pdcurses/files/pdcurses/3.6/pdcurs36.zip/download 下载pdcurses后解压到C:\pdcurs36目录，命令行控制台cd到 C:\pdcurs36\wincon目录，运行 mingw32-make 命令编译pdcurses库，编译成功后目录下有多个demo的exe文件以及一个pdcurses.a文件，这个文件是库文件。

# 开发要点
1. 一次只能合并相邻的两个数字，例如 **[2 2 2 2]** ，向右合并以后是 **[空 空 4 4]** ，不是 **[空 空 空 8]**
2. 每次合并的时候，合并方向优先级高，例如 **[空 2 2 2]**，向右合并以后是 **[空 空 2 4]**，不是 **[空 空 4 2]** 
3. 判断游戏胜利或者失败
4. 每次合并以后随机新出4的概率10%

# 编译命令
- Linux/Mac: g++ 2048.cpp -l ncurses -o 2048
- Windows: g++ 2048.cpp C:\pdcurs36\wincon\pdcurses.a -I C:\pdcurs36\ -o 2048

# 开发步骤
1. [引入curses库]
2. [绘制游戏界面]
3. [游戏状态切换]
4. [重启初始化游戏]
5. [向左移动]
6. [向其他方向移动]
7. [游戏胜负判定]
