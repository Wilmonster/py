# py
## GAME UnboundSnake_v0.2


import re
import random
def main():
    pass
##    i = 0
##    #f = open('words.txt', 'r')


##    with open("ReporteTarjetaCredito_CIFIN_2015131.txt") as f:
##        print(f.name)
##        str = f.read(20);
##        print ("Read String is : ", str)
##        print(f.tell())
##        position = f.seek(0,2)
##        str = f.read(500);
##        print ("Read String is : ", str)
##        print(f.tell())
##    if '5564793654654' in open('ReporteTarjetaCredito_CIFIN_2015131.txt').read():
##        print ("true")
##    str= "holaMundo"
##    print(str.find("o"))

##working find
##with open('ReporteTarjetaCredito_CIFIN_2015131.txt', 'r') as inF:
##    i = 0
##    for line in inF:
##        if 'CAFERINO' in line:
##            # do_something
##            i = i + 1
##        #for line_no, line in enumerate(f):
##        # Remember not to count the newline character
##            #if len(line.strip()) != 32:
##            #print (line_no, len(line.strip()),len(line))
##        #    i = i+1
##    print(i)
    i = 0
    maxValue = 0
    fo = open("foo.txt", "w")
    with open('PTAHO66785920150228.txt', 'r') as inF:
        for line in inF:
            i = i + 1
            if i % 10000 == 0:
                text = line[99:110]
                try:
                    p = int(text)
                    if p > maxValue :
                        maxValue = p
                except:
                    print("line number:",i,"error value:",text)
                else:
                    if p > 0 :
                        #line[start-1 : end]
                        x = 5
                        y = 'lemon'
                        z = "The items in the basket are %s and %s" % (x,y)
##                        print("line number:\t",i," value:\t",p,"\t",text,line[1:12],"Num Cuenta:\t",line[12:30])
##                        fo.write("line number:\t %s value:\t %s \t %s %s Num Cuenta:\t %s \n" % (i,p,text,line[1:12],line[12:30]))
                        music = ["Abba","Rolling Stones","Black Sabbath","Metallica"]
                        #Join a list with an empty space
                        print ('\n'.join(music))
                        fo.write("line number:\t {} value:\t {} \t {} {} Num Cuenta:\t {}\n".format(i,p,text,line[1:12],line[12:30]))
    print(maxValue)
    fo.close()


##NOw using regular expressions
##    text = "He was carefully disguised but captured quickly by police."
##    print(re.findall(r"\w+ly", text))
##    print(re.match("c", "abcdef"))  # No match
##    print(re.search("c", "abcdef")) # Match
##
##    def repl(m):
##       inner_word = list(m.group(2))
##       random.shuffle(inner_word)
##       return m.group(1) + "".join(inner_word) + m.group(3)

##    text = "Professor Abdolmalek, please report your absences promptly."
##    print(re.sub(r"(\w)(\w+)(\w)", repl, text))
##    print(re.sub(r"(\w)(\w+)(\w)", repl, text))

##07-16: carefully
##40-47: quickly
##text = "He was carefully disguised but captured quickly by police."
##for m in re.finditer(r"\w+ly", text):
##    print ("%02d-%02d: %s" % (m.start(), m.end(), m.group(0)))

##    x = "Hello World!"
##    print(x[6:12])


##    #for line in f:
##    #    print (len(line))

import glob
import os

def main():
    pass

##filenames = ['No reportar Datacredito Enero 2015.txt', 'Eliminar Datacredito Enero 2015.txt'
##            , 'Fallecidos Datacredito Enero 2015.txt', 'Incapacidad Total Datacredito Enero 2015.txt']
##with open('output.txt', 'w') as outfile:
##    for fname in filenames:
##        with open(fname) as infile:
##            for line in infile:
##                outfile.write(line)
outputfilename = 'output.txt'
filesDir = "./No Reportar/"
extensionFile = ".txt"

with open(outputfilename, 'w') as outfile:
    for file in os.listdir(filesDir):
        if file.endswith(extensionFile):
            with open(filesDir+file) as infile:
                for line in infile:
                    if len(line.strip()) > 0 :
                        outfile.write(line)

##os.chdir("./No Reportar")
##for file in glob.glob("*.txt"):
##    print(file)

##from tkinter import *           # Importing the Tkinter (tool box) library
##root = Tk()                     # Create a background window
##                                # Create a list
##li = 'Carl Patrick Lindsay Helmut Chris Gwen'.split()
##listb = Listbox(root)           # Create a listbox widget
##for item in li:                 # Insert each item within li into the listbox
##    listb.insert(0,item)
##
##listb.pack()                    # Pack listbox widget
##root.mainloop()                 # Execute the main event handler

##from tkinter import *
##
##def Pressed():                          #function
##        print ('buttons are cool')
##
##root = Tk()                             #main window
##button = Button(root, text = 'Press', command = Pressed)
##button.pack(pady=20, padx = 20)
##
##root.mainloop()

#     t k P h o n e . p y
#
from tkinter import *
from phones  import *

def whichSelected () :
    print ("At %s of %d" % (select.curselection(), len(phonelist)))
    return int(select.curselection()[0])

def addEntry () :
    phonelist.append ([nameVar.get(), phoneVar.get()])
    setSelect ()

def updateEntry() :
    phonelist[whichSelected()] = [nameVar.get(), phoneVar.get()]
    setSelect ()

def deleteEntry() :
    del phonelist[whichSelected()]
    setSelect ()

def loadEntry  () :
    name, phone = phonelist[whichSelected()]
    nameVar.set(name)
    phoneVar.set(phone)

def makeWindow () :
    global nameVar, phoneVar, select
    win = Tk()

    frame1 = Frame(win)
    frame1.pack()

    Label(frame1, text="Name").grid(row=0, column=0, sticky=W)
    nameVar = StringVar()
    name = Entry(frame1, textvariable=nameVar)
    name.grid(row=0, column=1, sticky=W)

    Label(frame1, text="Phone").grid(row=1, column=0, sticky=W)
    phoneVar= StringVar()
    phone= Entry(frame1, textvariable=phoneVar)
    phone.grid(row=1, column=1, sticky=W)

    frame2 = Frame(win)       # Row of buttons
    frame2.pack()
    b1 = Button(frame2,text=" Add  ",command=addEntry)
    b2 = Button(frame2,text="Update",command=updateEntry)
    b3 = Button(frame2,text="Delete",command=deleteEntry)
    b4 = Button(frame2,text=" Load ",command=loadEntry)
    b1.pack(side=LEFT); b2.pack(side=LEFT)
    b3.pack(side=LEFT); b4.pack(side=LEFT)

    frame3 = Frame(win)       # select of names
    frame3.pack()
    scroll = Scrollbar(frame3, orient=VERTICAL)
    select = Listbox(frame3, yscrollcommand=scroll.set, height=6)
    scroll.config (command=select.yview)
    scroll.pack(side=RIGHT, fill=Y)
    select.pack(side=LEFT,  fill=BOTH, expand=1)
    return win

def setSelect () :
    phonelist.sort()
    select.delete(0,END)
    for name,phone in phonelist :
        select.insert (END, name)

win = makeWindow()
setSelect ()
win.mainloop()


phonelist = [
  ['Meyers, Chris',  '343-4349'],
  ['Smith, Robert',  '689-1234'],
  ['Jones, Janet',   '483-5432'],
  ['Barnhart, Ralph','683-2341'],
  ['Nelson, Eric',   '485-2689'],
  ['Prefect, Ford',  '987-6543'],
  ['Zigler, Mary',   '567-8901'],
  ['Smith, Bob',     '689-1234']
]
