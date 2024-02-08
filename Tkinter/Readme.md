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

