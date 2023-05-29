# nvim


## 要求
neovim >=0.8.0

非ARM版本，优先找[Stable Release](https://github.com/neovim/neovim/releases/tag/stable)文件

#### Install from source

针对ARM版本，编译源码。以下在Jetson平台验证。其它ARM平台可以参考。

```Shell
sudo apt remove python3-neovim neovim  # 先卸载之前的neovim版本

sudo apt install ninja-build gettext cmake unzip curl  # 安装依赖

mkdir ~/setup -p
cd ~/setup
git clone https://github.com/neovim/neovim
cd neovim/
# 编译安装
make CMAKE_BUILD_TYPE=Release
sudo make install
sudo cp /usr/local/bin/nvim /usr/bin/
nvim --version
```

项目中已经包含`nvim/bin/nvim-arm64-v0.10.0-dev-release`
可以直接使用：
```Shell
sudo cp nvim/bin/nvim-arm64-v0.10.0-dev-release /usr/bin/nvim
```


**Uninstall**

```Shell
sudo cmake --build build/ --target uninstall
sudo rm /usr/local/bin/nvim    # 检查
sudo rm -r /usr/local/share/nvim/    # 检查
sudo rm /usr/bin/nvim
```

## 加载配置
```Shell
mkdir -p ~/.config
cd ~/.config
git clone https://github.com/jeffw6/neovim
```

## 基于配置

1. 显示行号；
2. 缩进为2；
3. 启用鼠标；
4. 默认主题： tokyonight-moon


## 插件

1. 自动安装管理：`packer`;
2. 主题：folke/tokyonight.nvim;
3. 状态栏：lualine.nvim;
4. 文档树：nvim-tree.lua;
5. 定位窗口：vim-tmux-navigator;
6. 语法高亮：nvim-treesitter;
7. 括号颜色：nvim-ts-rainbow;
8. LSP: mason, mason-lspconfig, nvim-lspconfig;
9. 自动补全：nvim-cmp, cmp-nvim-lsp, LuaSnip, cmp_luasnip, friendly-snippets;
10. 文件路径：cmp-path;
11. gcc和gc注释：Comment.nvim;
12. 自动补全括号：nvim-autopairs;
13. buffer分割线：bufferline.nvim;
14. 左侧git提示：gitsigns.nvim;
15. 文件检索：telescope.nvim;
