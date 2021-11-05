# Windows 完全求生指南

這份文件的產生是因為我最近工作筆電換成了公司配的 ThinkPad X1 Carbon，所以工作環境從 macOS
變成了 Windows。作為一個平常工作大量依賴鍵盤與 Commandline 的人， 一定要想辦法打造一個
舒適的工作環境，想辦法活下去！

如果你覺得有什麼更好用的競品，或是覺得很實用的軟體都歡迎開 issue 提供、討論。

## 實用工具

### [PowerToys](https://github.com/microsoft/PowerToys)

- 絕對不只是 Toys！
- PowerToys Run 可以取代 Wox
- FancyZones 可以快速排列視窗到預先規劃好的區域
- File Explorer Add-ons 可以讓檔案管理員預覽 Markdown 跟 SVG
- Keyboard Manager 可以 re-map 鍵盤按鍵

### [Wox](http://www.wox.one/)

- 把 Spotlight 帶到 Windows 上！
- 把預設的 HotKey 改成 Ctrl-Alt-Space，因為 Alt-Space 去移動、縮放視窗很好用
- 其他競品
	- [Ueli](https://ueli.app/)

> TODO: 附上 Wox 設定檔

### [ShareX](https://getsharex.com/)

- Windows 內建的 PrtScrn 有夠爛，這工具用起來就像 Mac 的截圖 Command-Shift-3
- 其他競品
	- [LightShot](https://app.prntscr.com/)
	- [Win-Shift-S](https://support.microsoft.com/help/4488540/windows-10-how-to-take-and-annotate-screenshots)

### [Everything](https://www.voidtools.com/)

- 你不會想用 Windows 內建的搜索功能的...
- 裝好就可以[關掉 Windows 內建的 search service](https://j.mp/disable-windows-search-service)
- 裝了之後直接設定開機自動啟動，或是 Run as Service
- 我自己設定了 HotKey Ctrl-Alt-F

### [Stardock Fences](https://www.stardock.com/products/fences/)

- 老牌軟體，讓你的桌面井然有序，不過要付費
- 不想付錢可以試試 [Nimi Places](https://www.playpcesor.com/2013/07/nimi-places.html) 或其他替代品

## Terminal Emulator

### [Windows Terminal](https://github.com/microsoft/terminal)

- 微軟官方推出的新一代 Terminal，支援 GPU 加速
- 唯一缺點是，把檔案拖拉到 Windows Terminal 視窗內的時候，不會自動轉換成 `/mnt/` 的路徑，但是 WSLTTY 可以

設定檔在這： [windows-terminal-settings.json](windows-terminal-settings.json)

我做了一個程式，註冊一個 global hotkey 來切換 Windows Terminal，行為有點像 iTerm2 的 `Toggle All Windows`，
可以在 [Inndy/TerminalSummoner](https://github.com/Inndy/TerminalSummoner) 找到

### [WSLTTY](https://github.com/mintty/wsltty)

### [Cmder](https://cmder.net/)

- ~~Windows 最強 Terminal Emulator~~ 我覺得不容易設定
- 支援 cmd / PowerShell / WSL / cygwin

## Package Manager

### [scoop](https://scoop.sh/)

- 看到有人推薦 [OneGet](https://github.com/OneGet/oneget)，但是我沒用過
- 類似 `brew` 的做法，會把 Windows 軟體包直接拆開，裝在 `%UserProfile%\scoop` 底下
- `scoop install aria2; scoop config aria2-enabled true`
- `scoop install ag busybox fd file git gzip jq less ln neovim psutils shasum sqlite sudo tar touch which xz`

### [Chocolatey](https://chocolatey.org/)

- 以前用 Chocolatey 經驗不好，後來也沒有繼續嘗試
- 套件比 scoop 更多

## Windows Subsystem Linux

### [WSL安裝指南](https://docs.microsoft.com/zh-tw/windows/wsl/install-win10)

- 我太習慣 Unix 環境跟 Commandline 的工作環境了
- 現在的 WSL 我覺得已經發展到超過堪用的程度了

### [Linuxbrew](http://linuxbrew.sh/)

- macOS 的第三方套件管理程式 [Homebrew](https://brew.sh/) 也支援 Linux
- 除非你用 [Arch Linux](https://www.archlinux.org/)，不然 brew 的套件版本一定比較新
- `brew install nvim tmux`

### 系統剪貼簿

把以下兩行加入你的 `~/.bashrc` （或你自己的 shell rc）

``` bash
alias paste="powershell.exe -Command Get-Clipboard"
alias copy="powershell.exe -Command 'Set-Clipboard([Console]::In.ReadToEnd())'"
```

*Windows 貼上的換行會是 `\r\n`，要 pipe 到其他地方使用可以先 `tr -d \\r`*

## Windows 系統調整

- 關掉 [Windows Telemetry](https://www.neweggbusiness.com/smartbuyer/windows/should-you-disable-windows-10-telemetry/)
	- [O&O ShutUp10](https://www.oo-software.com/en/shutup10)
- 關掉 [Windows Defender](https://www.windowscentral.com/how-permanently-disable-windows-defender-windows-10)
	- **<span style="color: red">⚠️⚠️⚠️ 除非你知道自己在做什麼，也知道為什麼要關掉
      Windows Defender，不然不建議這麼做。事實上， Windows Defender
      是一個很棒的防毒軟體！</span>**
	- MsMpEng 真的吃掉太多資源，也造成執行程式的卡頓，WSL 效能低落，i7 變 i3 不誇張
- 關掉 [索引服務](https://www.online-tech-tips.com/computer-tips/simple-ways-to-increase-your-computers-performace-turn-off-indexing-on-your-local-drives/)
	- Everything 不管是建立索引還是搜尋速度都完勝，也不會一直吃效能

## 快捷鍵

[Windows Shortcuts by @moskytw](https://paper.dropbox.com/doc/Windows-Shortcuts-Moskys-Notes-2xHBugmq1xnYtBhhcnHmW)

## Misc

### [剪貼簿歷程](https://support.microsoft.com/zh-tw/help/4464215/windows-10-get-help-with-clipboard)

- Windows 10 新增的剪貼簿歷史紀錄功能

### [clong/MakeWindows10GreatAgain](https://github.com/clong/MakeWindows10GreatAgain)
### [Sycnex/Windows10Debloater](https://github.com/Sycnex/Windows10Debloater)

- 裡面有很多值得參考的 tweak 跟懶人 script
