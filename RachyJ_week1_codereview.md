## 1. 代码格式问题：
#### 这个文件 batch_file_rename_issue.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -19,16 +19,24 @@
 
             os.rename(
                 os.path.join(work_dir, filename),
-                os.path.join(work_dir, newfile)
-            )
+                os.path.join(work_dir, newfile))
 
 
 def get_parser():
-        parser = argparse.ArgumentParser(description = 'change extension of files in a working directory')
-        parser.add_argument('work_dir', metavar = 'WORK_DIR', type = str, nargs = 1, help='the directory where to change extension')
-        parser.add_argument('old_ext', metavar = 'OLD_EXT', type = str, nargs = 1, help = 'old extension')
-        parser.add_argument('new_ext', metavar = 'NEW_EXT', type = str, nargs = 1, help = 'new extension')
-        return parser
+    parser = argparse.ArgumentParser(
+        description='change extension of files in a working directory')
+    parser.add_argument(
+        'work_dir',
+        metavar='WORK_DIR',
+        type=str,
+        nargs=1,
+        help='the directory where to change extension')
+    parser.add_argument(
+        'old_ext', metavar='OLD_EXT', type=str, nargs=1, help='old extension')
+    parser.add_argument(
+        'new_ext', metavar='NEW_EXT', type=str, nargs=1, help='new extension')
+    return parser
+
 
 def main():
     parser = get_parser()
@@ -40,5 +48,6 @@
 
     batch_rename(work_dir, old_ext, new_ext)
 
+
 if __name__ == '__main__':
     main()
```

</details>

#### 这个文件 ex40.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -1,17 +1,19 @@
 class Song(object):
-    def __init__(self,lyrics):
+    def __init__(self, lyrics):
         self.lyrics = lyrics
 
     def sing_me_a_song(self):
         for line in self.lyrics:
             print(line)
 
-happy_bday = Song(["Happy birthday to you",
-                    "I don't wan to get sued.",
-                    "So I'll stop right there"])
 
-bulls_on_parade = Song(["They rally around the family",
-                        "With pockets full of shells."])
+happy_bday = Song([
+    "Happy birthday to you", "I don't wan to get sued.",
+    "So I'll stop right there"
+])
+
+bulls_on_parade = Song(
+    ["They rally around the family", "With pockets full of shells."])
 
 happy_bday.sing_me_a_song()
 
```

</details>

#### 这个文件 ex42.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -2,6 +2,7 @@
 class Animal(object):
     ## a placeholder when a statement is required syntactically, but no code needs to be executed
     pass
+
 
 ## Dog is a class, inherit Animal
 class Dog(Animal):
@@ -10,12 +11,14 @@
         self.name = name
         print("The dog name is %s" % name)
 
+
 ## cat is a class, inherit Animal
 class Cat(Animal):
     def __init__(self, name):
         ## cat has a name
         self.name = name
         print("The cat name is %s" % name)
+
 
 ## person is a base class
 class Person(object):
@@ -28,7 +31,8 @@
         print("The name of the person is %s" % name)
         #print("He/She has a pet %s" % name.pet)
 
-## empoyee is a type of person
+
+    ## empoyee is a type of person
 class Employee(Person):
     def __init__(self, name, salary):
         ## run the init method of its parent class - Person
@@ -38,17 +42,21 @@
         print("%s earns how much each year" % name)
         print(salary)
 
+
 ## fish is an object
 class Fish(object):
     pass
+
 
 ## salmon is a fish
 class Salmon(Fish):
     pass
 
+
 ## halibut is a fish
 class Halibut(Fish):
     pass
+
 
 ## rover is a Dog
 rover = Dog("Rover")
@@ -58,7 +66,6 @@
 
 ## Mary is a person
 mary = Person("Mary")
-
 
 ## Mary's pet is satan
 mary.pet = satan
