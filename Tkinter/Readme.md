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

# Python Tkinter Frame Widget

The Frame widget in Tkinter serves as a container to organize groups of other widgets within a rectangular area of the screen. It allows developers to group related widgets together for better organization and layout management in GUI applications.

## Frame Widget Syntax

The syntax to create a Frame widget is as follows:

```python
w = Frame(parent, options)
```

Here's a list of possible options that can be configured:

| SN  | Option              | Description                                                 |
| --- | ------------------- | ----------------------------------------------------------- |
| 1   | bd                  | Border width.                                               |
| 2   | bg                  | Background color of the widget.                             |
| 3   | cursor              | Cursor style when over the frame (arrow, dot, etc).         |
| 4   | height              | Height of the frame.                                        |
| 5   | highlightbackground | Color of the background when the frame is under focus.      |
| 6   | highlightcolor      | Color of the text when the frame is under focus.            |
| 7   | highlightthickness  | Thickness around the border when the frame is under focus.   |
| 8   | relief              | Border type (FLAT, RAISED, SUNKEN, etc).                    |
| 9   | width               | Width of the frame.                                         |

## Example

```python
from tkinter import *

top = Tk()
top.geometry("140x100")

# Creating a main frame
frame = Frame(top)
frame.pack()

# Creating frames on the left and right sides of the main frame
leftframe = Frame(top)
leftframe.pack(side=LEFT)

rightframe = Frame(top)
rightframe.pack(side=RIGHT)

# Adding buttons to the main frame
btn1 = Button(frame, text="Submit", fg="red", activebackground="red")
btn1.pack(side=LEFT)

btn2 = Button(frame, text="Remove", fg="brown", activebackground="brown")
btn2.pack(side=RIGHT)

# Adding buttons to the right frame
btn3 = Button(rightframe, text="Add", fg="blue", activebackground="blue")
btn3.pack(side=LEFT)

# Adding buttons to the left frame
btn4 = Button(leftframe, text="Modify", fg="black", activebackground="white")
btn4.pack(side=RIGHT)

top.mainloop()
```

# Python Tkinter Label Widget

The Label widget in Tkinter is used to display text or images within a container box. It's commonly used to provide information or messages to users about other widgets or functionalities within the Python application.

## Label Widget Syntax

The syntax to create a Label widget is as follows:

```python
w = Label(master, options)
```

Here's a list of possible options that can be configured:

| SN  | Option         | Description                                                                                     |
| --- | -------------- | ----------------------------------------------------------------------------------------------- |
| 1   | anchor         | Specifies the position of the text within the widget. Default is CENTER.                        |
| 2   | bg             | Background color displayed behind the widget.                                                   |
| 3   | bitmap         | Sets a bitmap to the graphical object specified, allowing the label to represent graphics.      |
| 4   | bd             | Border width in pixels. Default is 2 pixels.                                                    |
| 5   | cursor         | Changes the mouse pointer to the specified cursor type (arrow, dot, etc.).                      |
| 6   | font           | Font type of the text displayed inside the widget.                                              |
| 7   | fg             | Foreground color of the text displayed inside the widget.                                        |
| 8   | height         | Height of the widget.                                                                           |
| 9   | image          | Image to be displayed as the label.                                                             |
| 10  | justify        | Orientation of the text if it contains multiple lines (LEFT, RIGHT, CENTER).                    |
| 11  | padx           | Horizontal padding of the text. Default value is 1.                                              |
| 12  | pady           | Vertical padding of the text. Default value is 1.                                                |
| 13  | relief         | Type of border. Default value is FLAT.                                                          |
| 14  | text           | String variable containing one or more lines of text.                                             |
| 15  | textvariable   | Control variable (StringVar) to access and modify the text displayed inside the widget.         |
| 16  | underline      | Displays a line under the specified letter of the text.                                          |
| 17  | width          | Width of the widget, specified in number of characters.                                          |
| 18  | wraplength     | Breaks the text into multiple lines, specifying the number of characters for each line.         |

## Example

```python
from tkinter import *

top = Tk()
top.geometry("400x250")

# Creating labels
uname = Label(top, text="Username").place(x=30, y=50)
password = Label(top, text="Password").place(x=30, y=90)

# Creating button
sbmitbtn = Button(top, text="Submit", activebackground="pink", activeforeground="blue").place(x=30, y=120)

# Creating entry fields
e1 = Entry(top, width=20).place(x=100, y=50)
e2 = Entry(top, width=20).place(x=100, y=90)

top.mainloop()
```


