# 檔案說明

- `UrSchool教授資料.xlsx`: UrSchool原始教授資料
- `人氣教授養成指南.Rmd`: 程式原始碼，詳細資訊在下方有更詳細的說明
- `人氣教授養成指南.html`: 原始碼輸出網頁的結果
- `style.css`: 設定HTML排版

# 原始碼說明

## 資料前處理

- `show_raw_data/`: 原始資料以及資料前處理
- `score_converter/`: 平均成績轉換分數之函數
- `major_converter/`: 系所整合函數
- `position_converter/`: 職稱整合函數
- `get_department/`: 將同一學院之系所做歸類
- `data/`: 經前處理過後之全部資料（包含上述學院歸納）

## 量化分析

### 各系所各項指標分析

- `by_department/`: 去除NA資料之data
- `department/`: 所有學院之vector
- `department_average/`:計算各學院之平均分數
- `depart_score_analysis/`: 各學院平均分數表格化

### 各項指標與私心推薦指數的相關性

- `regression_result/`: 私心推薦分數與其他指標間的線性相關
- `score/`: 包含私心推薦分數與經由與其他指標的線性相關獲得之推薦私心分數預估dataframe
- `predict_result/`: score之視覺化結果
- `position_converter/`: 職稱整合函數
- `get_department/`: 將同一學院之系所做歸類
- `data/`: 經前處理過後之全部資料（包含上述學院歸納）

### 土博士 v.s. 洋墨水

- `type/`: 最高學歷項目的本土與非本土歸納
- `TW`: 辨識為本土學歷之中文關鍵字
- `tw`:辨識為本土學歷之英文關鍵字 
- `data_with_type/`:包含type項目之data，且去除type與私心推薦項目之NA值
- `私心推薦分數/`: data_with_type資料屬性化為character之私心推薦項目

### 教授有綽號是否代表與學生比較喜歡？

- `nickname/`: 教授有無綽號之歸納
- `named/`: nickname中被歸類為有綽號之資料
- `named_data/`: data中去除綽號項目為NA之結果
- `ranking/`: named_data資料屬性化為character之私心推薦項目

## 語意分析

### 學生最重視什麼？

- `comment/`: data中篩選姓名與評論項目，並去除NA值
- `get_adj/`: 取得形容詞的函數
- `get_segged_text/`: 對每個教授的評論斷詞的函數
- `comment_df/`: 將每個評論的斷詞串起來
- `tidy_text_format/`: comment_df整理
- `text_final/`: 抓出前 30 個最常出現的形容詞
- `important_personality/`: 評論中最常出現的詞彙前30名的圖表
- `wordcloud/`: 上述圖表之文字雲圖
- `major_converter/`: 系所整合函數
- `position_converter/`: 職稱整合函數
- `get_department/`: 將同一學院之系所做歸類
- `data/`: 經前處理過後之全部資料（包含上述學院歸納）

### 學生最重視什麼？（各個學院）

- `usually/`: ˋ各學院及其最常出現之形容詞
- `important_department/`: 留言者在評論各學院教授時最常使用的形容詞之表格
- `high_review/`: 私心推薦教授分數為5分之教授與其評論
- `low_review/`: 私心推薦分數小於或等於3分之教授與其評論
- `important_personality_high_score/`: 留言者在評論私心推薦教授分數為5分的教授時最常使用的形容詞之表格
- `important_personality_low_score/`: 留言者在評論私心推薦分數小於或等於3分的教授時最常使用的形容詞之表格
