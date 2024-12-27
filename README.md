# SHU Bachelor Thesis OSC v3.x

## 1. 关于 SHU-Bachelor-Thesis-OSC

本模板是上海大学本科生毕业论文 latex 模板 - 开源社区版本。

此模板基于[SHU-Bachelor-Thesis](https://github.com/alfredbowenfeng/SHU-Bachelor-Thesis)修改得来。

本身[SHU-Bachelor-Thesis](https://github.com/alfredbowenfeng/SHU-Bachelor-Thesis)又是由 [ShuThesis](https://github.com/ahhylau/shuthesis)修改得来的。后者是一个支持上海大学硕士和博士毕业论文的 latex 模板，前者对其进行了一定的改进，但是还有诸多遗留问题。

本模板对[SHU-Bachelor-Thesis](https://github.com/alfredbowenfeng/SHU-Bachelor-Thesis) 遗留的问题又进行了进一步改进，使其尽量与上海大学本科生论文的 MS Word 版本格式一致。

感谢前面几位同学的工作和开源精神。希望本模板能帮助到本科生同学，希望越来越多的同学能加入到开源社区大家庭。

模板的维护是一个相当考验细节处理的工作，欢迎 pull requests. 作者会尽可能尽快处理。

## 2. TODO List

- [x] 重构项目目录。
- [ ] 更新 README.md 和相关文档，匹配 v3.x.
- [x] 增加 bash 编译脚本。
- [ ] 增加 bat 编译脚本。
- [ ] 增加 ps1 编译脚本。
- [ ] 增加 CI: Build Check.
- [x] 增加 CD: Release.
- [ ] Windows + Latex 环境配置文档。
- [ ] Windows + WSL + Docker + Latex 环境配置文档。
- [ ] Mac + Latex 环境配置文档。
- [ ] VSCode 开发环境集成文档。

## 3. 使用步骤

### 3.1. 本地

- 本地安装 Latex.
- 下载本模板到本地解压，或 clone 本模板。
- 修改 data 文件夹下的.tex 文件，编辑论文内容。
- 通过根目录下的 main.tex 文件添加或删去章节。
- 编译：`bash scripts/build.sh xebib`.

### 3.2. Overleaf

- 下载本模板到本地解压，或 git clone 本模板。
- 如果使用了 git clone, 删除模板内 (隐藏的) .git 目录：`rm -rf .git`.
- 将模板压缩为 .zip 文件。
- 打开 Overleaf, 点击创建新项目并上传项目，将 zip 文件拖入对话框。
- 加载完成后，点击左上角菜单，在编译器处选择 XeLaTeX.
- 按下 Ctrl-S 保存并编译。

## 4. 注意事项

### 4.1. 论文信息

你需要在 `main.tex` 的导言区修改你的个人信息， `data/cover.tex` 和 `data/declaration.tex` 不需要进行修改。

```tex
% 下面是论文相关信息的填写：
% 论文题目：
\newcommand{\iTitle}{基于摸鱼链的隐私保护摸鱼学习技术研究}
% 学院：
\newcommand{\iSchool}{摸鱼工程与科学学院}
% 专业：
\newcommand{\iMajor}{摸鱼科学与技术}
% 学号：
\newcommand{\iStudentNumber}{20122012}
% 学生姓名：
\newcommand{\iStudentName}{莫雨}
% 指导老师：
\newcommand{\iSupervisorName}{余墨}
% 起讫时间：
\newcommand{\iThesisTime}{2024 年 1 月 15 日起 5 月 24 日止}
```

如果在签字后需要覆盖原创性声明部分，可以增加 pdf 文件后，修改 `main.tex` 文章区起始的代码。

```tex
% before:
\include{data/cover}
\include{data/declaration}
% 如果需要直接覆盖封面和原创性声明，请将下面一行取消注释，并注释上面两行。
% \includepdf[pages={1,2}]{cover.pdf}

% after:
\include{data/cover}
\includepdf[pages={1}]{declaration.pdf}
```