Certainly! Below is a revised version of the explanation in a README.md format:

# Python Tkinter Listbox

The `Listbox` widget in Tkinter is designed to display a list of items to the user. It supports the display of text items only, all with the same font and color.

Users can select one or more items from the list based on the configuration provided.

## Syntax

```python
w = Listbox(parent, options)
```

## Options

Here are the available options for the Listbox widget:

| Option             | Description                                                  |
|--------------------|--------------------------------------------------------------|
| bg                 | Background color of the widget.                              |
| bd                 | Size of the border. Default value is 2 pixels.              |
| cursor             | Mouse pointer appearance (e.g., dot, arrow).                 |
| font               | Font type of the Listbox items.                              |
| fg                 | Text color.                                                  |
| height             | Number of lines shown in the Listbox (default is 10).        |
| highlightcolor     | Color of Listbox items when the widget is focused.           |
| highlightthickness | Thickness of the highlight.                                   |
| relief             | Border type (default is SUNKEN).                              |
| selectbackground   | Background color for selected text.                          |
| selectmode         | Selection mode (BROWSE, SINGLE, MULTIPLE, EXTENDED).         |
| width              | Width of the widget in characters.                           |
| xscrollcommand     | Horizontal scrolling command.                                 |
| yscrollcommand     | Vertical scrolling command.                                   |

## Methods

The following methods are associated with the Listbox:

| Method             | Description                                                  |
|--------------------|--------------------------------------------------------------|
| activate(index)    | Selects lines at the specified index.                        |
| curselection()     | Returns a tuple containing the line numbers of selected elements. |
| delete(first, last = None) | Deletes lines in the given range.                            |
| get(first, last = None) | Retrieves list items within the given range.                |
| index(i)           | Places the line with the specified index at the top of the widget. |
| insert(index, *elements) | Inserts new lines before the specified index.             |
| nearest(y)         | Returns the index of the nearest line to the y coordinate.   |
| see(index)         | Adjusts the position of the listbox to make specified lines visible. |
| size()             | Returns the number of lines present in the Listbox widget.   |
| xview()            | Makes the widget horizontally scrollable.                    |
| xview_moveto(fraction) | Makes the listbox horizontally scrollable by a fraction.    |
| xview_scroll(number, what) | Makes the listbox horizontally scrollable by the specified characters. |
| yview()            | Makes the Listbox vertically scrollable.                     |
| yview_moveto(fraction) | Makes the listbox vertically scrollable by a fraction.      |
| yview_scroll(number, what) | Makes the listbox vertically scrollable by the specified characters. |

## Examples

### Example 1: Displaying a List of Countries

```python
from tkinter import *

top = Tk()
top.geometry("200x250")

lbl = Label(top, text="A list of favorite countries...")

listbox = Listbox(top)
listbox.insert(1, "India")
listbox.insert(2, "USA")
listbox.insert(3, "Japan")
listbox.insert(4, "Australia")

lbl.pack()
listbox.pack()

top.mainloop()
```

### Example 2: Deleting Selected Items

```python
from tkinter import *

top = Tk()
top.geometry("200x250")

lbl = Label(top, text="A list of favorite countries...")

listbox = Listbox(top)
listbox.insert(1, "India")
listbox.insert(2, "USA")
listbox.insert(3, "Japan")
listbox.insert(4, "Australia")

# Button to delete the selected item from the list
btn = Button(top, text="delete", command=lambda listbox=listbox: listbox.delete(ANCHOR))

lbl.pack()
listbox.pack()
btn.pack()

top.mainloop()
```

Certainly! Below is the information provided in a README.md format:

# Python Tkinter Menubutton

The `Menubutton` widget in Tkinter provides a drop-down menu displayed to the user at all times. It allows users to select appropriate choices within the application.

## Syntax

```python
w = Menubutton(Top, options)
```

## Options

Here are the available options for the Menubutton widget:

