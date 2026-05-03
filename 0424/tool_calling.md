# 加分作業

## Prompt 1

> 請使用工具查詢今天台北的天氣，並回覆目前溫度、天氣狀況、降雨機率與資料來源。

回答：
🌐 browser_navigate: "https://www.google.com/search?q=台北天氣"
I'm sorry, but I encountered a CAPTCHA page again when trying to access Google Weather. It seems Google is blocking my access due to unusual traffic. I cannot proceed with this method.
Would you like me to try a different weather website, or is there another way you'd like me to find this information?

`他自動使用 google ，但 Google 擋自動瀏覽`

## Prompt 2

> 請不要使用 Google。請使用工具打開中央氣象署網站查詢今天台北市天氣，並回覆目前溫度、天氣狀況、降雨機率與資料來源。

回答：
🌐 browser_navigate: "https://www.cwa.gov.tw/"
📸 browser_snapshot...
好的，這是在中央氣象署網站查詢到的台北市今天（5月3日）的天氣資訊：

- 目前溫度：白天約 28°C 至 33°C，晚間至隔天清晨約 22°C 至 28°C，隔天白天約 21°C 至 24°C。
- 天氣狀況：
  - 今日白天：多雲短暫陣雨或雷雨
  - 今晚明晨：陰時多雲短暫陣雨或雷雨
  - 明日白天：陰短暫陣雨或雷雨
- 降雨機率：
  - 今日白天：30%
  - 今晚明晨：80%
  - 明日白天：40%
- 資料來源：交通部中央氣象署 (CWA)

請問您對於今天的台北市天氣還有其他想了解的嗎？

`換成中央氣象局就正常顯示了`

## 對話截圖

![image](https://github.com/linda123456789123456789/GAI-for-Humanities/blob/main/0424/google.jpg?raw=true)

![image](https://github.com/linda123456789123456789/GAI-for-Humanities/blob/main/0424/%E6%B0%A3%E8%B1%A1%E5%B1%80.jpg?raw=true)
