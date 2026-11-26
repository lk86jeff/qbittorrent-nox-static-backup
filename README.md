# qbittorrent-nox-static-backup

qbittorrent-nox 靜態編譯執行檔備份，Linux x86_64，qBittorrent 4.1.9 到 4.6.7，搭配不同版本的 libtorrent。

**備份庫的執行檔全部適用於 Linux x86_64（amd64，64 位元 x86）架構。** 這裡沒有 32 位元 x86 或 ARM／ARM64 版本；其他架構請查看上游的發布頁面。

檔案都在 [Releases](https://github.com/lk86jeff/qbittorrent-nox-static-backup/releases)，依系列分成 `4.1` 到 `4.6` 六個 Release，每個 Release 附 `SHA256SUMS`。

## 檔案來源與比對

這些檔案是我從 [Aniverse 的 SourceForge 目錄](https://sourceforge.net/projects/inexistence/files/qbittorrent/)和 [userdocs/qbittorrent-nox-static 的 GitHub Releases](https://github.com/userdocs/qbittorrent-nox-static/releases)下載保存的。

2026 年 11 月 27 日，我核對了備份庫全部 134 個檔案：

- 9 個檔案與 SourceForge 頁面公布的 SHA-256 一致，包括 4.1、4.2 系列的 8 個檔案，以及 4.3.0／libtorrent 1.2.10 的檔案。
- 其餘 125 個檔案與 userdocs 的 GitHub Release 檔案一致。我從 71 個 Release 下載 200 個 x86_64／amd64 候選檔案，計算 SHA-256 後，與本備份庫 Release 提供的雜湊比對。

[逐檔比對表](https://jeffhsieh.com/downloads/qbittorrent-sha256-comparison-2026-11-27.tsv)列出上游檔名、SHA-256、對應的備份檔案與來源連結。[備份說明文章](https://jeffhsieh.com/posts/qbittorrent-nox-backup-pt/)也有上游 Release 的截圖與使用說明。

SHA-256 一致表示比對的檔案內容一致。上游仍保留部分舊版，例如 [4.3.9／libtorrent 1.2.14](https://github.com/userdocs/qbittorrent-nox-static/releases/tag/release-4.3.9_v1.2.14)；可用版本以上游頁面為準。

## 檔名規則

`x86_64-qbittorrent-nox-<qBittorrent 版本>-lt<libtorrent 版本>[-glibc|-musl][-cmake][-icu]`

## 用法

```bash
wget -O qbittorrent-nox https://github.com/lk86jeff/qbittorrent-nox-static-backup/releases/download/4.3/x86_64-qbittorrent-nox-4.3.9-lt1.2.15
sudo install -m 755 qbittorrent-nox /usr/local/bin/qbittorrent-nox
qbittorrent-nox --version
```

## 說明

- 這些是第三方靜態編譯檔案的備份，並非 qBittorrent 官方發行檔，請自行評估後使用。
- 舊版本內含的函式庫不會再更新。
- qBittorrent 以 GPL-2.0-or-later 授權，原始碼：https://github.com/qbittorrent/qBittorrent （各版本對應 `release-<版本>` tag）。libtorrent 原始碼：https://github.com/arvidn/libtorrent
