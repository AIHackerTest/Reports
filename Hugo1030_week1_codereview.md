## 1. 代码格式问题：
#### 这个文件 weather_info.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -16,31 +16,29 @@
     # 查询城市天气，并将查询结果存入字典
     if order in weather_dic.keys():
         weather = weather_dic[order]
-        history_dic[order] = weather #保存查询结果
+        history_dic[order] = weather  #保存查询结果
         print('{}的天气状况为：{}'.format(order, weather))
 
     # 查询帮助信息
     elif order in ['h', 'help']:
-        print(
-        '''
+        print('''
             输入城市名，查询该城市的天气；
             输入 help, 获取帮助文档；
             输入 history, 获取查询历史；
             输入 quit, 退出天气查询系统。
-        '''        
-        )
+        ''')
 
     # 查询历史记录
     elif order in ['history']:
         for order in history_dic:
             print(order, history_dic[order])
-    
+
     # 返回历史记录，退出程序
     elif order in ['quit', 'q']:
         print("显示查询结果，退出程序！")
         for order in history_dic:
             print(order, history_dic[order])
         break
-        
+
     else:
-        print('没有该城市信息!请输入help查看帮助文档。') +        print('没有该城市信息!请输入help查看帮助文档。')
```

</details>


## 2. 代码相似问题：


## 3. 复杂度及其他问题：