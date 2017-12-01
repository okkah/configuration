"setting
"文字コードをUFT-8に設定
set fenc=utf-8
"バックアップファイルを作らない
set nobackup
"スワップファイルを作らない
set noswapfile
"編集中のファイルが変更されたら自動で読み直す
set autoread
"バッファが編集中でもその他のファイルを開けるように
set hidden
"入力中のコマンドをステータスに表示する
set showcmd

"見た目
"行番号を表示
set number
"現在の行を強調表示
set cursorline
"行末の1文字先までカーソルを移動できるように
set virtualedit=onemore
"インデントはスマートインデント
set smartindent
"ビープ音を可視化
set visualbell
"括弧入力時の対応する括弧を表示
set showmatch
"ステータスラインを常に表示
set laststatus=2
"コマンドラインの補完
set wildmode=list:longest
"折り返し時に表示行単位での移動できるようにする
nnoremap j gj
nnoremap k gk
"挿入モードでバックスペースが効かない時の対処
set backspace=indent,eol,start

"Tab
"不可視文字を可視化(タブが「▸-」と表示される)
set list listchars=tab:\▸\-
"Tab文字を半角スペースにする
set expandtab
"行頭以外のTab文字の表示幅（スペースいくつ分）
set tabstop=4
"行頭でのTab文字の表示幅
set shiftwidth=2

"検索
"検索文字列が小文字の場合は大文字小文字を区別なく検索する
set ignorecase
"検索文字列に大文字が含まれている場合は区別して検索する
set smartcase
"検索文字列入力時に順次対象文字列にヒットさせる
set incsearch
"検索時に最後まで行ったら最初に戻る
set wrapscan
"検索語をハイライト表示
set hlsearch
"ESC連打でハイライト解除
nmap <Esc><Esc> :nohlsearch<CR><Esc>

"色
syntax on
highlight Comment ctermfg=Darkgray
highlight Constant ctermfg=Darkyellow
highlight Identifier ctermfg=Yellow
highlight Statement ctermfg=Darkmagenta
highlight Title ctermfg=Darkmagenta
highlight Special ctermfg=Darkyellow
highlight LineNr ctermfg=Darkgray

"クリップボードからのペースト設定
if &term =~ "xterm"
    let &t_SI .= "\e[?2004h"
    let &t_EI .= "\e[?2004l"
    let &pastetoggle = "\e[201~"

    function XTermPasteBegin(ret)
        set paste
        return a:ret
    endfunction

    inoremap <special> <expr> <Esc>[200~ XTermPasteBegin("")
endif
"ヤンクした時に自動でクリップボードにコピー
set clipboard=unnamed,autoselect

"マウスの有効化
if has('mouse')
    set mouse=a
    if has('mouse_sgr')
        set ttymouse=sgr
    elseif v:version > 703 || v:version is 703 && has('patch632')
        set ttymouse=sgr
    else
        set ttymouse=xterm2
    endif
endif
