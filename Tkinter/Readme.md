# Python Tkinter Tutorial

This Tkinter tutorial covers both basic and advanced concepts to help beginners and professionals create graphical user interfaces for desktop-based applications using Python.

## Introduction to Tkinter

Python provides the standard library Tkinter for building desktop GUI applications. It simplifies the process of creating user interfaces.

To create an empty Tkinter top-level window, follow these steps:

1. Import the Tkinter module.
2. Create the main application window.
3. Add widgets like labels, buttons, frames, etc., to the window.
4. Call the main event loop so that actions can take place on the user's screen.

```python
# Import the Tkinter module
from tkinter import *

# Create the main application window
top = Tk()

# Enter the event main loop
top.mainloop()
```

## Tkinter Widgets

Tkinter provides various widgets such as buttons, canvas, checkbuttons, entries, frames, labels, listboxes, menubuttons, menus, messages, radiobuttons, scales, scrollbars, text fields, toplevel windows, spinboxes, paned windows, label frames, and message boxes.

Here's a summary of some commonly used widgets:

| SN  | Widget       | Description                                                  |
| --- | ------------ | ------------------------------------------------------------ |
| 1   | Button       | Adds various kinds of buttons to the application.            |
| 2   | Canvas       | Used to draw graphics on the window.                         |
| 3   | Checkbutton  | Displays a checkbox.                                         |
| 4   | Entry        | Displays a single-line text field.                           |
| 5   | Frame        | Container for other widgets.                                 |
| 6   | Label        | Displays text or information.                                |
| 7   | ListBox      | Displays a list of options.                                  |
| 8   | Menubutton   | Displays menu items.                                         |
| 9   | Menu         | Adds menus to the application.                               |
| 10  | Message      | Displays a message box.                                      |
| 11  | Radiobutton  | Provides multiple options for the user to select one.        |
| 12  | Scale        | Provides a slider for the user.                              |
| 13  | Scrollbar    | Adds scrollbars to the window.                               |
| 14  | Text         | Displays multi-line text field.                             |
| 15  | Toplevel     | Creates a separate window container.                        |
| 16  | Spinbox      | Selects values from options.                                 |
| 17  | PanedWindow  | Contains horizontal or vertical panes.                       |
| 18  | LabelFrame   | Container widget acting as a frame with a border and title. |
| 19  | MessageBox   | Displays message boxes in desktop applications.              |

## Tkinter Geometry Management

Tkinter offers three geometry management methods:

1. **pack() method**: Organizes widgets in a block.
2. **grid() method**: Organizes widgets in a tabular form.
3. **place() method**: Organizes widgets using specific x and y coordinates.

Let's explore each method:

### pack() method

The `pack()` method organizes widgets in blocks. Options can control the position and behavior of widgets.

```python
widget.pack(options)
```

Options include `expand`, `fill`, and `side`.

### grid() method

The `grid()` method organizes widgets in a tabular form, allowing specification of rows, columns, and spans.

```python
widget.grid(options)
```

Options include `row`, `column`, `columnspan`, `rowspan`, `ipadx`, `ipady`, `padx`, `pady`, and `sticky`.

### place() method

The `place()` method positions widgets using specific x and y coordinates.

```python
widget.place(options)
```

Options include `x`, `y`, `height`, `width`, `relx`, `rely`, `relheight`, `relwidth`, `anchor`, and `bordermode`.


# Python Tkinter Button Widget

The button widget in Tkinter allows developers to add various types of buttons to their Python applications. These buttons can be configured to meet specific requirements, including appearance and behavior. Additionally, methods or functions can be associated with buttons to execute tasks when they are clicked.

## Button Widget Syntax

The syntax to create a button widget is as follows:

```python
W = Button(parent, options)
```

Here's a list of possible options that can be configured:

| SN  | Option             | Description                                                  |
| --- | ------------------ | ------------------------------------------------------------ |
| 1   | activebackground   | Background color when the mouse hovers over the button.      |
| 2   | activeforeground   | Font color when the mouse hovers over the button.            |
| 3   | Bd                 | Border width in pixels.                                      |
| 4   | Bg                 | Background color of the button.                              |
| 5   | Command            | Function called when the button is pressed.                  |
| 6   | Fg                 | Foreground color of the button.                              |
| 7   | Font               | Font of the button text.                                     |
| 8   | Height             | Height of the button (in text lines or pixels for images).   |
| 9   | Highlightcolor     | Color of the highlight when the button has focus.            |
| 10  | Image              | Image displayed on the button.                               |
| 11  | justify            | Text justification (LEFT, RIGHT, CENTER).                    |
| 12  | Padx               | Additional padding in the horizontal direction.              |
| 13  | Pady               | Additional padding in the vertical direction.                |
| 14  | Relief             | Border type (SUNKEN, RAISED, GROOVE, RIDGE).                 |
| 15  | State              | Button state (DISABLED, ACTIVE).                             |
| 16  | Underline          | Set to underline button text.                                |
| 17  | Width              | Width of the button (in letters or pixels).                  |
| 18  | Wraplength         | Text wrap length.                                            |

## Examples

### Simple Button