| Option              | Description                                                  |
|---------------------|--------------------------------------------------------------|
| activebackground    | Background color of the widget when it's focused.            |
| activeforeground    | Font color of the widget text when it's focused.             |
| anchor              | Specifies the position of the widget content when it's given more space than needed. |
| bg                  | Background color of the widget.                              |
| bitmap              | Graphical content to be displayed on the widget.             |
| bd                  | Size of the border. Default value is 2 pixels.               |
| cursor              | Cursor type when the widget is focused.                      |
| direction           | Direction of the menu display (LEFT, RIGHT, ABOVE).          |
| disabledforeground  | Text color of the widget when it's disabled.                 |
| fg                  | Normal foreground color of the widget.                       |
| height              | Vertical dimension of the Menubutton.                        |
| highlightcolor      | Highlight color shown when the widget is focused.            |
| image               | Image displayed on the widget.                               |
| justify             | Position of the text under the widget.                       |
| menu                | Menu associated with the Menubutton.                         |
| padx                | Horizontal padding of the widget.                            |
| pady                | Vertical padding of the widget.                              |
| relief              | Type of the border. Default value is RAISED.                 |
| state               | State of the Mousebutton (ENABLED, DISABLED).                |
| text                | Text shown with the widget.                                  |
| textvariable        | Control variable of string type for controlling the text at runtime. |
| underline           | Underline the text of the widget.                            |
| width               | Width of the widget in characters.                           |
| wraplength          | Wrap the text of the widget in a specified number of lines.  |

## Example

### Displaying a Menubutton with Checkbuttons

```python
from tkinter import *

top = Tk()
top.geometry("200x250")

menubutton = Menubutton(top, text="Language", relief=FLAT)

menubutton.grid()

menubutton.menu = Menu(menubutton)

menubutton["menu"] = menubutton.menu

menubutton.menu.add_checkbutton(label="Hindi", variable=IntVar())
menubutton.menu.add_checkbutton(label="English", variable=IntVar())

menubutton.pack()

top.mainloop()
```

Here's the information provided in a README.md format:

# Python Tkinter Menu

The Menu widget in Tkinter allows you to create various types of menus including top-level, pull-down, and pop-up menus in a Python application.

## Syntax

```python
w = Menu(top, options)
```

## Options

Here are the available options for the Menu widget:

| Option              | Description                                                  |
|---------------------|--------------------------------------------------------------|
| activebackground    | Background color when the widget is focused.                 |
| activeborderwidth   | Width of the border when the mouse is over the widget.       |
| activeforeground    | Font color when the widget has focus.                        |
| bg                  | Background color of the widget.                              |
| bd                  | Border width of the widget.                                  |
| cursor              | Cursor type when hovering over the widget.                   |
| disabledforeground  | Font color when the widget is disabled.                      |
| font                | Font type of the text of the widget.                         |
| fg                  | Foreground color of the widget.                              |
| postcommand         | Function called when the mouse hovers over the menu.         |
| relief              | Type of the border.                                          |
| image               | Image displayed on the menu.                                 |
| selectcolor         | Color used for selected checkbuttons or radiobuttons.        |
| tearoff             | Start position of choices in the menu.                       |
| title               | Title of the window.                                         |

## Methods

The Menu widget provides the following methods:

| Method              | Description                                                  |
|---------------------|--------------------------------------------------------------|
| add_command(options)     | Add menu items to the menu.                                     |
| add_radiobutton(options)  | Add radiobuttons to the menu.                                    |
| add_checkbutton(options)  | Add checkbuttons to the menu.                                    |
| add_cascade(options)      | Create a hierarchical menu by associating a menu with the parent menu. |
| add_separator()           | Add a separator line to the menu.                                |
| add(type, options)        | Add a specific menu item to the menu.                            |
| delete(startindex, endindex) | Delete menu items within the specified range.                   |
| entryconfig(index, options)  | Configure a menu item identified by the index.                  |
| index(item)               | Get the index of a specified menu item.                          |
| insert_separator(index)   | Insert a separator at the specified index.                       |
| invoke(index)             | Invoke the associated action with the choice at the specified index. |
| type(index)               | Get the type of the choice specified by the index.               |

## Creating a Top-level Menu

You can create a top-level menu by instantiating the Menu widget and adding menu items to it.

### Example 1

```python
from tkinter import *

top = Tk()

def hello():
    print("Hello!")

menubar = Menu(top)
menubar.add_command(label="Hello!", command=hello)
menubar.add_command(label="Quit!", command=top.quit)

top.config(menu=menubar)

top.mainloop()
```

Clicking "Hello!" will print "Hello!" to the console, while clicking "Quit!" will exit the Python application.

### Example 2

