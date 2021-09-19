# Text to speech
##### Learn how to convert your Text into Voice with Python and Google APIs  
Text to speech is a process to convert any text into voice. Text to speech project takes words on digital devices and convert them into audio with a button click or finger touch. Text to speech python project is very helpful for people who are struggling with reading.
## Project Prerequisites
To implement this project, we will use the basic concepts of Python, ***Tkinter***, ***gTTS***, and ***playsound*** libraries.
+ Tkinter is a standard GUI Python library that is one of the fastest and easiest ways to build GUI applications using Tkinter.
+ gTTS (Google Text-to-Speech) is a Python library, which is a very easy library that converts the text into audio.
+ The playsound module is used to play audio files. With this module, we can play a sound file with a single line of code.
##### To install the required libraries, you can use pip install command:
     pip install tkinter
     pip install gTTS
     pip install playsound   # pip install pygobject
## Text to Speech Python Project
The objective of this project is to convert the text into voice with the click of a button. This project will be developed using ***Tkinter, gTTs,*** and ***playsound*** library.

In this project, we add a message which we want to convert into voice and click on play button to play the voice of that text message.
+ Importing the modules
+ Create the display window
+ Define functions
So these are the basic steps that we will do in this Python project. Let’s start.
## 1. Import Libraries
    from tkinter import *
    from gtts import gTTS
    from playsound import playsound
   
### 2. Initializing window
    root = Tk()
    root.geometry("500x400")
    root.configure(bg='ghost white')
    root.title("SON BK - TEXT TO SPEECH")
    
+ ***Tk()*** to initialized tkinter which will be used for GUI
+ ***geometry()*** used to set the width and height of the window
+ ***configure()*** used to access window attributes
+ ***bg*** will used to set the color of the background
+ ***title()*** set the title of the window
    
Label() widget is used to display one or more than one line of text that users can’t able to modify.

    Label(root, text="TEXT_TO_SPEECH", font="arial 20 bold", bg='white smoke').pack()
    Label(text="SON BK", font='arial 15 bold', bg='white smoke', width='20').pack(side='bottom')

    Msg = StringVar()
    Label(root, text="Enter Text", font='arial 15 bold', bg='white smoke').place(x=20, y=60)

    entry_field = Entry(root, textvariable=Msg, width='55')
    entry_field.place(x=20, y=100)
+ ***root*** is the name which we refer to our window
+ ***text*** which we display on the label
+ ***font*** in which the text is written
+ ***pack*** organized widget in block
+ ***Msg*** is a string type variable
+ ***Entry()*** used to create an input text field
+ ***textvariable*** used to retrieve the current text to entry widget
+ ***place()*** organizes widgets by placing them in a specific position in the parent widget

## 3. Function to Convert Text to Speech
    def Text_to_speech():
       Message = entry_field.get()
       speech = gTTS(text=Message)
       speech.save('Speech.mp3')
       playsound('Speech.mp3')
+ ***Message*** variable will stores the value of entry_field
+ ***text*** is the sentences or text to be read.

As we want the default value of lang, so no need to give that to gTTS.
+ ***speech*** stores the converted voice from the text
+ ***speech.save(‘Speech.mp3’)*** will saves the converted file as Speech as mp3 file
+ ***playsound()*** used to play the sound

## 4. Function Exit()
    def Exit():
        root.destroy()
        
## 5. Function Reset()
    def Reset():
        Msg.set("")![Screenshot from 2021-09-19 09-57-20](https://user-images.githubusercontent.com/87347502/133913940-e1c0018c-ca19-4903-a9aa-c218c4597954.png)

        
## 6. Button
    Button(root, font='arial 15 bold', text="PLAY", width='4',  command=Text_to_speech).place(x=100, y=140)
    Button(root, font='arial 15 bold', text='EXIT', width='4', command=Exit, bg='OrangeRed1').place(x=175, y=140)
    Button(root, font='arial 15 bold', text='RESET', width='6', command=Reset).place(x=250, y=140)
