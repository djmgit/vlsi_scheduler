## VLSI scheduler

**Currently this script only supports resource constrained scheduling**

### Dependencies
- Python
- lp-solve

### Installing lp-solve
On ubuntu, lp-solve can be installed as follows - 

``` sudo apt-get install lp-solve ```

### Quickstart
A sample operation control graph has been provided in the repository.
To see the script in action, please follow the following steps
- Clone this repo
- Open the cloned repo in terminal
- Run ``` python scheduler.py ```
- You will be provided with a schedule on terminal, also output files for both the linear programming model
  and the output will be created in the same directory
  
### How it works?
The script requires the operation control graph as an input. This graph can be provided as a json input. That is
a json file containing the definition of the graph along with some other parameters has to be present in 
the same directory has the source code. Currently a sample graph called **ocg.json** is already present in the repo.
This file can be editted to provide a different graph input to solve and schedule.

### How to create the json graph
Given below is a sample graph in json:

```
{
	"total_ops": 8,
	"csteps_estimate": 6,
	"graph": {
		"0": [1, 2, 3],
		"1": [4],
		"2": [5, 6],
		"3": [7],
		"4": [5],
		"5": [6],
		"6": [7]
	},
	"op_types_number": "4",
	"op_types": {
		"0": [0, 7],
		"1": [1, 2, 6],
		"2": [4, 5],
		"3": [3]
	},
	"op_instances": {
		"0": 1,
		"1": 1,
		"2": 1,
		"3": 1
	},
	"var_type": "bin"
}

```

The above json file corresponds to the following graph
