一、管理环境

1.创建新环境
conda create --name <env_name> <package_names>
eg： conda create --name python2 python=2.7 ，即创建一个名为“python2”的环境，环境中安装版本为2.7的python。
eg： conda create -n python3 python=3.5 numpy pandas ，即创建一个名为“python3”的环境，环境中安装版本为3.5的python，同时也安装了numpy和pandas。

2.切换环境
activate <env_name>

3.退出环境至root
deactivate

4.显示已创建环境
conda info --envs  或  conda info -e  或  conda env list

5. 复制环境
conda create --name <new_env_name> --clone <copied_env_name>

6. 删除环境
conda remove --name <env_name> --all

二、管理包

1. 查找可供安装的包版本

① 精确查找

conda search --full-name <package_full_name>
eg: conda search --full-name python 即查找全名为“python”的包有哪些版本可供安装。

② 模糊查找

conda search <text>
eg: conda search py 即查找含有“py”字段的包，有哪些版本可供安装。

2. 获取当前环境中已安装的包信息

conda list

3. 安装包

① 在指定环境中安装包

conda install --name <env_name> <package_name>
eg: conda install --name python2 pandas 即在名为“python2”的环境中安装pandas包。

② 在当前环境中安装包

conda install <package_name>

eg:conda install pandas 即在当前环境中安装pandas包

③ 使用pip安装包

→ 使用场景

当使用 conda install 无法进行安装时，可以使用pip进行安装。例如：see包。



→ 命令

pip install <package_name>
注意： <package_name> 为指定安装包的名称。包名两边不加尖括号“<>”。
如： pip install see 即安装see包。


→ 注意

pip只是包管理器，无法对环境进行管理。因此如果想在指定环境中使用pip进行安装包，则需要先切换到指定环境中，再使用pip命令安装包。
pip无法更新python，因为pip并不将python视为包。
pip可以安装一些conda无法安装的包；conda也可以安装一些pip无法安装的包。因此当使用一种命令无法安装包时，可以尝试用另一种命令。

4. 卸载包

① 卸载指定环境中的包

conda remove --name <env_name> <package_name>
注意：
① <env_name> 即卸载包所在指定环境的名称。环境名两边不加尖括号“<>”。

② <package_name> 即要卸载包的名称。包名两边不加尖括号“<>”。

例如： conda remove --name python2 pandas 即卸载名为“python2”中的pandas包。


② 卸载当前环境中的包

conda remove <package_name>
注意：
① <package_name> 即要卸载包的名称。包名两边不加尖括号“<>”。

② 执行命令后即在当前环境中卸载指定包。

例如： conda remove pandas 即在当前环境中卸载pandas包。


5. 更新包

① 更新所有包

conda update --all
或

conda upgrade --all
建议：在安装Anaconda之后执行上述命令更新Anaconda中的所有包至最新版本，便于使用。


② 更新指定包

conda update <package_name>
或

conda upgrade <package_name>
注意：
① <package_name> 为指定更新的包名。包名两边不加尖括号“<>”。

② 更新多个指定包，则包名以空格隔开，向后排列。如： conda update pandas numpy matplotlib 即更新pandas、numpy、matplotlib包。

