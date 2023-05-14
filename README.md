# AirBnB Project: The Console.

This project Creates a console that s

"Structure of the project"

`Storage engine -> Json file.`
`Console -> cmd with python library cmd.Cmd`

# Description of the project

This is the first part of the project that simulates an airbnb application in which we are creating a clone that creates users based on information provided to the console

# Prerequisites 

Python3.10 or later. To install on linux:
```
sudo apt-get install python3
```

# Installation

Clone the repository

```
git clone https://github.com/shadrackodielo/AirBnB_clone.git; cd AirBnB_clone
```

# Run

Use:

```
python3 console.py
```
or
```
./console.py
```

# Testing 

check if the tests work:

```
python3 -m unittest discover tests
```

# Use

## Available commands
|Command| Explanation |
|--|--|
| create | Creates a new instance of `BaseModel`, saves it (to the JSON file) and prints the `id`. Ex: `$ create BaseModel`  |
| show | Prints the string representation of an instance based on the class name and `id`. Ex: `$ show BaseModel 1234-1234-1234` |
| all | Prints all string representation of all instances based or not on the class name. Ex: `$ all BaseModel` |
| update | Updates an instance based on the class name and `id` by adding or updating attribute (save the change into the JSON file). Ex: `$ update BaseModel 1234-1234-1234 email "aibnb@holbertonschool.com"` |

## Normal command input

|Command| Example|
|--|--|
|create| create [class name] |
|show| show [class name] [id] |
|all| create [class name] [id]|
|update| create [class name] [id] [arg_name] [arg_value]|


## Alternative command input
|Command| Example|
|--|--|
|[class name].all()| User.all() |
|[class name].count()| User.count() |
|[class name].show()| User.show() |
|[class name].destroy()| User.destroy() |
|[class name].update([id], [attribute name], [attribute value].all()| User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", "first_name", "John") |
|(class name).update([id], [dictionary representation])| User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", {'first_name': "John", "age": 89}) |

## Available classes
|Class name| Attributes|
|--|--|
| BaseModel | `id`, `created_at`, `updated_at`  |
| User| `email`, `password`, `first_name`, `last_name` |
| State| `name` `state_id`|
| City| `name`  |
| Amenity | `name` |
| Place | `city_id` `user_id` `name` `description` `number_rooms` `number_bathrooms` `max_guest` `price_by_night` `latitude``longitude` `amenity_ids` |
| Review| `place_id` `user_id` `text` |

* every model inherits attributes from BaseModel

## How to start it

### Interactive Mode
```
$ ./console.py
```

Now you are on interactive mode and you will see the prompt `(hbnb)`
input a command:

```
(hbnb) create User
```
the id of the created model will be visible in the standard output, if you do:

```
(hbnb) show User [id]
```

All the attributes of the created model will be in your screen.

use: 

```
(hbnb) help
```
For a list of usable commands, to exit press Ctrl+D or type the command quit.

### Non-Interactive Mode

The console can also be used in non-interactive mode:

```
$ echo "create User" | ./console.py

$ echo "help" | ./console.py
```

The program will create a file called: `file.json` whenever you create a new model, it'll be store in the top folder.