```

</details>

#### 这个文件 Google_News.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -2,6 +2,7 @@
 # Beautiful Soup 是一个可以从HTML或XML文件中提取数据的Python库
 from bs4 import BeautifulSoup as soup
 from urllib.request import urlopen
+
 
 def news():
     # specify the url of Google News RSS
@@ -16,16 +17,17 @@
     Client.close()
 
     # extract content as xml
-    soup_page = soup(xml_page,"xml")
+    soup_page = soup(xml_page, "xml")
     news_list = soup_page.findAll("item")
 
     for news in news_list:
         print(news.title.text)
         print(news.link.text)
         print(news.pubDate.text)
-        print("-"*150)
+        print("-" * 150)
 
     # What was the below line for?
     #n = input()
 
+
 news()
```

</details>

#### 这个文件 Print_List_of_Even_Numbers.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -1 +1 @@
-print ([x for x in range(int(input()),int(input())) if not x%2])
+print([x for x in range(int(input()), int(input())) if not x % 2])
```

</details>

#### 这个文件 SimpleStopWatch.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -5,12 +5,12 @@
 print('Press ENETER to begin, Press Ctrl + c to stop')
 while True:
     try:
-        input() #for ENETER
+        input()  #for ENETER
         starttime = time.time()
         print('Started: ')
     except KeyboardInterrupt:
         print('Stopped')
         endtime = time.time()
         # round 数字精确到两位
-        print('Total time:', round(endtime-starttime, 2), 'secs')
+        print('Total time:', round(endtime - starttime, 2), 'secs')
         break
```

</details>

#### 这个文件 weather_checker.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -5,46 +5,52 @@
 weather_dict = {}
 
 # source_data = open("weather_info.txt")
-with open("weather_info.txt", "r") as source_data:# optimize using with..as, not need to call close file
+with open(
+        "weather_info.txt", "r"
+) as source_data:  # optimize using with..as, not need to call close file
 
-	for item in source_data.readlines():
-		pair = item.split(',')
-		#print(pair)
-		city_item = pair.pop(0)
-		whether_item = pair.pop(-1)
-		# insert the data into the dict
-		weather_dict.update({city_item:whether_item})
+    for item in source_data.readlines():
+        pair = item.split(',')
+        #print(pair)
+        city_item = pair.pop(0)
+        whether_item = pair.pop(-1)
+        # insert the data into the dict
+        weather_dict.update({city_item: whether_item})
+
 
 def check_weather(query):
-	try:
-		print(weather_dict[query])
-		history.append(query)
+    try:
+        print(weather_dict[query])
+        history.append(query)
 
-	except:
-		print("City or command not found")
+    except:
+        print("City or command not found")
+
 
 def program_help():
