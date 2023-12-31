# Monkeywork

## Description

Are you in need of a Monkey typing on their keyboard and saving files into a random directory? Look no further…

This program was designed to stress test a file synchronization solution by simulating a user who reads, writes, and edits files within a specific directory.
You can specify a working directory where the program will conduct the following operations at a set interval:
-	Create text and binary files with random content.
-	Create random subdirectories.
-	Open and edit files.
-	Rename files and directories.
-	Delete random files.
-	Delete random subdirectories.
All operations are being written into a log file.

The idea behind this program is to run it on both ends of a file sharing or syncing solution. By doing so, you can test whether your solution is capable of handling regular and potentially conflicting user activities.

## !!! CAUTION !!!

The program can and will destroy files in the selected work directory. Be sure to select a dedicated work directory and **review the code before executing it on your system**!

## Run in console

You can run the `monkeywork.py` directly from from the console with:

```bash
python monkeywork.py "<Path to your workdir>" [OPTIONS]
```

example:
```bash
python monkeywork.py "L:\monkeywork-test\"
```

Options are:

-f | force selected direcotry and delete all contents in set directory
-y | skip start confirmation

## Installation

Use it as a package

```bash
pip install monkeywork
```

## Usage

Example with custom interval setting:
```python
from monkeywork import Monkey

mky = Monkey(workdir="F:/mky-test", interval_min_s=.1, interval_max_s=1)
mky.run()
```

orther avaiable setting:
|variable | Description |
|---|---|
|workdir:str| must be set to a valid path |
|interval_min_s:float | shortest interval |
|interval_max_s:float | longest interval |
|max_file_size_mb:int | maximum file size in MB |
|max_file_amount:int | maximumg file count
|target_file_amount:int | program targets this amount of files |
|path_length_limit:int | program should not exceed set path length |
|logging_to_file_enabled:bool | enable logging to file |
