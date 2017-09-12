## 1. 代码格式问题：
#### 这个文件 weather_api.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -22,16 +22,21 @@
 unit = 'c'
 i = 0
 
-def fetch_weather(location, unit):# 用requests库，与API交互并获取信息
-    result = requests.get('https://api.seniverse.com/v3/weather/daily.json', params={
+
+def fetch_weather(location, unit):  # 用requests库，与API交互并获取信息
+    result = requests.get(
+        'https://api.seniverse.com/v3/weather/daily.json',
+        params={
             'key': 'aavbujnax07w0irk',
             'location': location,
             'language': 'zh-Hans',
             'unit': unit
-        }, timeout=20) 
+        },
+        timeout=20)
     return result
-    
-def show_weather(result, i): # 处理JSON格式信息
+
+
+def show_weather(result, i):  # 处理JSON格式信息
     jd = json.loads(result.text)
     for info in jd['results']:
         date = info['daily'][i]['date']
@@ -41,21 +46,23 @@
         low = info['daily'][i]['low']
         wind_direction = info['daily'][i]['wind_direction']
         wind_scale = info['daily'][i]['wind_scale']
-        weather_str = '{}\n{}白天{},夜晚{}。\n最高气温{}度,最低气温{}度\n{}风{}级。\n'.format(date, order, text_day, text_night, high, low, wind_direction, wind_scale)
+        weather_str = '{}\n{}白天{},夜晚{}。\n最高气温{}度,最低气温{}度\n{}风{}级。\n'.format(
+            date, order, text_day, text_night, high, low, wind_direction,
+            wind_scale)
         return weather_str
-        
+
+
 while True:
     order = input('请输入指令或您要查询的城市名：')
-    try:# 显示查询信息，并保存到history列表中
+    try:  # 显示查询信息，并保存到history列表中
         result = fetch_weather(order, unit)
         weather_str = show_weather(result, i)
         print(weather_str)
         history_list.append(weather_str)
-        
+
     except KeyError:
         if order in ['h', 'help']:
-            print(
-            '''
+            print('''
                 输入城市名，查询该城市的天气；
                 输入 help, 获取帮助文档；
                 输入 history, 获取查询历史；
@@ -65,19 +72,18 @@
                 输入 1，查询明天天气；
                 输入 2，查询后天天气。
                 输入 quit, 退出天气查询系统。
-            '''        
-            )
-        
+            ''')
+
         # 切换到摄氏度
         elif order == 'c':
             unit = order
             print('已切换到摄氏度\n')
-        
+
         # 切换到华氏度
         elif order == 'f':
             unit = order
             print('已切换到华氏度\n')
-           
+
         # 指定查询今天天气
         elif order == '0':
             i = 0
@@ -102,4 +108,4 @@
             break
 
         else:
-            print('没有该城市信息!请输入help查看帮助文档。') +            print('没有该城市信息!请输入help查看帮助文档。')
```

</details>


## 2. 代码相似问题：


## 3. 复杂度及其他问题：