```python
from tkinter import *

top = Tk()
top.geometry("200x100")
b = Button(top, text="Simple")
b.pack()
top.mainloop()
```

### Button with Functions

```python
from tkinter import *
from tkinter import messagebox

top = Tk()
top.geometry("200x200")

def fun():
    messagebox.showinfo("Hello", "Red Button clicked")

b1 = Button(top, text="Red", command=fun, activeforeground="red", activebackground="pink", pady=10)
b2 = Button(top, text="Blue", activeforeground="blue", activebackground="pink", pady=10)
b3 = Button(top, text="Green", activeforeground="green", activebackground="pink", pady=10)
b4 = Button(top, text="Yellow", activeforeground="yellow", activebackground="pink", pady=10)

b1.pack(side=LEFT)
b2.pack(side=RIGHT)
b3.pack(side=TOP)
b4.pack(side=BOTTOM)

top.mainloop()
```

# Python Tkinter Canvas Widget

The canvas widget in Tkinter allows developers to add structured graphics, including graphs and plots, to their Python applications. It provides a versatile tool for creating visual elements dynamically.

## Canvas Widget Syntax

The syntax to create a canvas widget is as follows:

```python
w = Canvas(parent, options)
```

Here's a list of possible options that can be configured:

| SN  | Option            | Description                                           |
| --- | ----------------- | ----------------------------------------------------- |
| 1   | bd                | Border width (default is 2).                          |
| 2   | bg                | Background color of the canvas.                       |
| 3   | confine           | Makes the canvas unscrollable outside the region.     |
| 4   | cursor            | Cursor style on the canvas (arrow, circle, dot, etc). |
| 5   | height            | Height of the canvas.                                 |
| 6   | highlightcolor    | Color when the canvas is focused.                     |
| 7   | relief            | Border type (SUNKEN, RAISED, GROOVE, RIDGE).          |
| 8   | scrollregion      | Coordinates specifying the canvas area.               |
| 9   | width             | Width of the canvas.                                  |
| 10  | xscrollincrement  | Increment for horizontal scrolling.                  |
| 11  | xscrollcommand    | Command for horizontal scrollbar.                     |
| 12  | yscrollincrement  | Increment for vertical scrolling.                    |
| 13  | yscrollcommand    | Command for vertical scrollbar.                       |

## Examples

### Simple Canvas

```python
from tkinter import *

top = Tk()
top.geometry("200x200")

# Create a simple canvas
c = Canvas(top, bg="pink", height=200)

c.pack()

top.mainloop()
```

### Creating an Arc on Canvas

```python
from tkinter import *

top = Tk()
top.geometry("200x200")

# Create a simple canvas
c = Canvas(top, bg="pink", height=200, width=200)

# Create an arc
arc = c.create_arc((5, 10, 150, 200), start=0, extent=150, fill="white")

c.pack()

top.mainloop()
```

# Python Tkinter Checkbutton Widget

The Checkbutton widget in Tkinter is used to track the user's choices within the application. It provides a mechanism for implementing on/off selections, allowing users to make multiple selections from a set of options.

## Checkbutton Widget Syntax

The syntax to create a Checkbutton widget is as follows:

```python
w = Checkbutton(master, options)
```

Here's a list of possible options that can be configured:

| SN  | Option             | Description                                                      |
| --- | ------------------ | ---------------------------------------------------------------- |
| 1   | activebackground   | Background color when the checkbutton is under the cursor.       |
| 2   | activeforeground   | Foreground color when the checkbutton is under the cursor.       |
| 3   | bg                 | Background color of the button.                                  |
| 4   | bitmap             | Image (monochrome) displayed on the button.                      |
| 5   | bd                 | Border size around the corner.                                   |
| 6   | command            | Function called when the state of the checkbutton is changed.    |
| 7   | cursor             | Cursor style when over the checkbutton.                          |
| 8   | disableforeground | Color of the text of a disabled checkbutton.                    |
| 9   | font               | Font of the checkbutton text.                                    |
| 10  | fg                 | Foreground color (text color) of the checkbutton.                |
| 11  | height             | Height of the checkbutton (number of lines).                     |
| 12  | highlightcolor     | Color of the focus highlight when the checkbutton is focused.    |
| 13  | image              | Image used to represent the checkbutton.                         |
| 14  | justify            | Text justification if it contains multiple lines.                |
| 15  | offvalue           | Value when the button is unchecked.                              |
| 16  | onvalue            | Value when the button is checked.                                |
| 17  | padx               | Horizontal padding of the checkbutton.                           |
| 18  | pady               | Vertical padding of the checkbutton.                             |
| 19  | relief             | Border type of the checkbutton.                                  |
| 20  | selectcolor        | Color of the checkbutton when it is set.                         |
| 21  | selectimage        | Image shown on the checkbutton when it is set.                   |
| 22  | state              | State of the checkbutton (normal, DISABLED, ACTIVE).             |
| 23  | underline          | Index of the character in the text to be underlined.             |
| 24  | variable           | Associated variable tracking the state of the checkbutton.       |
| 25  | width              | Width of the checkbutton (number of characters).                 |
| 26  | wraplength         | Text wrapping length.                                            |

