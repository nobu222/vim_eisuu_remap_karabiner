# vim_eisuu_remap_karabiner

vim使用時の日本語入力を選択状態で、escapeキーもしくはcontrol+[の実行時に英数キーをはさむ

Karabiner の設定ファイルの作成(iTerm2,MacVim,Terminalに対応)

```
<?xml version="1.0"?>
<root>
    <appdef>
        <appname>MacVIM</appname>
        <equal>org.vim.MacVim</equal>
    </appdef>
    <appdef>
        <appname>TERMINAL</appname>
        <equal>com.apple.Terminal</equal>
    </appdef>
    <appdef>
        <appname>ITERM2</appname>
        <equal>com.googlecode.iterm2</equal>
    </appdef>
    <windownamedef>
        <name>VIM</name>
        <regex>.* - VIM.*</regex>
    </windownamedef>
    <item>
        <name>Private Mapping</name>
        <item>
            <name>Custom Vim Change CONTROL_L+BRACKET_RIGHT+EISUU</name>
            <identifier>private.control_bracket_plus_eisuu</identifier>
            <only>MacVIM,TERMINAL,ITERM2</only>
            <windowname_only>VIM</windowname_only>
            <autogen>
                __KeyToKey__
                KeyCode::BRACKET_RIGHT, ModifierFlag::CONTROL_L,
                KeyCode::JIS_EISUU, KeyCode::BRACKET_RIGHT, ModifierFlag::CONTROL_L
            </autogen>
        </item>
        <item>
            <name>Custom Vim Change ESC+EISUU</name>
            <identifier>private.escape_plus_eisuu</identifier>
            <only>MacVIM,TERMINAL,ITERM2</only>
            <windowname_only>VIM</windowname_only>
            <autogen>
                __KeyToKey__
                KeyCode::ESCAPE,
                KeyCode::JIS_EISUU, KeyCode::ESCAPE
            </autogen>
        </item>
    </item>
</root>
```
