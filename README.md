# Project
from tkinter import *

    
w=Tk()
w.title("project")
w.minsize(height=512,width=384)
w.configure(background="black")


#MORSE

def l():
               
    l=Tk()
    my=StringVar(l)
    
    def k():
        
        a=(my.get()).upper()
        t=[]
        for i in range(65,91):
            t.append(chr(i))
        for i in range(0,10):
            t.append(str(i))
        l2=['._','_...','_._.','_..','.','.._.','__.','....','..','.___','_._','._..','__','_.','___','.__.','__._','._.','...','_','.._','..._','.__','_.._','_.__','__..','_____','.____','..___','...__','...._','.....','_....','__...','___..','____.']
        key=dict(zip(t,l2))
        d=''
        for i in a:
            if i in t:
                d+=key[i]+' '
            elif i==' ' :
                d+='\t'
            else:
                d+=i
        print(d)
        
        
    l.title("project")
    l.minsize(height=512,width=500)
    l.configure(background="black")
    lb=Label(l,text="MORSE CODE",fg="green",font=("terminal",45),bg="black").place(x=0,y=0)
    lb5=Label(l,text="ENTER MESSAGE:",fg="green",font=("terminal"),bg="black").place(x=0,y=100)
    txt1=Entry(l,textvariable=my).place(x=200,y=100)
    
    
    bt1=Button(l,text="SUBMIT",fg="green",bg="black",font=("terminal"),command=k).place(x=350,y=100)
    BT2=Button(l,text="QUIT",fg="green",bg="black",command=l.destroy).place(x=1,y=125)
    
#KNOCK
def knock():
    win=Tk()
    my=StringVar(win)
    def k():
            o=(my.get()).upper()
            a=['A','B',['C','K'],'D','E']
            a1=['F','G','H','I','J']
            a2=['L','M','N','O','P']
            a3=['Q','R','S','T','U']
            a4=['V','W','X','Y','Z']
            b=[a,a1,a2,a3,a4]
            pos=[]
            for i in o:
               if i=='C' or i=='K' :
                    pos.append([1,3])
               else:
                   for j in b:
                       if i in j:
                           t=[b.index(j)+1,j.index(i)+1]
                           pos.append(t)
            for i in pos:
                for j in i:
                    for t in range(j):
                        playsound.playsound('KNOCK KNOCK.wav')
                    playsound.playsound('silence.mp3')
         
    win.title("project")
    win.minsize(height=512,width=500)
    win.configure(background="black")
    lb=Label(win,text="KNOCK CODE",fg="green",font=("terminal",45),bg="black").place(x=0,y=0)
    lb5=Label(win,text="ENTER MESSAGE:",fg="green",font=("terminal"),bg="black").place(x=0,y=100)
    txt1=Entry(win,textvariable=my).place(x=200,y=100)
    
    
    bt1=Button(win,text="SUBMIT",fg="green",bg="black",font=("terminal"),command=k).place(x=350,y=100)
    BT2=Button(win,text="QUIT",fg="green",bg="black",command=win.destroy).place(x=1,y=125)
    
    
    
lb1=Label(text="PROJECT",font=("terminal",45),fg="green",bg="black").place(x=0,y=0)
bt1=Button(w,text="MORSE CODE",fg="light green",bg="black",command=l).place(x=0,y=100)
bt2=Button(w,text="KNOCK CODE",fg="light green",bg="black",command=knock).place(x=0,y=150)
bt3=Button(w,text="ADVANCE CAESER SHIFT",fg="light green",bg="black").place(x=0,y=200)
BT2=Button(w,text="QUIT",fg="green",bg="black",command=w.destroy).place(x=1,y=300)


w.mainloop()