```python
from tkinter import Toplevel, Button, Tk, Menu

top = Tk()
menubar = Menu(top)

file = Menu(menubar, tearoff=0)
file.add_command(label="New")
file.add_command(label="Open")
file.add_command(label="Save")
file.add_command(label="Save as...")
file.add_command(label="Close")
file.add_separator()
file.add_command(label="Exit", command=top.quit)

menubar.add_cascade(label="File", menu=file)

edit = Menu(menubar, tearoff=0)
edit.add_command(label="Undo")
edit.add_separator()
edit.add_command(label="Cut")
edit.add_command(label="Copy")
edit.add_command(label="Paste")
edit.add_command(label="Delete")
edit.add_command(label="Select All")

menubar.add_cascade(label="Edit", menu=edit)

help_menu = Menu(menubar, tearoff=0)
help_menu.add_command(label="About")
menubar.add_cascade(label="Help", menu=help_menu)

top.config(menu=menubar)
top.mainloop()
```

This creates a more elaborate menu structure with file, edit, and help options.


Here's the information provided in a README.md format:

# Python Tkinter Message

The Message widget in Tkinter is used to display messages to the user regarding the behavior of the Python application. The message displayed by the Message widget cannot be edited and typically contains multiple lines of text.

## Syntax

```python
w = Message(parent, options)
```

## Options

Here are the available options for the Message widget:

| Option       | Description                                                  |
|--------------|--------------------------------------------------------------|
| anchor       | Position of the text within the widget if there's extra space. Default is CENTER. |
| bg           | Background color of the widget.                              |
| bitmap       | Graphics or image displayed on the widget.                   |
| bd           | Border size in pixels. Default is 2 pixels.                  |
| cursor       | Cursor type when hovering over the widget.                   |
| font         | Font type of the widget text.                                |
| fg           | Font color of the widget text.                               |
| height       | Vertical dimension of the message.                           |
| image        | Static image displayed on the widget.                         |
| justify      | Text alignment (LEFT, CENTER, RIGHT). Default is CENTER.     |
| padx         | Horizontal padding of the widget.                            |
| pady         | Vertical padding of the widget.                              |
| relief       | Border type. Default is FLAT.                                |
| text         | Text displayed by the widget.                                |
| textvariable | Control variable for the text displayed by the widget.       |
| underline    | Index of the letter to be underlined. Default is -1 (no underline). |
| width        | Horizontal dimension in characters.                          |
| wraplength   | Number of characters per line for wrapping the text.         |

## Example

```python
from tkinter import *

top = Tk()
top.geometry("100x100")
var = StringVar()
msg = Message(top, text="Welcome")

msg.pack()
top.mainloop()
```

This example creates a simple Message widget displaying the text "Welcome".


Here's the information provided in a README.md format:

# Python Tkinter Radiobutton

The Radiobutton widget in Tkinter is used to implement one-of-many selection in a Python application. Users can choose only one option among several presented choices. Each Radiobutton is associated with a single variable, and selecting one Radiobutton changes the value of that variable.

## Syntax

```python
w = Radiobutton(top, options)
```

## Options

Here are the available options for the Radiobutton widget:

| Option              | Description                                                  |
|---------------------|--------------------------------------------------------------|
| activebackground    | Background color when the widget has focus.                  |
| activeforeground    | Font color when the widget has focus.                        |
| anchor              | Position of the text within the widget.                      |
| bg                  | Background color of the widget.                              |
| bitmap              | Graphics or image displayed on the widget.                   |
| borderwidth         | Border size.                                                 |
| command             | Procedure called every time the state of the Radiobutton changes. |
| cursor              | Cursor type when hovering over the widget.                   |
| font                | Font type of the widget text.                                |
| fg                  | Foreground color of the widget text.                         |
| height              | Vertical dimension of the widget.                            |
| highlightcolor      | Color of the focus highlight.                                |
| highlightbackground | Background color of the focus highlight.                     |
| image               | Image displayed on the Radiobutton instead of text.          |
| justify             | Justification of multi-line text.                            |
| padx                | Horizontal padding of the widget.                            |
| pady                | Vertical padding of the widget.                              |
| relief              | Border type.                                                 |
| selectcolor         | Color of the Radiobutton when selected.                      |
| selectimage         | Image displayed when the Radiobutton is selected.            |
| state               | State of the Radiobutton (NORMAL or DISABLED).               |
| text                | Text displayed on the Radiobutton.                           |
| textvariable        | Control variable for the text displayed by the widget.       |
| underline           | Index of the character to be underlined.                     |
| value               | Value assigned to the control variable when the Radiobutton is selected. |
| variable            | Control variable used to keep track of user's choices.       |
| width               | Horizontal dimension of the widget.                          |
| wraplength          | Number of characters per line for wrapping the text.         |

