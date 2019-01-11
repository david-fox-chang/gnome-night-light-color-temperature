# gnome-night-light-color-temperature

這是一個支援 `gnome 桌面系統的` 簡易 `螢幕夜光色溫調整工具`，基於指令行運行

記得請開啟夜光模式，這工具才有用喔

```bash
git clone https://github.com/david-fox-chang/gnome-night-light-color-temperature.git 夜光模式色溫調整
cd 夜光模式色溫調整
chmod u+x gnome-night-light-color-temperature;

./gnome-night-light-color-temperature --help
```

## 取得當前夜光色溫

> 此為 `預設行為` 不必加 `--get` 選項即可見

```bash
./gnome-night-light-color-temperature
./gnome-night-light-color-temperature --get
```

## 設定夜光色溫

> 設定色溫為 5500k

```bash
./gnome-night-light-color-temperature --set 5500
```

> 設定色溫為 自訂定義設定值

```bash
./gnome-night-light-color-temperature --set <some comsumer config name>

# 範例，work_tv是我接電視工作所使用的設定檔
./gnome-night-light-color-temperature --set 'work_tv'
```

## 自訂設定值

> 目前是放在本 script 中，約在本 script 中 ` 355 行` 左右的區域

可以在「使用者設定值」區域中，使用

`set_user_config $name $value $description`

該區域有範例可看

> 當然可以改寫成外連設定檔，起初只是想簡單使用而已有需要再開個 issue 跟我說，我找時間改
