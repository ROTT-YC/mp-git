# 那些python練習過的小東西

## 邏輯判斷
###  九九乘法表-雙重迴圈

```gherkin=
for i in range(1,10):
  for j in range(1,10):
    print(i*j,end=" ")
    print("%d*%d=%2d" % (i,j,i*j),end=" ")  #顯示幾乘幾
  print("")  #換行
```
> 升級版 - 神秘數字版
```gherkin=
_r = input('請輸入0~9:')  #把誰變不見
for i in range(1,19):
  for j in range(1,19):
    print(str(i*j).replace(_r,'*'), end='\t')
  print()
```
![](https://i.imgur.com/RTVf5uY.png)



###  陣列排序
使用numpy產生隨機數值陣列
```gherkin=
# 使用sort排序 - 由大到小
import numpy as np
x = np.random.randint(0,101,size=10)
print("初始陣列:",(x))
y = sorted(x,reverse = True)
print("排序後陣列:",(y))
```
```gherkin=
# 雙層for迴圈 - 由小到大
import numpy as np
z = np.random.randint(1,100,size=10)
print("初始陣列:  ",(z))

for j in range(len(z)):
  for i in range(len(z)-1):
    if z[i] > z[i+1]:
      _change = z[i]
      z[i] = z[i+1]
      z[i+1] = _change
print('排列後陣列:',z)

```
```gherkin=
# 倒轉
a = input('input:')
print(a[::-1])
```

### 找出質數
> 預設情境:
> 輸入兩個數字，顯示出兩數值之間的質數

```gherkin=
_min = int(input('input1:'))
_max = int(input('input2:'))
ans = []
for i in range(_min,_max+1):
  _num = 0
  for j in range(2,i):
    if i%j ==0:
      _num +=1
  if _num == 0:
      ans.append(i)

print(ans)
```
### 註冊小遊戲
> 預設情境:
> 註冊開始
> 請輸入學生姓名:
> Q:是否結束(y/n)
>  要能判斷除y與n之外字母並回覆輸入錯誤
> 註冊結束
> output:班級共?人，名稱為??
```gherkin=
student_list = []
print('註冊開始')

_outof = False
while _outof == False:
  _theend = input('是否結束(y/n) ')
  if _theend == 'n':
    # name_add = input('請輸入學生姓名: ')
    # student_list.append(name_add)
    student_list.append(input('請輸入學生姓名: '))
    _outof = False
  elif _theend == 'y':
    _outof = True
    print('註冊結束','\n班級共',len(student_list),'人,名稱為',student_list)
  else:
    print('輸入錯誤')
```
![](https://i.imgur.com/Y2dRTKb.png)

### 不重複幾A幾B小遊戲
```gherkin=
count =0
_outof = False
while _outof == False:
  ans =[2,3,4,8]
  A = 0
  B = 0
  
  test = input('請輸入4個不重複的數字:')


  if len(test) != 4:
    print('輸入錯誤!!!')
  elif len(set(test)) != len(test):
    print('有重複數值!!!')
  else:
    count+=1
    for i in range(4):
      if str(test[i]) == str(ans[i]):
        A += 1
      elif str(test[i]) != str(ans[i]):
        if str(test[i]) in str(ans):
          B += 1 #是否有出現在其他位置(出現在ans的list裡)
      
    print('第',count,'次猜測，目前結果為',A,'A',B,'B')
  if A == 4:
    print('恭喜答對,答案為',test)
    _thend = input('是否再玩一輪?(Y/N) ')
    if _thend == 'N':
      _outof = True
```
## 套件
### Datetime
```gherkin=
#使用 datetime 套件顯示現在時間
import datetime as dt
now = dt.datetime.now()
print(now.strftime("%Y/%m/%d %H:%M:%S"))  #此時時區未調整

from datetime import datetime,timezone,timedelta
dt1 = datetime.utcnow().replace(tzinfo=timezone.utc)
dt2 = dt1.astimezone(timezone(timedelta(hours=8))) #轉換時區 -> 東八區

print(dt2.strftime("%Y/%m/%d %H:%M:%S"))
```