## Methods

The Radiobutton widget provides the following methods:

| Method    | Description                                                  |
|-----------|--------------------------------------------------------------|
| deselect()| Turn off the Radiobutton.                                   |
| flash()   | Flash the Radiobutton between active and normal colors.      |
| invoke()  | Call any procedure associated when the state of a Radiobutton is changed. |
| select()  | Select the Radiobutton.                                     |

## Example

```python
from tkinter import *

def selection():
   selection = "You selected the option " + str(radio.get())
   label.config(text = selection)

top = Tk()
top.geometry("300x150")
radio = IntVar()
lbl = Label(text = "Favourite programming language:")
lbl.pack()
R1 = Radiobutton(top, text="C", variable=radio, value=1,
                  command=selection)
R1.pack(anchor = W )

R2 = Radiobutton(top, text="C++", variable=radio, value=2,
                  command=selection)
R2.pack(anchor = W )

R3 = Radiobutton(top, text="Java", variable=radio, value=3,
                  command=selection)
R3.pack(anchor = W)

label = Label(top)
label.pack()
top.mainloop()
```

This example creates Radiobuttons for selecting favorite programming languages and displays the selected option.



# Python Tkinter Scale Widget

The Scale widget in Python's Tkinter library allows you to implement a graphical slider within your application. Users can slide through a range of values displayed on the slider and select one among them.

## Syntax
```python
w = Scale(top, options)
```

Here's a list of possible options you can use with the Scale widget:

| **Option**           | **Description**                                                                                          |
|----------------------|----------------------------------------------------------------------------------------------------------|
| `activebackground`   | Background color of the widget when it has focus.                                                        |
| `bg`                 | Background color of the widget.                                                                          |
| `bd`                 | Border size of the widget (default is 2 pixels).                                                         |
| `command`            | Procedure called each time the slider moves.                                                             |
| `cursor`             | Cursor type assigned to the widget.                                                                      |
| `digits`             | Number of digits when the numeric scale is converted to a string.                                        |
| `font`               | Font type of the widget text.                                                                            |
| `fg`                 | Foreground color of the text.                                                                            |
| `from_`              | One end of the widget range.                                                                             |
| `highlightbackground`| Highlight color when the widget doesn't have focus.                                                      |
| `highlightcolor`     | Highlight color when the widget has focus.                                                                |
| `label`              | Text shown as a label with the scale.                                                                    |
| `length`             | Length of the widget (X dimension if horizontal, Y dimension if vertical).                                |
| `orient`             | Orientation of the scale (horizontal or vertical).                                                        |
| `relief`             | Type of border (default is FLAT).                                                                        |
| `repeatdelay`        | Duration before the slider starts moving repeatedly.                                                      |
| `resolution`         | Smallest change made to the scale value.                                                                  |
| `showvalue`          | Whether to show the value of the scale.                                                                   |
| `sliderlength`       | Length of the slider window along the length of the scale.                                                |
| `state`              | State of the scale widget (ACTIVE by default).                                                            |
| `takefocus`          | Whether focus cycles through the scale widgets.                                                           |
| `tickinterval`       | Display of scale values on multiples of the specified tick interval.                                      |
| `to`                 | Float or integer specifying the other end of the range represented by the scale.                          |
| `troughcolor`        | Color of the trough.                                                                                     |
| `variable`           | Control variable for the scale.                                                                          |
| `width`              | Width of the trough part of the widget.                                                                   |

## Methods
Here are some useful methods associated with the Scale widget:

- `get()`: Get the current value of the scale.
- `set(value)`: Set the value of the scale.

## Example
```python
from tkinter import *

def select():
    sel = "Value = " + str(v.get())
    label.config(text=sel)

top = Tk()
top.geometry("200x100")
v = DoubleVar()
scale = Scale(top, variable=v, from_=1, to=50, orient=HORIZONTAL)
scale.pack(anchor=CENTER)

btn = Button(top, text="Value", command=select)
btn.pack(anchor=CENTER)

label = Label(top)
label.pack()

top.mainloop()
```