## Checkbutton Widget Methods

Here are the methods that can be called with Checkbuttons:

1. `deselect()`: Turn off the checkbutton.
2. `flash()`: Flash the checkbutton between active and normal colors.
3. `invoke()`: Invoke the method associated with the checkbutton.
4. `select()`: Turn on the checkbutton.
5. `toggle()`: Toggle between different checkbuttons.

## Example

```python
from tkinter import *

top = Tk()
top.geometry("200x200")

checkvar1 = IntVar()
checkvar2 = IntVar()
checkvar3 = IntVar()

chkbtn1 = Checkbutton(top, text="C", variable=checkvar1, onvalue=1, offvalue=0, height=2, width=10)
chkbtn2 = Checkbutton(top, text="C++", variable=checkvar2, onvalue=1, offvalue=0, height=2, width=10)
chkbtn3 = Checkbutton(top, text="Java", variable=checkvar3, onvalue=1, offvalue=0, height=2, width=10)

chkbtn1.pack()
chkbtn2.pack()
chkbtn3.pack()

top.mainloop()
```

# Python Tkinter Entry Widget

The Entry widget in Tkinter provides a single-line text box for users to input values into the application. It is commonly used to accept text strings from users and supports basic text entry functionalities.

## Entry Widget Syntax

The syntax to create an Entry widget is as follows:

```python
w = Entry(parent, options)
```

Here's a list of possible options that can be configured:

| SN  | Option              | Description                                                        |
| --- | ------------------- | ------------------------------------------------------------------ |
| 1   | bg                  | Background color of the widget.                                    |
| 2   | bd                  | Border width of the widget in pixels.                              |
| 3   | cursor              | Cursor style when over the entry (arrow, dot, etc).                |
| 4   | exportselection     | Controls whether text is copied to the clipboard automatically.    |
| 5   | fg                  | Text color.                                                        |
| 6   | font                | Font type of the text.                                             |
| 7   | highlightbackground | Color displayed in the traversal highlight region when unfocused.  |
| 8   | highlightcolor      | Color of the traversal highlight rectangle when focused.           |
| 9   | highlightthickness  | Width of the highlight rectangle.                                  |
| 10  | insertbackground    | Background color in the area covered by the insertion cursor.      |
| 11  | insertborderwidth   | Width of the 3-D border around the insertion cursor.               |
| 12  | insertofftime       | Time the insertion cursor remains "off" in each blink cycle.        |
| 13  | insertontime        | Time the insertion cursor remains "on" in each blink cycle.         |
| 14  | insertwidth         | Total width of the insertion cursor.                               |
| 15  | justify             | Text organization (LEFT, RIGHT, CENTER).                            |
| 16  | relief              | Border type (FLAT, RAISED, SUNKEN, etc).                           |
| 17  | selectbackground    | Background color of selected text.                                 |
| 18  | selectborderwidth   | Width of the border around selected text.                          |
| 19  | selectforeground    | Text color of selected text.                                       |
| 20  | show                | Show different text instead of the string (e.g., password).         |
| 21  | textvariable        | StringVar instance to retrieve text from the entry.                 |
| 22  | width               | Width of the displayed text or image.                               |
| 23  | xscrollcommand      | Link to a horizontal scrollbar.                                    |

## Entry Widget Methods

Here are the methods that can be called with Entry widgets:

1. `delete(first, last = none)`: Delete specified characters.
2. `get()`: Retrieve the text inside the widget.
3. `icursor(index)`: Change the insertion cursor position.
4. `index(index)`: Place the cursor to the left of a character.
5. `insert(index,s)`: Insert a string at a specified index.
6. `select_adjust(index)`: Include the selection of a character.
7. `select_clear()`: Clear the selection.
8. `select_form(index)`: Set the anchor index position.
9. `select_present()`: Check if text in the Entry is selected.
10. `select_range(start,end)`: Select characters within a range.
11. `select_to(index)`: Select characters from the beginning to a specified index.
12. `xview(index)`: Link to a horizontal scrollbar.
13. `xview_scroll(number,what)`: Make the entry scrollable horizontally.

## Example: A Simple Calculator

```python
import tkinter as tk
from functools import partial

def call_result(label_result, n1, n2):
    num1 = (n1.get())
    num2 = (n2.get())
    result = int(num1) + int(num2)
    label_result.config(text="Result = %d" % result)
    return

root = tk.Tk()
root.geometry('400x200+100+200')
root.title('Calculator')

number1 = tk.StringVar()
number2 = tk.StringVar()

labelNum1 = tk.Label(root, text="A").grid(row=1, column=0)
labelNum2 = tk.Label(root, text="B").grid(row=2, column=0)
labelResult = tk.Label(root)
labelResult.grid(row=7, column=2)

entryNum1 = tk.Entry(root, textvariable=number1).grid(row=1, column=2)
entryNum2 = tk.Entry(root, textvariable=number2).grid(row=2, column=2)

call_result = partial(call_result, labelResult, number1, number2)

buttonCal = tk.Button(root, text="Calculate", command=call_result).grid(row=3, column=0)

root.mainloop()
```

