import tkinter.messagebox
from tkinter import *
# importing message box from the tkinter
from tkinter import messagebox
# importing a library converting text in to audio
import pyttsx3
# parent window initialization
root = Tk()
root.geometry("350x500")
root.configure(bg="blue")
def login():
    username=user_entry.get()
    password=password_entry.get()
    if(username==" " and password==" "):
        messagebox.showerror("","Enter username and password for authentication")
    elif(username == "Reema" and password == "Y@#$%()"):
        messagebox.showinfo("", "Successfully Login")
        yyyy()
    else:
        messagebox.showerror("", "Enter  correct username and password for authentication")
#billing System Login
frame1=Frame(root,highlightthickness=2,highlightbackground="white")
Label(root, text='ADMIN LOGIN', font=('Bold', 25), fg='black',bg="blue",
                 bd=0,  relief=FLAT).place(x=45,y=50)
user_label = Label(root, text='username', font=('Bold', 12), fg='black',bg="blue",
                 bd=0,  relief=FLAT)
user_label.place(x=40,y=160)
user_entry = Entry(root, width=20, bd=5, fg="blue")
user_entry.place(x=140,y=160)
#password
password_label = Label(root, text='Password', font=('Bold', 12), fg='black',bg="blue",
                 bd=0,  relief=FLAT)
