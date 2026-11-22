# Todotui
Todotui is a CLI todo list that allows the user to view, add, remove and mark items as completed. Despite its name, the current version does not support
a terminal user interface (TUI). The next step in this project is to add a TUI that allows the user to manage a todo list via both text editing and 
keyboard commands (e.g. Ctrl+M to mark item as completed).

## Installation
Simply download the `todotui` file.

## Usage
Run `./todotui -<option> [argument]` according to the following table:
| option | argument | description |
|--------|---------|-------------|
| v      | none    | outputs the todo list.| 
| a      | string  | adds the specified argument string as an  item to the todo list.| 
| r      | id      | removes the item with the specified id from the todo list.| 
| m      | id      | marks the item with the specified id as completed/uncompleted.| 
| c      | none    | clears the todo list.|

## How It Works
The program mantains two text files: `todolist.txt` and `status.txt`. The former contains the numbered items added by the user, the latter contains 
the status of each item in the format `<id>: <status>` where `<status>` is either `0` (unmarked) or `1` (marked).

When the user adds an item, the program generates a progressive id, appends the item to `todolist.txt` and appends the id to `status.txt` with status
`0`. When the user marks an item, the program filps the corresponding id's status in `status.txt`. When the user removes an item, the program eliminates
the corresponding row from both `todolist.txt` and `status.txt` and updates the other items' ids accordingly. When the user lists the items, the program
outputs `todolist.txt` with the crossed text formatting for the marked items i.e. the items with status `1` in `status.txt`.
