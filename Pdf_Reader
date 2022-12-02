from tkinter import *
from tkinter import filedialog

import pyttsx3
import PyPDF2

Window = Tk()
Window.geometry('500x350')
Window.config(bg="white")
Window.title("Convert PDF File Text to Audio Speech")

page1= Label(Window, text=" Enter starting page number")
startingpagenumber = Entry(Window)
page1.place(relx=0.02,rely=0.1)
startingpagenumber.place(relx=0.6,rely=0.1)

label = Label(Window, text="Select the PDF you want to read.")
label.place(relx=0.3,rely=0.2)
def file():
    path = filedialog.askopenfilename()
    book = open(path, 'rb')
    pdfreader = PyPDF2.PdfFileReader(book)
    pages = pdfreader.numPages
    speak = pyttsx3.init()
    
    for i in range(int(startingpagenumber.get()), pages):
        page = pdfreader.getPage(i) 
        txt = page.extractText()
        speak.say(txt)
        speak.runAndWait()

B=Button(Window, text="Choose  the PDF", command=file)
B.place(relx=0.4,rely=0.3)

mainloop()