password_label.place(x=40,y=230)
password_entry = Entry(root, width=20, bd=5, fg="blue")
password_entry.place(x=140,y=230)
#button
button3=Button(root, text="Login", fg="white", bg="blue", width=30, height=2, bd=5,command=lambda:login())
button3.place(x=40,y=350)
def yyyy():
    frameImp = Frame(root, bg="#FDFBD4")
    frameImp.pack()
    def Bill():
        entry1 = str(name_entry.get())
        entry2 = str(name_entry2.get())
        entry3 = str(name_entry3.get())
        text = "\n" + "Bill Number:" + entry1 + "\n" + "Phone Number:" + entry2 + "\n" + "Address:" + entry3 + "\n"
        textarea.insert(END, "\nWelcome to the Mall")
        textarea.insert(END, text)
        textarea.insert(END, "\n==================================================")
        textarea.insert(END, "\nProduct\t\tQuantity\t\tpieces")
        textarea.insert(END, "\n==================================================")
        if cosmetic_label_entry1.get()!=0:
            textarea.insert(END, f"\n Hair oil\t\t\t{cosmetic_label_entry1.get()}\t\t{name6_entry.get()}")
        if grocery_label_entry1.get()!=0:
            textarea.insert(END, f"\n Imported Fruits\t\t\t{grocery_label_entry1.get()}\t\t{name_entry26.get()}")
        if clothing_label_entry1.get()!=0:
            textarea.insert(END, f"\n Men's Shirt\t\t\t{clothing_label_entry1.get()}\t\t{name_entry36.get()}")
        textarea.insert(END, "\n==================================================")
        textarea.insert(END, f"\nCosmetic Tax:\t\t{name46_entry.get()}")
        textarea.insert(END, f"\nGrocery Tax:\t\t{name_entry56.get()}")
        textarea.insert(END, f"\nGarnment Tax:\t\t{name_entry66.get()}")

    def Total():

        # for cosmetic
        entry11 = int(cosmetic_label_entry1.get()) * 10
        entry12 = int(cosmetic_label_entry2.get()) * 10
        entry13 = int(cosmetic_label_entry3.get()) * 10
        entry14 = int(cosmetic_label_entry4.get()) * 10
        entry15 = int(cosmetic_label_entry5.get()) * 10
        entry16 = int(cosmetic_label_entry6.get()) * 10
        total = entry11 + entry12 + entry13 + entry14 + entry15 + entry16
        name6_entry.insert(0, total)

        # for grocery
        entry21 = int(grocery_label_entry1.get()) * 10
        entry22 = int(grocery_label_entry2.get()) * 10
        entry23 = int(grocery_label_entry3.get()) * 10
        entry24 = int(grocery_label_entry4.get()) * 10
        entry25 = int(grocery_label_entry5.get()) * 10
        entry26 = int(grocery_label_entry6.get()) * 10
        total = entry21 + entry22 + entry23 + entry24 + entry25 + entry26
        name_entry26.insert(0, total)
        # for clothes
        entry31 = int(clothing_label_entry1.get()) * 10
        entry32 = int(clothing_label_entry2.get()) * 10
        entry33 = int(clothing_label_entry3.get()) * 10
        entry34 = int(clothing_label_entry4.get()) * 10
        entry35 = int(clothing_label_entry5.get()) * 10
        entry36 = int(clothing_label_entry6.get()) * 10
        total = entry31 + entry32 + entry33 + entry34 + entry35 + entry36
        name_entry36.insert(0, total)

    def exit():
        frameImp.destroy()

    # r.iconbitmap('icon.ico')
    # heading
    title = Label(frameImp, text='BILLING SYSTEM OF MALL', font=('Bold', 32), fg='white',
                  bd=0, bg='black', relief=FLAT)
    title.pack(fill=X)
    # creating frame 1
    frame1 = LabelFrame(frameImp, text="customer details", bg='black', fg='gold', font=('Bold', 19))
    # first label
    name = Label(frame1, text='Name', font=('Bold', 12), fg='white',
                 bd=0, bg='black', relief=FLAT)
    name.grid(row=1, column=1, padx=40, pady=50)
    name_entry = Entry(frame1, width=20, bd=5, fg="blue")
    name_entry.grid(row=1, column=2, padx=40, pady=50)
    # second label
    name2 = Label(frame1, text='Phone Number', font=('Bold', 12), fg='white',
                  bd=0, bg='black', relief=FLAT)
    name2.grid(row=1, column=3, padx=40, pady=50)
    name_entry2 = Entry(frame1, width=20, bd=5, fg="blue")
    name_entry2.grid(row=1, column=4)
    # third label
    name3 = Label(frame1, text='Address', font=('Bold', 12), fg='white',
                  bd=0, bg='black', relief=FLAT)
    name3.grid(row=1, column=5, padx=40, pady=50)
    name_entry3 = Entry(frame1, width=20, bd=5, fg="blue")
    name_entry3.grid(row=1, column=6)

    Button(frame1, text="PRINT", fg="black", bg="white", width=20, height=2, bd=5). \
        grid(row=1, column=7, padx=300, pady=10)
    frame1.pack(fill=X)
    # creating frame2
    main_frame = LabelFrame(frameImp)
    frame2 = LabelFrame(main_frame, text="Cosmetic", bg='black', fg='gold', font=('Bold', 19))
    # creating cosmetic_label1
    cosmetic_label1 = Label(frame2, text='Hair Oil', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    cosmetic_label1.grid(row=1, column=1, padx=50, pady=10)
    cosmetic_label_entry1 = Entry(frame2, width=20, bd=5, fg="blue")
    cosmetic_label_entry1.grid(row=1, column=2, padx=30, pady=10)
    cosmetic_label_entry1.insert(0, 0)
    # creating cosmetic_label2
    cosmetic_label2 = Label(frame2, text='Body Lotion', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    cosmetic_label2.grid(row=2, column=1, padx=20, pady=20)
    cosmetic_label_entry2 = Entry(frame2, width=20, bd=5, fg="blue")
    cosmetic_label_entry2.grid(row=2, column=2, padx=30, pady=20)
    cosmetic_label_entry2.insert(0, 0)
    # creating cosmetic_label3
    cosmetic_label3 = Label(frame2, text='Lipstick', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    cosmetic_label3.grid(row=3, column=1, padx=20, pady=20)
    cosmetic_label_entry3 = Entry(frame2, width=20, bd=5, fg="blue")
    cosmetic_label_entry3.grid(row=3, column=2, padx=30, pady=20)
    cosmetic_label_entry3.insert(0, 0)
    # creating cosmetic_label4
    cosmetic_label4 = Label(frame2, text='Conditioner', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    cosmetic_label4.grid(row=4, column=1, padx=20, pady=20)
    cosmetic_label_entry4 = Entry(frame2, width=20, bd=5, fg="blue")
    cosmetic_label_entry4.grid(row=4, column=2, padx=30, pady=20)
    cosmetic_label_entry4.insert(0, 0)

    # creating cosmetic_label5
    cosmetic_label5 = Label(frame2, text='Hair Serum', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    cosmetic_label5.grid(row=5, column=1, padx=20, pady=20)
    cosmetic_label_entry5 = Entry(frame2, width=20, bd=5, fg="blue")
    cosmetic_label_entry5.grid(row=5, column=2, padx=30, pady=20)
    cosmetic_label_entry5.insert(0, 0)
    # creating cosmetic_label6
    cosmetic_label6 = Label(frame2, text='Foundation', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    cosmetic_label6.grid(row=6, column=1, padx=20, pady=13)
    cosmetic_label_entry6 = Entry(frame2, width=20, bd=5, fg="blue")
    cosmetic_label_entry6.grid(row=6, column=2, padx=30, pady=13)
    cosmetic_label_entry6.insert(0, 0)
    frame2.pack(side=LEFT)
    frame2.pack_propagate(False)
    frame2.configure(width=400, height=400)

    # creating frame3
    frame3 = LabelFrame(main_frame, text="Grocery", bg='black', fg='gold', font=('Bold', 19))
    # creating grocery label1
    grocery_label1 = Label(frame3, text='Imported Fruits', font=('Bold', 12), fg='white',
                           bd=0, bg='black', relief=FLAT)
    grocery_label1.grid(row=1, column=1, padx=50, pady=17)
    grocery_label_entry1 = Entry(frame3, width=20, bd=5, fg="blue")
    grocery_label_entry1.grid(row=1, column=2, padx=30, pady=17)
    grocery_label_entry1.insert(0, 0)
    # creating grocery label2
    grocery_label2 = Label(frame3, text='Indian Vegetables', font=('Bold', 12), fg='white',
                           bd=0, bg='black', relief=FLAT)
    grocery_label2.grid(row=2, column=1, padx=20, pady=20)
    grocery_label_entry2 = Entry(frame3, width=20, bd=5, fg="blue")
    grocery_label_entry2.grid(row=2, column=2, padx=30, pady=20)
    grocery_label_entry2.insert(0, 0)
    # creating grocery label3
    grocery_label3 = Label(frame3, text='Imported Vegetables', font=('Bold', 12), fg='white',
                           bd=0, bg='black', relief=FLAT)
    grocery_label3.grid(row=3, column=1, padx=20, pady=20)
    grocery_label_entry3 = Entry(frame3, width=20, bd=5, fg="blue")
    grocery_label_entry3.grid(row=3, column=2, padx=30, pady=20)
    grocery_label_entry3.insert(0, 0)
    # creating grocery label4
    grocery_label4 = Label(frame3, text='Mushrooms', font=('Bold', 12), fg='white',
                           bd=0, bg='black', relief=FLAT)
    grocery_label4.grid(row=4, column=1, padx=20, pady=20)
    grocery_label_entry4 = Entry(frame3, width=20, bd=5, fg="blue")
    grocery_label_entry4.grid(row=4, column=2, padx=30, pady=20)
    grocery_label_entry4.insert(0, 0)
    # creating grocery label5
    grocery_label5 = Label(frame3, text='Brocolli', font=('Bold', 12), fg='white',
                           bd=0, bg='black', relief=FLAT)
    grocery_label5.grid(row=5, column=1, padx=20, pady=13)
    grocery_label_entry5 = Entry(frame3, width=20, bd=5, fg="blue")
    grocery_label_entry5.grid(row=5, column=2, padx=30, pady=13)
    grocery_label_entry5.insert(0, 0)
    # creating grocery label6
    grocery_label6 = Label(frame3, text='Vegetarian Egg', font=('Bold', 12), fg='white',
                           bd=0, bg='black', relief=FLAT)
    grocery_label6.grid(row=6, column=1, padx=20, pady=13)
    grocery_label_entry6 = Entry(frame3, width=20, bd=5, fg="blue")
    grocery_label_entry6.grid(row=6, column=2, padx=30, pady=13)
    grocery_label_entry6.insert(0, 0)
    frame3.pack(side=LEFT)
    frame3.pack_propagate(False)
    frame3.configure(width=400, height=400)
    # creating frame4
    frame4 = LabelFrame(main_frame, text="Clothes", bg='black', fg='gold', font=('Bold', 19))
    # creating cosmetic_label1
    clothing_label1 = Label(frame4, text="Men's Shirt", font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    clothing_label1.grid(row=1, column=1, padx=50, pady=10)
    clothing_label_entry1 = Entry(frame4, width=20, bd=5, fg="blue")
    clothing_label_entry1.grid(row=1, column=2, padx=30, pady=10)
    clothing_label_entry1.insert(0, 0)
    # creating cosmetic_label2
    clothing_label2 = Label(frame4, text="Men's Tousers", font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    clothing_label2.grid(row=2, column=1, padx=50, pady=17)
    clothing_label_entry2 = Entry(frame4, width=20, bd=5, fg="blue")
    clothing_label_entry2.grid(row=2, column=2, padx=50, pady=17)
    clothing_label_entry2.insert(0, 0)
    # creating cosmetic_label3
    clothing_label3 = Label(frame4, text='Lehenga', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    clothing_label3.grid(row=3, column=1, padx=50, pady=10)
    clothing_label_entry3 = Entry(frame4, width=20, bd=5, fg="blue")
    clothing_label_entry3.grid(row=3, column=2, padx=50, pady=20)
    clothing_label_entry3.insert(0, 0)
    # creating cosmetic_label1
    clothing_label4 = Label(frame4, text='Saree', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    clothing_label4.grid(row=4, column=1, padx=50, pady=10)
    clothing_label_entry4 = Entry(frame4, width=20, bd=5, fg="blue")
    clothing_label_entry4.grid(row=4, column=2, padx=50, pady=20)
    clothing_label_entry4.insert(0, 0)
    # creating cosmetic_label5
    clothing_label5 = Label(frame4, text='Gown', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    clothing_label5.grid(row=5, column=1, padx=50, pady=10)
    clothing_label_entry5 = Entry(frame4, width=20, bd=5, fg="blue")
    clothing_label_entry5.grid(row=5, column=2, padx=50, pady=20)
    clothing_label_entry5.insert(0, 0)
    # creating cosmetic_label6
    clothing_label6 = Label(frame4, text='Kids Wear', font=('Bold', 12), fg='white',
                            bd=0, bg='black', relief=FLAT)
    clothing_label6.grid(row=6, column=1, padx=50, pady=20)
    clothing_label_entry6 = Entry(frame4, width=20, bd=5, fg="blue")
    clothing_label_entry6.grid(row=6, column=2, padx=50, pady=10)
    clothing_label_entry6.insert(0, 0)
    frame4.pack(side=LEFT)
    frame4.pack_propagate(False)
    frame4.configure(width=400, height=400)
    # creating frame5
    frame5 = LabelFrame(main_frame, text="", bg='white', font=('Bold', 19))
    frame_label5 = Label(frame5, text='Bill of the shopping', font=('Bold', 15), fg='black',
                         bd=0, relief=FLAT)
    frame_label5.place(x=100, y=20)
    textarea = Text(frame5, height=20, width=80, fg="black")
    textarea.place(x=0, y=60)
    scrollbar = Scrollbar(frame5)
    scrollbar.pack(side=RIGHT, fill=Y)

    frame5.pack(side=LEFT)
    frame5.pack_propagate(False)
    frame5.configure(width=440, height=400)
    main_frame.pack(fill=X)

    # creating frame 6
    frame6 = LabelFrame(frameImp, text="Bill System", fg='gold', font=('Bold', 19), bg='black')
    # first label
    name6 = Label(frame6, text='Cosmetic cost', font=('Bold', 12), fg='white',
                  bd=0, bg='black', relief=FLAT)
    name6.grid(row=1, column=1, padx=10, pady=10)
    name6_entry = Entry(frame6, width=20, bd=5, fg="blue")
    name6_entry.grid(row=1, column=2, padx=10, pady=10)
    # second label
    name26 = Label(frame6, text='Grocery cost', font=('Bold', 12), fg='white',
                   bd=0, bg='black', relief=FLAT)
    name26.grid(row=1, column=3, padx=40, pady=10)
    name_entry26 = Entry(frame6, width=20, bd=5, fg="blue")
    name_entry26.grid(row=1, column=4, padx=10, pady=10)
    # third label
    name36 = Label(frame6, text='Clothes Cost', font=('Bold', 12), fg='white',
                   bd=0, bg='black', relief=FLAT)
    name36.grid(row=1, column=5, padx=10, pady=10)
    name_entry36 = Entry(frame6, width=20, bd=5, fg="blue")
    name_entry36.grid(row=1, column=6, padx=10, pady=10)

    # fourth label
    name46 = Label(frame6, text='Cosmetic Tax', font=('Bold', 12), fg='white',
                   bd=0, bg='black', relief=FLAT)
    name46.grid(row=2, column=1, padx=10, pady=10)
    name46_entry = Entry(frame6, width=20, bd=5, fg="blue")
    name46_entry.grid(row=2, column=2, padx=10, pady=10)
    name46_entry.insert(0, 55)
    # fivth label
    name56 = Label(frame6, text='Grocery Tax', font=('Bold', 12), fg='white',
                   bd=0, bg='black', relief=FLAT)
    name56.grid(row=2, column=3, padx=40, pady=10)
    name_entry56 = Entry(frame6, width=20, bd=5, fg="blue")
    name_entry56.grid(row=2, column=4, padx=10, pady=10)
    name_entry56.insert(0, 7.32)
    # sixth label
    name66 = Label(frame6, text='Clothes Tax', font=('Bold', 12), fg='white',
                   bd=0, bg='black', relief=FLAT)
    name66.grid(row=2, column=5, padx=10, pady=10)
    name_entry66 = Entry(frame6, width=20, bd=5, fg="blue")
    name_entry66.grid(row=2, column=6, padx=10, pady=10)
    name_entry66.insert(0, 23)
    # functional Buttons
    Total_button = Button(frame6, text="Total", fg="white", bg="black", width=15, height=2, bd=10
                          , command=lambda: Total()). \
        grid(row=1, column=7, padx=50, pady=20)
    Bill_button = Button(frame6, text="Bill", fg="white", bg="black", width=15, height=2, bd=10
                         , command=lambda: Bill()). \
        grid(row=1, column=8, padx=50, pady=20)
    Exit_button = Button(frame6, text="Exit", fg="white", bg="black", width=15, height=2, bd=10
                         , command=lambda: exit()). \
        grid(row=1, column=9, padx=50, pady=20)
    frame6.pack(fill=X)


root.mainloop()
