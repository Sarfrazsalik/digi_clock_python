# digi_clock_python
from tkinter import *
from tkinter.ttk import *
from datetime import datetime


# window configuration
window = Tk()
window.title(" DIGITAL CLOCK")
window.geometry('400x150')

bg_color = "#faf9f5"
f_color = "#34b1eb"

window.resizable(width=True, height=True)
window.configure(bg=bg_color)


def clock():
    time = datetime.now()
    hour = time.strftime('%H:%M:%S ')
    weekday = time.strftime('%A')
    day = time.day
    month = time.strftime('%b')
    year = time.strftime('%y')
    l1.configure(text=hour)
    l1.after(1000, clock)
    l2.configure(text=weekday + "   " + str(day) +
                 "/" + str(month) + "/" + str(year))


l1 = Label(window, text="12:49:05", font=(
    "ds-digital", 80), background=bg_color)
l1.grid(row=0, column=0, padx=3, sticky=NW)


l2 = Label(window, text="Saturday 22/05/23",
           font=("ds-digital", 20), background=bg_color,foreground=f_color)
l2.grid(row=1, column=0, padx=3, sticky=NW)


clock()


window.mainloop()
 
