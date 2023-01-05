# NEORV32 Xilinx Vivado Example testbench setup
## Prerequisites:

- Vivado 2021.2 installed
- digilent Arty-A7 "axc7a35ticsg324-1L" downloaded if there is a need to implement NEORV32 on FPGA
- Python 3.6.9 

## How To Run

Use only main script `neorv32_verifire.py`

### Arguments :
`--help` 			 | `-h`         : Help message <br />
`--vivado_path`      | `-vp`		: Path to Vivado dir <br />
`--generate_project` | `-gp` 		: Option to generate new Vivado project <br />
`--project_path` 	 | `-pp` [PATH] : Path to existing Noerv32 Vivado project (please, for now provide path to project generated by this script)<br />
`--simulate` 		 | `-s`  [PATH]	: Simulate scenario given by PATH <br />
`--simulate_all` 	 | `-sa` 		: Simulate all scenarios present in testbench folder <br />
`--verbosity` 		 | `-v` {0,1,2} : Verbosity mode, NOT SUPPORTED YET <br />

### Required Arguments :
The `--vivado_path` argument is required.
User must use either `--generate_project`  or `--project_path` and `--simulate`  or `--simulate_all` arguments.

### Examples :
Generate project and simulate all scenarios :
`python3 neorv32_verifire.py --vivado_path /home/ohnut/Vivado/2020.2/ --generate_project --simulate_all`

Use existing project and simulate chosen scenario :
`python3 neorv32_verifire.py --vivado_path /home/ohnut/Vivado/2020.2/ --project_path ./vivado --simulate testbench/test_files/blink/led`


### Known issues :
Writing to simulation output file doesnt work on Windows OS.
All simulations are running for 1000ms for now.

