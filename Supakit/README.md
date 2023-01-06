# ไม่รู้จะพิมพ์อะไรดีเอาสูตรผัดกระเพราไปละกัน 
<img src="https://avatars.githubusercontent.com/u/49468390?v=4"  width="100" height="100" >

## ส่วนผสม ผัดกะเพราหมูสับ
* เนื้อหมู 400 กรัม
* ใบกะเพรา 50 กรัม
* กระเทียม 2 หัว
* พริกแดงจินดา 12 เม็ด
* พริกแห้งแดงจินดา 6 เม็ด
* น้ำปลา 1 ช้อนโต๊ะ
* ซอสปรุงรสฝาเขียว 1 1/2 ช้อนโต๊ะ
* ซอสหอย 3 ช้อนโต๊ะ
* ซีอิ้วดำหวาน 1/2 ช้อนโต๊ะ (ไม่ชอบกลิ่นตัดออกได้)
* น้ำตาลทราย 1/2 ช้อนโต๊ะ
 

## วิธีทำ ผัดกะเพราหมูสับ
1. หั่นหมูสันคอออกเป็นชิ้นๆ แล้วสับหมูออกให้ละเอียดตามความต้องการ แล้วพักไว้
2. โขลกพริกแห้งให้ละเอียด แล้วใส่พริกแดงจินดา และกระเทียมโขลกตามลงไปให้ละเอียด (สามารถปั่นแทนได้ ตามความชอบ)
3. ตั้งกระทะให้ร้อน ใส่น้ำมันพืชลงไปพอประมาณ ผัดพริกและกระเทียมให้มีกลิ่นหอม
4. เมื่อพริกกระเทียมหอมได้ที่แล้ว ใส่หมูสับลงไปผัดให้กระจาย ไม่เกาะกันเป็นก้อน ผัดให้เข้ากับพริกกระเทียม ให้หมูสุกในระดับนึง แล้วปรุงรสด้วย น้ำมันหอย น้ำปลา ซอสปรุงรส และซีอิ๊วดำหวาน น้ำตาล เล็กน้อย เร่งไฟผัดให้เข้ากัน ชิมรสชาติ แล้วใส่ใบกะเพราลงไปผัดให้เข้ากัน ปิดเตา ตักเสิร์ฟ

[ต้นฉบับ](https://food.trueid.net/detail/k7DvOYgLXXeP)

``` 
#โปรแกรมคำนวณหาราศีและจำนวนวันที่ต่างกัน ระหว่าง 2 date
def read_date(n):
    mname=["Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"]
    print("Insert date ",n,"(Ex 10 Oct 2001)")
    date = input(" : ").split()
    d = int(date[0])
    m = mname.index(date[1][:3])+1
    y = int(date[2])
    return [d,m,y]
def zodiac(d,m):
    if   d >=22 and m ==3 or d<=21 and m==4 : z="Arise"
    elif d >=22 and m ==4 or d<=21 and m==5 : z="Taurus"
    elif d >=22 and m ==5 or d<=21 and m==6 : z="Gemini"
    elif d >=22 and m ==6 or d<=21 and m==7 : z="Cancer"
    elif d >=22 and m ==7 or d<=21 and m==8 : z="Leo"
    elif d >=22 and m ==8 or d<=21 and m==9 : z="Virgo"
    elif d >=22 and m ==9 or d<=21 and m==10 : z="Libra"
    elif d >=22 and m ==10 or d<=21 and m==11 : z="Scorpio"
    elif d >=22 and m ==11 or d<=21 and m==12 : z="Sagittarius"
    elif d >=22 and m ==12 or d<=21 and m==1 : z="Capricorn"
    elif d >=22 and m ==1 or d<=21 and m==2 : z="Aquarius"
    elif d >=22 and m ==2 or d<=21 and m==3 : z="Pisces"
    return z
def days_in_feb(y):
    nd = 28
    if y%400==0 or y%100 !=0 and y&4 ==0 :
        nd = 29
    return nd
def days_in_month(m,y):
    nd = 31
    if m ==4 or m==6 or m==9 or m==11:
        nd = days_in_feb(y)
    return nd
def days_in_year(y):
    return 365-28+days_in_feb(y)
def nth_day(d,m,y):
    ndays = [0,31,28,31,30,31,30,31,31,30,31,30,31]
    ndays[2]= days_in_feb(y)
    nd = d
    for k in range(1,12):
        if m <= k:
            break
        nd +=ndays[k]
        return nd
def days_in_between(d1,m1,y1,d2,m2,y2):
    d = days_in_year(y1)-nth_day(d1,m1,y1)
    d +=int((y2-y1-1)*365.25)
    d +=nth_day(d2,m2,y2)
    return d
def main():
    d1,m1,y1 = read_date(1)
    d2,m2,y2 = read_date(2)
    print("ราศีปีที่ 1 : ",zodiac(d1,m1),"ราศีปีที่ 2 : ",zodiac(d2,m2))
    print("จำนวนที่ต่างกัน",days_in_between(d1,m1,y1,d2,m2,y2))
main()
``` 


