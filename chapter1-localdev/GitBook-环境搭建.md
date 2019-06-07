## GitBook环境配置和常用命令

1. node.js  [官网: https://nodejs.org/en/download](https://nodejs.org/en/download)
1. 安装gitbook命令行工具 命令行执行：`npm install -g gitbook-cli` 
2. 安装后可以使用全局命令 gitbook
3. 在本地创建一个文件夹 然后 进入
4. 初始化gitbook ： `gitbook init` 会生成两个文件, 
5. **README.md** 书籍的介绍写在这里，  **SUMMARY.md** 文件书籍目录结构在这里配置
6. 找一个 markdown 编辑文件 (Typora， VsCode, Atom,)
7. 以下步骤使用命令操作 在目录中新增章节的目录后使用 `gitbook init` 会自动生成章节的文件
8. 启动本地服务器 `gitbook serve`  自动编译为静态html文件
9.  生成html目录 `gitbook build [书籍路径] [输出路径]` 
10. 生成PDF文件 `gitbook pdf ./ ./mybook.pdf`
11. 生成epub电子书 `gitbook epub ./ ./mybook.epub` 