-	print("""
+    print("""
 	 输入城市，获得天气信息；
 	 输入help或h，获得帮助提示；
 	 输入history，获取历史查询信息；
 	 输入exit，退出程序；
 	""")
 
+
 def get_history():
-	#print("history query info")
-	print(history)
+    #print("history query info")
+    print(history)
+
 
 while True:
-	query = input("请输入指令或您要查询的城市名：")
-	# print(query)
-	# history.append(query)
+    query = input("请输入指令或您要查询的城市名：")
+    # print(query)
+    # history.append(query)
 
-	if query =='help' or query =='h':
-		program_help()
-	elif query == 'history':
-		get_history()
-	elif query == 'exit':
-		exit(0)
-	else:
-		check_weather(query)
+    if query == 'help' or query == 'h':
+        program_help()
+    elif query == 'history':
+        get_history()
+    elif query == 'exit':
+        exit(0)
+    else:
+        check_weather(query)
```

</details>

#### 这个文件 WikiepediaModule.py:

<details>
<summary>More details</summary>

```diff
--- 
+++ 
@@ -1,5 +1,6 @@
 import wikipedia as wk
 from bs4 import BeautifulSoup
+
 
 def wiki():
     '''
@@ -33,83 +34,84 @@
 
     pass
 
+
 def fullPage(page):
     soup = BeautifulSoup(page.content, 'lxml')
     return soup
 
+
 def randomWiki():
-
     '''
     This function gives you a list of n number of
     random articles
     choose any articles
     '''
-    number=input("No: of Random Pages : ")
-    lst=wk.random(number)
+    number = input("No: of Random Pages : ")
+    lst = wk.random(number)
     for i in enumerate(lst):
         print(i)
     try:
-        key=input("Enter the number : ")
-        assert key>=0 and key<number
+        key = input("Enter the number : ")
+        assert key >= 0 and key < number
     except AssertionError:
-        key=input("Please enter corresponding article number : ")
+        key = input("Please enter corresponding article number : ")
 
-    page=wk.page(lst[key])
-    url=page.url
+    page = wk.page(lst[key])
+    url = page.url
     #originalTitle=page.original_title
-    pageId=page.pageid
+    pageId = page.pageid
     #references=page.references
-    title=page.title
+    title = page.title
     #soup=BeautifulSoup(page.content,'lxml')
-    pageLength=input('''Wiki Page Type : 1.Full 2.Summary : ''')
-    if pageLength==1:
-        soup=fullPage(page)
+    pageLength = input('''Wiki Page Type : 1.Full 2.Summary : ''')
+    if pageLength == 1:
+        soup = fullPage(page)
         print(soup)
     else:
         print(title)
-        print("Page Id = ",pageId)
+        print("Page Id = ", pageId)
         print(page.summary)
-        print("Page Link = ",url)
+        print("Page Link = ", url)
     #print "References : ",references
 
     pass
 
 
 def randomWiki():
-
     '''
     This function gives you a list of n number of
     random articles
     choose any articles
     '''
-    number=input("No: of Random Pages : ")
-    lst=wk.random(number)
+    number = input("No: of Random Pages : ")
+    lst = wk.random(number)
     for i in enumerate(lst):
         print(i)
     try:
-        key=input("Enter the number : ")
-        assert key>=0 and key<number
+        key = input("Enter the number : ")
+        assert key >= 0 and key < number
     except AssertionError:
-        key=input("Please enter corresponding article number : ")
+        key = input("Please enter corresponding article number : ")
 
-    page=wk.page(lst[key])
-    url=page.url
+    page = wk.page(lst[key])
+    url = page.url
     #originalTitle=page.original_title
-    pageId=page.pageid
+    pageId = page.pageid
     #references=page.references
-    title=page.title
+    title = page.title
     #soup=BeautifulSoup(page.content,'lxml')
-    pageLength=input('''Wiki Page Type : 1.Full 2.Summary : ''')
-    if pageLength==1:
-        soup=fullPage(page)
+    pageLength = input('''Wiki Page Type : 1.Full 2.Summary : ''')
+    if pageLength == 1:
+        soup = fullPage(page)
         print(soup)
     else:
         print(title)
-        print("Page Id = ",pageId)
+        print("Page Id = ", pageId)
         print(page.summary)
-        print("Page Link = ",url)
+        print("Page Link = ", url)
     #print "References : ",references
 
+    #randomWiki()
 
-#randomWiki()
+
 wiki()
```

</details>


## 2. 代码相似问题：
### 这些代码完全一样，建议抽象：

#### WikiepediaModule.py 文件中的 51 至 55 行：
```python
    try:
        key=input("Enter the number : ")
        assert key>=0 and key<number
    except AssertionError:
        key=input("Please enter corresponding article number : ")
```

#### WikiepediaModule.py 文件中的 89 至 93 行：
```python
    try:
        key=input("Enter the number : ")
        assert key>=0 and key<number
    except AssertionError:
        key=input("Please enter corresponding article number : ")
```

### 这些代码非常相似，建议抽象：

#### WikiepediaModule.py 文件中的 24 至 32 行：
```python
    if pageLength == 1:
        soup = fullPage(page)
        print(soup)

    else:
        print(title)
        print("Page ID= ", pageId)
        print(page.Summary)
        print("Page link =", url)
```

#### WikiepediaModule.py 文件中的 65 至 72 行：
```python
    if pageLength==1:
        soup=fullPage(page)
        print(soup)
    else:
        print(title)
        print("Page Id = ",pageId)
        print(page.summary)
        print("Page Link = ",url)
```

#### WikiepediaModule.py 文件中的 103 至 110 行：
```python
    if pageLength==1:
        soup=fullPage(page)
        print(soup)
    else:
        print(title)
        print("Page Id = ",pageId)
        print(page.summary)
        print("Page Link = ",url)
```

## 3. 复杂度及其他问题：
#### 文件 ex43.py 的 91-91 行
Error: invalid character in identifier (<unknown>, line 91)
