#CODSOFT

CALCULATOR:
Certainly! The provided Python program is a simple calculator with a graphical user interface (GUI) using the Tkinter library. Let's go through the details of each part of the code:

Importing Tkinter:
python
Copy code
import tkinter as tk
This line imports the Tkinter module, which is a standard GUI toolkit for Python.

Function Definitions:
python
Copy code
def button_click(value):
    current = entry.get()
    entry.delete(0, tk.END)
    entry.insert(tk.END, str(current) + str(value))
This function is called when a digit or operator button is clicked. It retrieves the current content of the entry widget, clears it, and then inserts the clicked value at the end.

python
Copy code
def clear_display():
    entry.delete(0, tk.END)
This function is called when the 'C' button is clicked. It clears the content of the entry widget.

python
Copy code
def calculate():
    try:
        result = eval(entry.get())
        entry.delete(0, tk.END)
        entry.insert(tk.END, result)
    except:
        entry.delete(0, tk.END)
        entry.insert(tk.END, "Error")
This function is called when the '=' button is clicked. It uses the eval() function to evaluate the mathematical expression entered by the user. If the evaluation is successful, the result is displayed; otherwise, an "Error" message is shown.

Main Window Initialization:
python
Copy code
root = tk.Tk()
root.title("Simple Calculator")
These lines create the main window and set its title.

Entry Widget:
python
Copy code
entry = tk.Entry(root, width=35, borderwidth=5)
entry.grid(row=0, column=0, columnspan=4, padx=10, pady=10)
This code creates an entry widget to display the input and output. It is positioned at row 0, column 0, spanning 4 columns, and with some padding.

Buttons:
python
Copy code
buttons = [
    ('7', '8', '9', '/'),
    ('4', '5', '6', '*'),
    ('1', '2', '3', '-'),
    ('0', 'C', '=', '+')
]
This is a 2D list defining the layout of buttons. The nested loop creates Tkinter Button widgets for each digit, operator, and special button.

Button Loop:
python
Copy code
for i, row in enumerate(buttons):
    for j, symbol in enumerate(row):
        # Button creation code
        button.grid(row=i + 1, column=j, padx=5, pady=5)
This loop iterates through the button layout list and creates buttons with appropriate labels and commands. The buttons are placed in a grid layout within the main window.

Running the Application:
python
Copy code
root.mainloop()
This line starts the Tkinter event loop, allowing the GUI to respond to user interactions.

When you run this program, a GUI window will appear with a simple calculator interface. Users can click the buttons to input digits and perform basic arithmetic operations. The calculator includes buttons for clearing the display, calculating the result, and handling errors.










CONTACT:

Certainly! The provided Python script creates a simple contact book application with a graphical user interface (GUI) using the Tkinter library. Let's go through the details of each part of the code:

Main Window Initialization:
python
Copy code
root = tk.Tk()
root.title("Contact Book")
root.geometry("300x300")
root.configure(bg="lightgrey")
These lines create the main window for the contact book application using Tkinter. The window has a title "Contact Book," a size of 300x300 pixels, and a light grey background.

Variable Initialization:
python
Copy code
name_var = tk.StringVar()
number_var = tk.StringVar()
These variables (name_var and number_var) are Tkinter StringVar objects used to store the values entered into the name and number entry widgets.

Entry Widgets for Name and Number:
python
Copy code
name_entry = tk.Entry(root, textvariable=name_var)
name_entry.pack()

number_entry = tk.Entry(root, textvariable=number_var)
number_entry.pack()
These lines create entry widgets for entering the contact's name and number. The textvariable parameter is set to the corresponding StringVar objects to link the entry widgets with the variables.

Button Functions:
python
Copy code
def add_contact():
    # Function to add a contact to the listbox
    # ...

def delete_contact():
    # Function to delete the selected contact from the listbox
    # ...

def edit_contact():
    # Function to edit the selected contact in a new window
    # ...
These functions (add_contact, delete_contact, edit_contact) define the actions to be performed when the "Add Contact," "Delete Contact," and "Edit Contact" buttons are clicked, respectively.

Add Contact Button:
python
Copy code
add_button = tk.Button(root, text="Add Contact", command=add_contact, bg="blue", fg="white")
add_button.pack()
This code creates a button labeled "Add Contact" with a blue background and white text. The command parameter specifies the function (add_contact) to be executed when the button is clicked.

Delete Contact Button:
python
Copy code
delete_button = tk.Button(root, text="Delete Contact", command=delete_contact, bg="red", fg="white")
delete_button.pack()
Similar to the "Add Contact" button, this code creates a button for deleting a contact with a red background and white text.

Edit Contact Button:
python
Copy code
edit_button = tk.Button(root, text="Edit Contact", command=edit_contact, bg="orange", fg="white")
edit_button.pack()
This code creates a button for editing a contact with an orange background and white text. Clicking this button opens a new window for editing the selected contact.

Listbox for Displaying Contacts:
python
Copy code
contact_list = tk.Listbox(root)
contact_list.pack()
This line creates a Tkinter Listbox widget to display the list of contacts.

Contact Editing Window:
python
Copy code
edit_window = tk.Toplevel(root)
edit_window.title("Edit Contact")
edit_window.geometry("250x120")
edit_window.configure(bg="lightgrey")
When the "Edit Contact" button is clicked, this code creates a new top-level window (edit_window) for editing the selected contact. The window has a title, size, and a light grey background.

Editing Window Entry Widgets:
python
Copy code
edit_name_entry = tk.Entry(edit_window, textvariable=edit_name_var)
edit_number_entry = tk.Entry(edit_window, textvariable=edit_number_var)
These lines create entry widgets in the editing window for entering the updated name and number of the contact.

Editing Window Save Button:
python
Copy code
save_button = tk.Button(edit_window, text="Save", command=save_edit, bg="green", fg="white")
save_button.pack()
This code creates a button in the editing window labeled "Save" with a green background and white text. Clicking this button saves the changes made to the contact and closes the editing window.

Running the Application:
python
Copy code
root.mainloop()
Finally, this line starts the Tkinter event loop, allowing the GUI to respond to user interactions. When you run this script, a contact book window will appear, allowing users to add, delete, and edit contacts with a simple user interface. The contact list is displayed in a listbox.





