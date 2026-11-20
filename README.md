# qbittorrent-nox-static-backup

qbittorrent-nox 靜態編譯執行檔備份，Linux x86_64，qBittorrent 4.1.9 到 4.6.7，搭配不同版本的 libtorrent。

檔案都在 [Releases](https://github.com/lk86jeff/qbittorrent-nox-static-backup/releases)，依系列分成 `4.1` 到 `4.6` 六個 Release，每個 Release 附 `SHA256SUMS`。

## 檔名規則

`x86_64-qbittorrent-nox-<qBittorrent 版本>-lt<libtorrent 版本>[-glibc|-musl][-cmake][-icu]`

## 用法

```bash
wget -O qbittorrent-nox https://github.com/lk86jeff/qbittorrent-nox-static-backup/releases/download/4.3/x86_64-qbittorrent-nox-4.3.9-lt1.2.15
sudo install -m 755 qbittorrent-nox /usr/local/bin/qbittorrent-nox
qbittorrent-nox --version
```

## 說明

- 這些不是官方發行檔，是早期第三方靜態編譯的備份，編譯者不明，請自行評估後使用。
- 舊版本內含的函式庫不會再更新。
- qBittorrent 以 GPL-2.0-or-later 授權，原始碼：https://github.com/qbittorrent/qBittorrent （各版本對應 `release-<版本>` tag）。libtorrent 原始碼：https://github.com/arvidn/libtorrent
