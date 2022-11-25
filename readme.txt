10장연습문제
1번
from tkinter import *

window = Tk()

program = Label(window, text="간단한 GUI 프로그램!")
program.pack()

firstBtn = Button(window, text="환영합니다.")
lastBtn  = Button(window, text="종료")

firstBtn.pack()
lastBtn.pack()

window.mainloop()
2번
def plus():
    global total
    total += int(e.get())
    display()

def minus():
    global total
    total -= int(e.get())
    display()

def reset():
    global total
    total = 100
    display()

def display():
    global secondLabel
    secondLabel.destroy() 
    secondLabel = Label(window,text=total)
    secondLabel.grid(row=0,column=1) 


from tkinter import *

total = 100

window = Tk()

firstLabel  = Label(window, text="현재 합계: ")
secondLabel = Label(window, text=total)

firstLabel.grid(row=0,column=0) 
secondLabel.grid(row=0, column=1)

e = Entry(window) 
e.grid(row=1,column=0, columnspan=3) 

plusBtn  = Button(window, text="더하기(+)", command=plus) 
minusBtn = Button(window, text="빼기(-)", command=minus) 
resetBtn = Button(window, text="초기화", command=reset)

plusBtn.grid(row=2, column=0)
minusBtn.grid(row=2, column=1)
resetBtn.grid(row=2, column=2)

window.mainloop()
3번
from tkinter import *
import random

window = Tk()
num = 0
betNum = random.randint(1,100)

def run():
    global num
    global betNum

    num = int(e.get())
    if num < betNum:
        firstLabel['text'] = "너무 낮아요!!"
    elif num > betNum:
        firstLabel['text'] = "너무 높아요!!"
    else:
        firstLabel['text'] = "정답입니다!"

def reset():
    global num
    global betNum

    e.delete(0,END)
    secondLabel.config(text="")
    betNum = random.randint(1,100)
    num = 0

firstLabel = Label(window, text="1에서 100사이의 수를 입력하세요.")
secondLabel = Label(window,)
thridLabel = Label(window, )

firstLabel.grid(row=1, column=0, columnspan=2)
secondLabel.grid(row=2, column=0, columnspan=2)
thridLabel.grid(row=4, column=0, columnspan=2)

e = Entry(window)
e.grid(row=3, column=0, columnspan=2)

firstBtn = Button(window, text="숫자를 입력", command = run)
secondBtn= Button(window, text="게임을 다시 실행", command = reset)

firstBtn.grid(row=5, column=0)
secondBtn.grid(row=5, column=1)

window.mainloop()
4번
def changedInch():
    inch  = int(e.get())  
    centi = inch * 2.54 # 인치 -> 센티미터
    forthLabel.configure(text = str(centi)+" 센티미터") 
    

from tkinter import *

window = Tk()

firstLabel = Label(window, text = "인치를 센티미터로 변환하는 프로그램: ")
firstLabel.grid(row=0, column=0,columnspan=2) 

secondLabel = Label(window, text = "인치를 입력하시오:")
secondLabel.grid(row=1, column=0)

e = Entry()
e.grid(row=1, column=1)

thirdLabel = Label(window, text = "변환결과:")
thirdLabel.grid(row=2, column=0)

forthLabel = Label(window, text = "0 센티미터")

forthLabel.grid(row=2, column=1)

changeBtn = Button(window, text="변환!", command=changedInch)
changeBtn.grid(row=3, column=1)

window.mainloop()
5번
from tkinter import*


window=Tk()
#-------상단 라벨 생성--------------
l1= Label(window,text="이름")
l2= Label(window,text="직업")
l3= Label(window,text="국적")


# 격자배열을 통해 1행에 배치
l1.grid(row=0,column=0)
l2.grid(row=1,column=0)
l3.grid(row=2,column=0)


#------입력부분 생성------------
e1=Entry(window)
e2=Entry(window)
e3=Entry(window)


# 격자배열을 통해 2행에 배치
e1.grid(row=0,column=1)
e2.grid(row=1,column=1)
e3.grid(row=2,column=1)


#-------하단 버튼 생성------------
b1=Button(window,text="Show")
b2=Button(window,text="Quit")


# 격자배열을 통해 3열에 배치
b1.grid(row=3,column=0)
b2.grid(row=3,column=1)


window.mainloop()
