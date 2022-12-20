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
