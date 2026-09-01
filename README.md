# PJSK Automatic Image Combination Library

個人 Discord bot 用的**圖片快取庫**。這裡存放的是由程式自動合成的圖片，
供 bot 在 Discord 訊息中以圖片連結引用。

> **此庫僅供該 bot 自身引用，不開放使用、轉載或散布。**
> This repository is a private-use image cache for a personal Discord bot.
> **Not for redistribution or reuse.**

---

## 這裡為什麼會存在

Discord 的附件連結自 2024 年起帶有簽章並會在 24 小時後失效，
無法作為長期引用的圖片來源。因此改由此庫託管，取得穩定的連結。

## 目錄結構

以**遊戲資料表的編號**作為目錄，一個編號一個資料夾：

```
gacha/{gachaId}/pu.png       該卡池的 PU（機率上升）成員合成圖
gacha/{gachaId}/ceil.png     該卡池天井可兌換成員的合成圖
event/{eventId}/...          活動相關的合成圖
index.json                   每張圖的對應資料：來源卡片編號、產生時間、素材版本
```

用編號而不用名稱當目錄，是因為名稱會變——同一個卡池復刻時會多出「[復刻]」前綴，
編號則是固定的。同一個卡池的各種圖放在同一個資料夾底下，之後要新增圖片種類
（例如整組卡面、費用表）不必改動既有結構。

`index.json` 讓 bot 不必猜檔案存不存在，也記錄了每張圖是用哪一版素材產的，
素材更新後可以一眼看出哪些圖需要重產。

---

## 圖片來源

合成圖由下列**公開資料與素材**疊合而成，本庫不包含任何原始素材檔案：

| 用途 | 來源 |
|---|---|
| 角色卡面縮圖 | [storage.sekai.best](https://storage.sekai.best/) |
| 卡框、屬性圖示、星等 | 遊戲內 UI 素材（版權見下） |
| 卡片與卡池資料 | [Sekai-World/sekai-master-db-tc-diff](https://github.com/Sekai-World/sekai-master-db-tc-diff) |

## 版權與免責聲明

本庫所含圖片係由《世界計畫 繽紛舞台！ feat. 初音未來》
（プロジェクトセカイ カラフルステージ！ feat. 初音ミク）之遊戲素材合成。

- 遊戲素材之著作權及一切權利均歸 **SEGA CORPORATION** 與 **Craft Egg / Colorful Palette Inc.**
  及其授權者所有。本庫與上述公司**無任何關聯**，亦非官方產物。
- 本庫為**非商業性**的個人用途快取，不販售、不提供下載服務、不用於任何營利行為。
- 本庫**不授予**任何人使用、重製、散布或改作其中內容的權利。
- 若著作權利人認為本庫有侵權疑慮，請以 issue 或任何方式告知，**將立即移除**。

All game assets are © SEGA / Craft Egg / Colorful Palette Inc.
This repository is an unofficial, non-commercial personal cache and is
**not affiliated with or endorsed by** the rights holders.
No rights are granted to any third party. Upon request from the rights
holders, all content will be removed immediately.
