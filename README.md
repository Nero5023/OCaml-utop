# OCaml opam 下载 utop 问题

## 1. MacOS 安装 utop 问题解决
### Requirement
#### 安装好 ocaml 环境
1. 安装好 OCmal 和 opam, 需要有 [brew](https://brew.sh/)
```
$ brew install ocaml
$ brew install opam
```
2. 初始化 opam 环境
```
$ opam init
```
### Issues
1. 可能是缺少 xcode command line tool。下载: ```xcode-select --install```
2. 静态库链接问题，可能装过 binutils 导致链接有误。可能可以通过 ```brew unlink binutils``` 来解决
3. 权限问题

### 通用解决方法（不完美）
#### 1. Backup ~/.opam directory

##### How to go to home directioy? 
```
$ cd ~ && open .
```
##### How to show hidden directioies or files?
Keyboard shortcut ```CMD+SHIFT+.```

#### 2. Delete ~/.opam directory

#### 3. Download opam.zip
[https://drive.google.com/file/d/12GJybDIgZG1G9xf10W85sINHyWPUMmMi/view?usp=sharing](https://drive.google.com/file/d/12GJybDIgZG1G9xf10W85sINHyWPUMmMi/view?usp=sharing)

#### 4. Unzip opam.zip to your home directory

#### 5. Try utop
```
$ utop
```
If it doesn't work, please delete ~/.opam directory and use your backup instead.



## 2. 使用 Docker
这是通用的方法，任何系统都可以使用
1.  [Install docker](https://docs.docker.com/get-docker/)
2.  Pull image by using docker
```
$ docker pull nero5023/ocaml-utop:1.0
```
3. Run 
```
$ docker run --name my-utop -it nero5023/ocaml-utop:1.0 utop
```
And then utop REPL will show up.

Next time you enter utop, just run
```
$ docker start -i  my-utop
```