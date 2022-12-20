> 幾乎都是複製老師的Code，但因為程式碼並不複雜因此稍花一點時間就能理解。除了做了些許修改將呼喚的函式名字減短以外邏輯都沒有改變。
# 隨機式列舉

```py
import random as rd

def rdCombined(pA, k):
    A = pA.copy()
    chooses = []
    for _ in range(k):
        i = rd.randrange(0, len(A))
        chooses.append(A[i])
        del A[i] #選到哪個就刪除哪個，防止隨機選擇到同樣的
    chooses.sort() #由大排到小
    return chooses # 將函式結果傳出去

A = [1,2,3,4,5]
for _ in range(10):
    print(rdCombined(A, 3)) #呼喚函式
```

## 運算結果
[2,3,4]<br />
[1,4,5]<br />
[2,4,5]<br />
[2,3,5]<br />
[2,4,5]<br />
[1,3,4]<br />
[1,4,5]<br />
[2,4,5]<br />
[1,4,5]<br />
[2,4,5]<br />

# 系統式列舉

```py
def combination(A, m): # 從 A 陣列中取出 m 個的所有可能性
    chooses = []
    c(A, len(A), m, chooses, m)

def c(A, n, k, chooses, m): # 從 A[0..n] 中選取 k 個補進 chooses，如果滿 m 個就印出
    if len(chooses)==m:
        print(chooses)
        return
    if n <= 0: return
    c(A,n-1,k,chooses,m) # C(n-1,k) // A[n-1] 沒取到

    chooses.append(A[n-1])
    c(A,n-1,k-1,chooses,m) # C(n-1,k-1) // A[n-1] 有取到
    del chooses[-1]

combination([1,2,3,4,5], 3)
```
## 運算結果
[3,2,1]<br />
[4,2,1]<br />
[4,3,1]<br />
[4,3,2]<br />
[5,2,1]<br />
[5,3,1]<br />
[5,3,2]<br />
[5,4,1]<br />
[5,4,2]<br />
[5,4,3]<br />