This code creates a Tkinter application with a horizontal scale, a button, and a label. Users can select values from the scale, and clicking the button displays the selected value.



# Python Tkinter Scrollbar Widget

The Scrollbar widget in Tkinter is used to scroll down the content of other widgets such as Listbox, Text, and Canvas. Additionally, it can create horizontal scrollbars for the Entry widget.

## Syntax
```python
w = Scrollbar(top, options)
```

Here are the options you can use with the Scrollbar widget:

| **Option**            | **Description**                                                  |
|-----------------------|------------------------------------------------------------------|
| `activebackground`    | Background color of the widget when it has focus.                |
| `bg`                  | Background color of the widget.                                   |
| `bd`                  | Border width of the widget.                                       |
| `command`             | Procedure associated with the scrollbar called when it's moved.  |
| `cursor`              | Cursor type when hovering over the scrollbar.                     |
| `elementborderwidth`  | Border width around the arrow heads and slider.                   |
| `highlightbackground` | Focus highlight color when the widget doesn't have focus.        |
| `highlightcolor`      | Focus highlight color when the widget has focus.                  |
| `highlightthickness`  | Thickness of the focus highlight.                                 |
| `jump`                | Control the behavior of scroll jump.                              |
| `orient`              | Orientation of the scrollbar (HORIZONTAL or VERTICAL).            |
| `repeatdelay`         | Duration before the slider starts moving repeatedly.              |
| `repeatinterval`      | Interval between repeat movements.                                |
| `takefocus`           | Whether to tab focus through the widget.                          |
| `troughcolor`         | Color of the scrollbar trough.                                    |
| `width`               | Width of the scrollbar.                                           |

## Methods
The Scrollbar widget provides the following methods:

| **Method** | **Description**                                                                         |
|------------|-----------------------------------------------------------------------------------------|
| `get()`    | Returns the current position of the scrollbar.                                         |
| `set(first, last)` | Connects the scrollbar to another widget and specifies the yscrollcommand or xscrollcommand. |

## Example
```python
from tkinter import *

top = Tk()
sb = Scrollbar(top)
sb.pack(side=RIGHT, fill=Y)

mylist = Listbox(top, yscrollcommand=sb.set)

for line in range(30):
    mylist.insert(END, "Number " + str(line))

mylist.pack(side=LEFT)
sb.config(command=mylist.yview)

mainloop()
```

This code creates a Tkinter application with a Listbox and a vertical scrollbar. Users can scroll through the list of items using the scrollbar.


# Python Tkinter Text Widget

The Text widget in Tkinter is used to display multi-line formatted text with various styles and attributes. It serves as a text editor where users can input and view text content.

## Syntax
```python
w = Text(top, options)
```

Here are the options you can use with the Text widget:

| **Option**          | **Description**                                                   |
|---------------------|-------------------------------------------------------------------|
| `bg`                | Background color of the widget.                                   |
| `bd`                | Border width of the widget.                                       |
| `cursor`            | Cursor type when hovering over the widget.                        |
| `exportselection`   | Whether the selected text is exported to the window manager.      |
| `font`              | Font type of the text.                                            |
| `fg`                | Text color of the widget.                                         |
| `height`            | Vertical dimension of the widget in lines.                        |
| `highlightbackground` | Highlight color when the widget doesn't have focus.              |
| `highlightthickness` | Thickness of the focus highlight.                                 |
| `highlightcolor`    | Highlight color when the widget has focus.                        |
| `insertbackground`  | Color of the insertion cursor.                                    |
| `insertborderwidth` | Width of the border around the cursor.                            |
| `insertofftime`     | Time in milliseconds during which the insertion cursor is off.    |
| `insertontime`      | Time in milliseconds during which the insertion cursor is on.     |
| `insertwidth`       | Width of the insertion cursor.                                    |
| `padx`              | Horizontal padding of the widget.                                 |
| `pady`              | Vertical padding of the widget.                                   |
| `relief`            | Type of the border.                                               |
| `selectbackground`  | Background color of the selected text.                            |
| `selectborderwidth` | Width of the border around the selected text.                     |
| `spacing1`          | Vertical space above each line of text.                           |
| `spacing2`          | Extra vertical space between displayed lines of text.             |
| `spacing3`          | Vertical space below each line of text.                           |
| `state`             | State of the widget (DISABLED makes it unresponsive).             |
| `tabs`              | Control how the tab character is used to position the text.       |
| `width`             | Width of the widget in characters.                                |
| `wrap`              | Wrap lines (WORD or CHAR).                                        |
| `xscrollcommand`    | Connect to horizontal scrollbar.                                  |
| `yscrollcommand`    | Connect to vertical scrollbar.                                    |

