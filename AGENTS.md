# cdda

此資料夾存放從實體 CD 轉出的 MP3，並非程式碼專案。

## 內容

- `愛哭公主/`、`勇氣小火車/`、`十二生肖/` — 各光碟的 MP3 輸出
- 打包過的加密 zip 在 `/home/dany/projs/cdda_mp3.zip`

## 環境備忘（重灌或換機需重裝）

- 光碟機 `/dev/sr0`，抓軌工具：`abcde`、`cdparanoia`、`lame`、`ffmpeg`、`eyed3`、`id3v2`
- 提示：`abcde` 這台的 CDDB/musicbrainz 查不到資料會 abort(`abcde-musicbrainz-tool failed`)，改用 `cdparanoia -B` 抓 WAV 再 `ffmpeg -b:a 320k` 轉 MP3
- 讀不到光碟時先 `eject -t /dev/sr0` 關托盤，或請使用者手動退出重放
- 抓 CDDA raw 用 `cdparanoia ... file.raw`，轉檔需指定 `-f s16le -ar 44100 -ac 2`
- 加密分享用 `zip -e`（ZipCrypto），iPhone 內建「檔案」App 才解得開；AES 加密的 7z 不行

## 既有規則（全域，來自 ~/.config/opencode/AGENTS.md）

- 禁止直接 commit 到 main；先開分支、測試與 typecheck 通過才能合併
