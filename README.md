# Windows 完全求生指南

這份文件的產生是因為我最近工作筆電換成了公司配的 ThinkPad X1 Carbon，所以工作環境從 macOS
變成了 Windows。作為一個平常工作大量依賴鍵盤與 Commandline 的人， 一定要想辦法打造一個
舒適的工作環境，想辦法活下去！

## 實用工具

### [Wox](http://www.wox.one/)

- 把 Spotlight 帶到 Windows 上！
- 把預設的 HotKey 改成 Ctrl-Alt-Space，因為 Alt-Space 去移動、縮放視窗很好用

### [LightShot](https://app.prntscr.com/)

- Windows 內建的 PrtScrn 有夠爛，這工具用起來就像 Mac 的截圖 Command-Shift-3

### [Everything](https://www.voidtools.com/)

- 你不會想用 Windows 內建的搜索功能的...
- 裝好就可以[關掉 Windows 內建的 search service](https://j.mp/disable-windows-search-service)
- 裝了之後直接設定開機自動啟動，或是 Run as Service
- 我自己設定了 HotKey Ctrl-Alt-F

### [Stardock Fences](https://www.stardock.com/products/fences/)

- 老牌軟體，讓你的桌面井然有序，不過要付費
- 不想付錢可以試試 [Nimi Places](https://www.playpcesor.com/2013/07/nimi-places.html) 或其他替代品

### [Cmder](https://cmder.net/)

- Windows 最強 Terminal Emulator
- 支援 cmd / PowerShell / WSL / cygwin
- 懶得設定 Cmder 的話可以用 [wsltty](https://github.com/mintty/wsltty)

### [scoop]()

- 以前用 [Chocolatey](https://chocolatey.org/) 經驗不好
	- 但是 scoop 上面的套件比較少
- 看到有人推薦 [OneGet](https://github.com/OneGet/oneget)，但是我沒用過
- 類似 `brew` 的做法，會把 Windows 軟體包直接拆開，裝在 `%UserProfile%\scoop` 底下

## Windows Subsystem Linux

### [WSL安裝指南](https://docs.microsoft.com/zh-tw/windows/wsl/install-win10)

- 我太習慣 Unix 環境跟 Commandline 的工作環境了
- 現在的 WSL 我覺得已經發展到超過堪用的程度了

### [Linuxbrew](http://linuxbrew.sh/)

- macOS 的第三方套件管理程式 [Homebrew](https://brew.sh/) 也支援 Linux
- 除非你用 [Arch Linux](https://www.archlinux.org/)，不然 brew 的套件版本一定比較新
- `brew install nvim tmux`
