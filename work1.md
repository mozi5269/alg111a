本作業複製蔡宗霖同學並且理解後撰寫一次執行
```py

from asyncio.windows_events import NULL
from operator import le
# from ipData import *
# 這是習題，請完成以下程式碼！

# 5a+7b+9c+2d+1e≤250
# 18a+4b-9c+10d+12e≤285
# 4a+7b+3c+8d+5e≤211
# 5a+13b+16c+3d-7e≤315

coea=[5,7,9,2,1]
coeb=[18,4,-9,10,12]
coec=[4,7,3,8,5]
coed=[5,13,16,3,-7]

lessequala=250
lessequalb=285
lessequalc=211
lessequald=315

mina=lessequala//min(coea)
minb=lessequalb//min(coeb)
minc=lessequalc//min(coec)
mind=lessequald//min(coed)
minall=min(mina,minb,minc,mind)
maxall=max(mina,minb,minc,mind)


print(mina,minb,minc,mind)
print(minall,maxall)

savea=NULL
saveb=NULL
savec=NULL
saved=NULL
savee=NULL
saveall=NULL

#暴力
for a in range(minall,maxall+1):
    for b in range(minall,maxall+1):
        for c in range(minall,maxall+1):
            for d in range(minall,maxall+1):
                for e in range(minall,maxall+1):
                    if(5*a+7*b+9*c+2*d+1*e<=250&18*a+4*b-9*c+10*d+12*e<=285&4*a+7*b+3*c+8*d+5*e<=211&5*a+13*b+16*c+3*d-7*e<=315):
                        ans=7*a+8*b+2*c+9*d+6*e
                        if(ans>saveall):
                            saveall=ans
                            savea=a
                            saveb=b
                            savec=c
                            saved=d
                            savee=e
                            print(a,b,c,d,e,saveall)

print(a,b,c,d,e,saveall)
```
