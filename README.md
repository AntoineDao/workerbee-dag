# workerbee
🍯 workerbee is the library to run, store and load honeybee jobs! In the future it should run, store and load the jobs for all insects in Ladybug Tools!


## Why?
We have been fighting an uphill battle to get honeybee to perform faster from inside
Grasshopper and Dynamo for running the commands and loading the results. It has been
proven to be very hard to achieve with all the limitations that IronPython has for using
3rd-party libraries that can be very helpful for our work.

By breaking down the writer and the worker (this repository) we can put an end to the
unnecessary complication and call the tasks as a subprocess from IronPython which can run
in CPython or any other language as needed!

Workerbee will be written to work with Python 2 and Python 3 and will take advantage of
available CPython libraries.


## How does it work?

```Python
from workerbee.worker import Worker

wb = Worker('PATH_TO_FOLDER_GENERATED_BY_HONEYBEE')

pid = wb.run(cpu_count=5, wait=True)

while wb.is_running:
    print(wb.progress)
```
