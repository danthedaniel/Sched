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

## Example

Using a file called `sched.csv` with the following contents:

```
5,Task A,teaearlgraycold,3
7,Task B,teaearlgraycold,4
3,Task C,teaearlgraycold,14
11,Task D,teaearlgraycold,1,5,7
8,Task E,teaearlgraycold,5,7,3
2,Task F,teaearlgraycold,6,11
9,Task G,teaearlgraycold,9,11,8
10,Task H,teaearlgraycold,9,11,3
```

You will receive the following output:

```
./scheduler --start 11/7/17 sched.csv
11/07/17 -> 11/21/17: Task C (teaearlgraycold)
11/07/17 -> 11/10/17: Task A (teaearlgraycold)
11/07/17 -> 11/11/17: Task B (teaearlgraycold)
11/11/17 -> 11/16/17: Task E (teaearlgraycold)
11/11/17 -> 11/12/17: Task D (teaearlgraycold)
11/12/17 -> 11/21/17: Task G (teaearlgraycold)
11/12/17 -> 11/21/17: Task H (teaearlgraycold)
11/12/17 -> 11/18/17: Task F (teaearlgraycold)
```
