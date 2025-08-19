" =========================
" CONFIGURACIÓN GENERAL
" =========================
set nocompatible
syntax on
set background=dark
set number

" Recordar posición del cursor al volver a abrir un archivo
if has("autocmd")
   au BufReadPost * if line("'\"") > 1 && line("'\"") <= line("$") | exe "normal! g'\"" | endif
endif

" =========================
" PLUGINS (usa :PlugInstall para instalarlos)
" =========================
call plug#begin('~/.vim/plugged')

" Explorador de archivos
Plug 'preservim/nerdtree'

Plug 'scottmckendry/cyberdream.nvim', {'as':'cyberdream'}
" Barra de estado
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'

" Autocompletado
Plug 'hrsh7th/nvim-cmp'
Plug 'hrsh7th/cmp-path'
Plug 'neovim/nvim-lspconfig'       " Configuración LSP
Plug 'hrsh7th/nvim-cmp'            " Motor de autocompletado
Plug 'hrsh7th/cmp-nvim-lsp'        " Fuente: LSP
Plug 'hrsh7th/cmp-buffer'          " Fuente: buffer
Plug 'hrsh7th/cmp-path'            " Fuente: rutas
Plug 'hrsh7th/cmp-cmdline'         " Fuente: comandos
Plug 'L3MON4D3/LuaSnip'            " Snippets
Plug 'saadparwaiz1/cmp_luasnip'    " Snippets + autocompletado


" LSP para Java
Plug 'neovim/nvim-lspconfig'
Plug 'mfussenegger/nvim-jdtls'

" Formateo de código
Plug 'mhartington/formatter.nvim'

call plug#end()

set background=dark
colorscheme cyberdream
"let g:airline_theme='dracula'
" =========================
" ATAJOS
" =========================
" NERDTree con <leader>e
nnoremap <leader>e :NERDTreeToggle<CR>

" Atajo para formatear con google-java-format
command! FormatJava execute '%!google-java-format -'
nnoremap <leader>f :FormatJava<CR>
