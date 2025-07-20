# nvim-call-hierarchy

## インストール

### lazy.nvim を利用する場合
```lua
{
  "yourname/nvim-call-hierarchy",
  dependencies = {
    "nvim-lua/plenary.nvim",
    "nvim-tree/nvim-web-devicons",
  },
}
```

### vim-plug を利用する場合
```vim
Plug 'yourname/nvim-call-hierarchy'
Plug 'nvim-lua/plenary.nvim'
Plug 'nvim-tree/nvim-web-devicons'
```

### packer.nvim を利用する場合
```lua
use {
  'yourname/nvim-call-hierarchy',
  requires = {
    'nvim-lua/plenary.nvim',
    'nvim-tree/nvim-web-devicons',
  }
}
```

Neovim 0.10.0 以上が必要です。

## 開発環境構築

1. リポジトリをクローンします。
   ```bash
   git clone https://github.com/yourname/nvim-call-hierarchy.git
   ```
2. Lua とテストツールをインストールします。
   ```bash
   sudo apt-get install -y lua5.1 luarocks
   sudo luarocks install busted
   ```
3. 依存プラグイン(plenary.nvim, nvim-web-devicons)をインストールします。
   ```bash
   git clone https://github.com/nvim-lua/plenary.nvim \
     ~/.local/share/nvim/site/pack/deps/start/plenary.nvim
   git clone https://github.com/nvim-tree/nvim-web-devicons.git \
     ~/.local/share/nvim/site/pack/deps/start/nvim-web-devicons
   ```
4. `nvim-call-hierarchy` を runtimepath に追加し、Neovim 0.10.0 以降で読み込みます。
   開発中はシンボリックリンクで追加すると便利です。
   ```bash
   ln -s $(pwd) ~/.local/share/nvim/site/pack/deps/start/nvim-call-hierarchy
   ```
5. Language Server をインストールし、Neovim 上でプラグインの動作を確認します。
   ```bash
   nvim --headless -c 'MasonInstall lua-language-server rust-analyzer jdtls tsserver' +qa
   ```
