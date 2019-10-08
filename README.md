
## 專題題目

2D平台遊戲 - 以化學和解謎為主軸，遊戲元素包含了跑酷及戰鬥等。

## 專題需求

1. 開場動畫
2. 主選單
3. 道具系統
4. 設定選單
5. 對話系統
6. 存檔系統
7. 關卡設計

## 功能性與非功能性需求

* ### 功能性需求

```
存檔
道具使用
按鍵設定
角色對話
戰鬥系統
陷阱機關
怪物
```

* ### 非功能性需求

```
存檔加密
載入速度優化
```
# Use case diagram

![安安廢物](usediagram.jpg "安安廢物")

# 使用案例重要性排序

1. Map
2. Enemy
3. Save / Load
4. Dialogue
5. Debug console

# 至少三個使用案例

1.Map
  
  主要路徑
  
  1.進入遊戲由時掃描所有scene，並將連結關係存入陣列  
  2.當玩家進入此scene，將其scene"已探索"設為true，並回存陣列  
  3.當玩家於選單中使用"地圖"按鈕，將所有scene依序畫出，並顯示於螢幕。  
  
  替代路徑  
  
  2.1若地圖"已探索"已經為true，則不做反應。  

2.Enemy  

  主要路徑  
  
  1.當玩家經過"紀錄器"時運行"存檔"函式  
  2.呼叫所有標有"需存取"的Node，進行其函式  
  3.將回傳的資料轉存進陣列，並輸出成.tres檔  
  4.於選單中進行"返回上個存檔"，運行"讀取"函式  
  5.讀取路徑中的tres檔案，並將資料回傳。  
  
  替代路徑
  
  3.1若檔案已存在，則進行覆蓋  
  4.1若檔案不存在，則此功能無法使用  

3.Save / Load

  主要路徑
  
  1.於生成點進行生成  
  2.檢測範圍內是否有玩家存在  
  3.若存在，則鎖定其目標進行移動  
  4.進入攻擊範圍內，則進行攻擊  
    
  替代路徑
  
  2.1若目標不存在，則進行隨機的移動  

# User Story

* 身為一個{{玩家}}，我希望遊戲要有{{存檔功能}}，讓我能夠{{存檔}}不用每次重來。

* 身為一個{{玩家}}，我希望遊戲有{{敵人}}，能夠讓我跟他{{戰鬥}}。

* 身為一個{{玩家}}，我希望遊戲有{{地圖}}，能夠容納我的{{角色}}，讓他跑跑跳跳。

* 身為一個{{遊戲開發者}}，我希望遊戲裡能有{{除錯視窗}}，讓我便於{{偵錯}}。

# 初步類別圖
![安安廢物](初步流程圖.png "安安廢物")

# 系統循序圖
![安安廢物](系統循序圖.png "安安廢物")
