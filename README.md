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
./gnome-night-light-color-temperature --set <some customer config name>

# 範例，work_tv是我接電視工作所使用的設定檔。色溫值是：5500k
./gnome-night-light-color-temperature --set 'work_tv'
```

## 簡易版的連續設定模式

> 因為剛開始設定色溫時一定需要嘗試，但一直重複輸入指令會讓 `~/.bash_history` 陷入災難性的重複指令，所以用這設定比較簡單

```bash
./gnome-night-light-color-temperature --loop-setting
```

進到 `loop-setting` 模式後會看到 `幫助(h) 離開(q) >`

比方說，我想要設定色溫在 6000

```
幫助(h) 離開(q) > s 6000
```

或是使用自訂色溫值 work_tv

```
幫助(h) 離開(q) > s 'work_tv'
```

這樣即可。

使用說明按下 `h`


## 複雜版的連續設定模式

有查詢自訂設定列表等功能，使用說明按下 `h`

```bash
./gnome-night-light-color-temperature --loop-subshell
```

> 本模式亦可以設定色溫、查詢當前色溫等，使用方式跟 `簡易版的連續設定模式` 很像，不在此贅述

### 查詢自訂設定

1. 例如，查詢自訂設定的 `描述 (desc)` 中，包含有 `工作` 的設定值

```
幫助(h) 離開(q) > query-user-configs desc 工作

      設 定 名 稱  設定值  敘述內容
 ---------------- -------- ----------------
          work_28    5300  接m2870v工作
          work_tv    5500  接電視工作
```

2. 例如，查詢自訂設定的 `設定名稱 (name)` 是不是有 `work_tv`

```
幫助(h) 離開(q) > query-user-configs name work_tv

      設 定 名 稱  設定值  敘述內容
 ---------------- -------- ----------------
          work_tv    5500  接電視工作
```

3. 例如，查詢自訂設定的 `設定值 (value)` 是不是有 `5000K` 色溫值

```
幫助(h) 離開(q) > query-user-configs value 5000

      設 定 名 稱  設定值  敘述內容
 ---------------- -------- ----------------
          leisure    5000  休閒

```

### 列出建議色溫配置

```
幫助(h) 離開(q) > list-recommands
```

## 自訂設定值

> 目前是放在本 script 中，約在本 script 中 ` 355 行` 左右的區域

可以在「使用者設定值」區域中，使用

`set_user_config $name $value $description`

該區域有範例可看

> 當然可以改寫成外連設定檔，起初只是想簡單使用而已有需要再開個 issue 跟我說，我找時間改