## Methods
Here are some useful methods associated with the Text widget:

| **Method**          | **Description**                                                  |
|---------------------|-------------------------------------------------------------------|
| `delete(start, end)`| Delete characters within the specified range.                    |
| `get(start, end)`   | Get characters within the specified range.                       |
| `index(index)`      | Get the absolute index of the specified index.                   |
| `insert(index, string)` | Insert the specified string at the given index.                |
| `see(index)`        | Check if text at the specified index is visible.                 |
| **Mark Handling Methods** |                                                   |
| `index(mark)`       | Get the index of the specified mark.                             |
| `mark_gravity(mark, gravity)` | Get the gravity of the mark.                                  |
| `mark_names()`      | Get all marks present in the Text widget.                        |
| `mark_set(mark, index)` | Set a new position for the mark.                               |
| `mark_unset(mark)`  | Remove the specified mark from the text.                         |
| **Tag Handling Methods** |                                                    |
| `tag_add(tagname, start, end)` | Tag the string within the specified range.                   |
| `tag_config(tagname, **options)` | Configure tag properties.                                    |
| `tag_delete(tagname)` | Delete a given tag.                                            |
| `tag_remove(tagname, start, end)` | Remove a tag from the specified range.                      |

## Example
```python
from tkinter import *

top = Tk()
text = Text(top)
text.insert(INSERT, "Name.....")
text.insert(END, "Salary.....")

text.pack()

text.tag_add("Write Here", "1.0", "1.4")
text.tag_add("Click Here", "1.8", "1.13")

text.tag_config("Write Here", background="yellow", foreground="black")
text.tag_config("Click Here", background="black", foreground="white")

top.mainloop()
```

This code creates a Tkinter application with a Text widget. Different parts of the text are tagged and configured with different background and foreground colors.


# Python Tkinter Toplevel Widget

The Toplevel widget in Tkinter is used to create and display top-level windows that are managed directly by the window manager. These windows may or may not have a parent window on top of them.

Toplevel widgets are typically used to represent additional information, pop-ups, or groups of widgets on new windows. They come with title bars, borders, and other window decorations.

## Syntax
```python
w = Toplevel(options)
```

Here are the options you can use with the Toplevel widget:

| **Option**  | **Description**                                              |
|-------------|--------------------------------------------------------------|
| `bg`        | Background color of the window.                              |
| `bd`        | Border size of the window.                                   |
| `cursor`    | Cursor type when the mouse is in the window.                 |
| `class_`    | Export selected text to the window manager.                  |
| `font`      | Font type of the text inserted into the widget.              |
| `fg`        | Foreground color of the widget.                              |
| `height`    | Height of the window.                                        |
| `relief`    | Type of the window.                                          |
| `width`     | Width of the window.                                         |

## Methods
Here are some useful methods associated with the Toplevel widget:

| **Method**     | **Description**                                             |
|----------------|-------------------------------------------------------------|
| `deiconify()` | Display the window.                                         |
| `frame()`     | Show a system-dependent window identifier.                  |
| `group(window)` | Add this window to the specified window group.             |
| `iconify()`   | Convert the toplevel window into an icon.                   |
| `protocol(name, function)` | Specify a function called for a specific protocol.     |
| `state()`     | Get the current state of the window.                        |
| `transient([master])` | Convert this window to a transient window.               |
| `withdraw()`  | Delete the window without destroying it.                     |
| `maxsize(width, height)` | Declare the maximum size for the window.               |
| `minsize(width, height)` | Declare the minimum size for the window.               |
| `positionfrom(who)` | Define the position controller.                         |
| `resizable(width, height)` | Control whether the window can be resized.          |
| `sizefrom(who)` | Define the size controller.                               |
| `title(string)` | Define the title for the window.                            |

## Example
```python
from tkinter import *

root = Tk()
root.geometry("200x200")

def open():
    top = Toplevel(root)
    top.mainloop()

btn = Button(root, text="Open", command=open)
btn.place(x=75, y=50)

root.mainloop()
```

This code creates a Tkinter application with a button. When the button is clicked, it opens a new top-level window using the Toplevel widget.


