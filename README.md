scheduler
===

A PERT scheduler.

## Usage

```
usage: scheduler [-h] [--start START_TIME] csv_file

Perform PERT scheduling.

Reads in a schedule as a CSV file formatted as:
	idx, task title, task lead, duration (days), [dep 1, ...]
Where dependencies are identified by the idx of another task.

positional arguments:
  csv_file            CSV file containing a list of tasks

optional arguments:
  -h, --help          show this help message and exit
  --start START_TIME  Start time in mm/dd/yy format
```
