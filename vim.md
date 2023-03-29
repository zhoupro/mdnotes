
where put config file.
echo stdpath("config")

:exe "edit" stdpath("config") . "/init.lua"

:edit $MYVIMRC

:help option-list
:help 'option_name'

绝对行号
set number
相对行号
方便使用 hljk
set relativenumber

缩进

editorconfig/editorconfig-vim
.editorconfig
[*.py]
indent_style = space
indent_size = 4

