# **Maersk-Case-Study: Simulating a Container Terminal**

## **Introduction**
**This project simulates a container terminal using SimPy.** It models the arrival of vessels, the unloading of containers using quay cranes, and the transportation of containers to the yard using trucks.

## **Task Description**
The simulation aims to model the following operations at a container terminal:

### **Vessel Arrivals:**
- Vessels arrive at the terminal following an exponential distribution with an average interval of 5 hours.
- Each vessel carries 150 containers to be discharged.

### **Berthing:**
- The terminal has **2 berths** (berth_1 and berth_2).
- If both berths are occupied, arriving vessels must wait until a berth is available.

### **Container Discharge:**
- There are **2 quay cranes** available, and each vessel uses only one crane for unloading.
- It takes **3 minutes** for a crane to move one container.
- Cranes must load containers onto trucks, and they must wait if no trucks are available.

### **Container Transport:**
- The terminal has **3 trucks** for transporting containers from the quay cranes to the yard.
- It takes a truck **6 minutes** to drop off a container and return.

### **Simulation Log:**
- Events such as vessel arrivals, berthing, crane operations, and truck operations are logged with timestamps.

## **Requirements**
- **Python 3.x**
- **SimPy**


## **Simulation Parameters**

The simulation parameters can be customized by the user or set to default values. The parameters include:

- **Number of berths**
- **Number of quay cranes**
- **Number of trucks**
- **Total simulation time (in minutes)**

## **Code Overview**
Classes and Functions
- **Class: ContainerTerminal**
Initializes resources for berths, cranes, and trucks.
Handles container discharge, including crane and truck operations.
- **Function: handle_vessel**
Manages the arrival, berthing, and container discharge of a vessel.

- **Function: generate_vessel_arrivals**
Generates vessel arrivals at the terminal based on an exponential distribution.

- **Function: get_simulation_parameters**
Prompts the user to input simulation parameters or use default values.

- **Function: main**
Main function to set up and run the simulation.

Usage
Run the simulation by executing the following command:


```sh
python maersk_case_study.py
```


You will be prompted to select default values or enter user-defined values for the simulation parameters. The simulation will then run, and logs of events will be printed to the console.

```bash
##Example Output:##

Select the choices:
1. Use default values
2. Enter user-defined values
Enter your choice (1 or 2): 1
You have chosen to use default values.
Simulation parameters:
Number of berths: 2
Number of cranes: 2
Number of trucks: 3
Total simulation time: 1000 minutes
Time 306.018: Vessel 1 Arrived
Time 306.018: Vessel 1 berthed
Time 306.018: Vessel 1 - Crane allocated
Time 306.018: Vessel 1 - Crane moved container 1
Time 309.018: Vessel 1 - Container 1 loaded onto truck
Time 313.617: Vessel 2 Arrived
Time 313.617: Vessel 2 berthed
Time 313.617: Vessel 2 - Crane allocated
Time 313.617: Vessel 2 - Crane moved container 1
Time 315.018: Vessel 1 - Truck transported container 1 to yard
Time 315.018: Vessel 1 - Crane moved container 2
Time 316.617: Vessel 2 - Container 1 loaded onto truck
Time 318.018: Vessel 1 - Container 2 loaded onto truck
Time 322.617: Vessel 2 - Truck transported container 1 to yard
Time 322.617: Vessel 2 - Crane moved container 2
Time 324.018: Vessel 1 - Truck transported container 2 to yard
Time 324.018: Vessel 1 - Crane moved container 3
Time 325.617: Vessel 2 - Container 2 loaded onto truck
Time 327.018: Vessel 1 - Container 3 loaded onto truck
Time 331.617: Vessel 2 - Truck transported container 2 to yard
Time 331.617: Vessel 2 - Crane moved container 3
Time 333.018: Vessel 1 - Truck transported container 3 to yard
Time 333.018: Vessel 1 - Crane moved container 4
Time 334.617: Vessel 2 - Container 3 loaded onto truck
Time 336.018: Vessel 1 - Container 4 loaded onto truck
Time 340.617: Vessel 2 - Truck transported container 3 to yard
Time 340.617: Vessel 2 - Crane moved container 4
Time 342.018: Vessel 1 - Truck transported container 4 to yard
Time 342.018: Vessel 1 - Crane moved container 5
Time 343.617: Vessel 2 - Container 4 loaded onto truck
Time 345.018: Vessel 1 - Container 5 loaded onto truck
Time 349.617: Vessel 2 - Truck transported container 4 to yard
Time 349.617: Vessel 2 - Crane moved container 5
Time 351.018: Vessel 1 - Truck transported container 5 to yard
Time 351.018: Vessel 1 - Crane moved container 6
Time 352.617: Vessel 2 - Container 5 loaded onto truck
Time 354.018: Vessel 1 - Container 6 loaded onto truck
Time 358.617: Vessel 2 - Truck transported container 5 to yard
Time 358.617: Vessel 2 - Crane moved container 6
Time 360.018: Vessel 1 - Truck transported container 6 to yard
Time 360.018: Vessel 1 - Crane moved container 7
Time 361.617: Vessel 2 - Container 6 loaded onto truck
Time 363.018: Vessel 1 - Container 7 loaded onto truck
Time 367.617: Vessel 2 - Truck transported container 6 to yard
Time 367.617: Vessel 2 - Crane moved container 7
Time 369.018: Vessel 1 - Truck transported container 7 to yard
Time 369.018: Vessel 1 - Crane moved container 8
Time 370.617: Vessel 2 - Container 7 loaded onto truck
Time 372.018: Vessel 1 - Container 8 loaded onto truck
Time 376.617: Vessel 2 - Truck transported container 7 to yard
Time 376.617: Vessel 2 - Crane moved container 8
Time 378.018: Vessel 1 - Truck transported container 8 to yard
Time 378.018: Vessel 1 - Crane moved container 9
Time 379.617: Vessel 2 - Container 8 loaded onto truck
Time 381.018: Vessel 1 - Container 9 loaded onto truck
Time 385.617: Vessel 2 - Truck transported container 8 to yard
Time 385.617: Vessel 2 - Crane moved container 9
Time 387.018: Vessel 1 - Truck transported container 9 to yard
Time 387.018: Vessel 1 - Crane moved container 10
Time 388.617: Vessel 2 - Container 9 loaded onto truck
Time 390.018: Vessel 1 - Container 10 loaded onto truck
Time 394.617: Vessel 2 - Truck transported container 9 to yard
Time 394.617: Vessel 2 - Crane moved container 10
Time 396.018: Vessel 1 - Truck transported container 10 to yard
Time 396.018: Vessel 1 - Crane moved container 11
Time 397.617: Vessel 2 - Container 10 loaded onto truck
Time 399.018: Vessel 1 - Container 11 loaded onto truck
Time 403.617: Vessel 2 - Truck transported container 10 to yard
Time 403.617: Vessel 2 - Crane moved container 11
Time 405.018: Vessel 1 - Truck transported container 11 to yard
Time 405.018: Vessel 1 - Crane moved container 12
Time 406.617: Vessel 2 - Container 11 loaded onto truck
Time 408.018: Vessel 1 - Container 12 loaded onto truck
Time 410.104: Vessel 3 Arrived
Time 410.104: Vessel 3 Waiting for a berth
Time 412.617: Vessel 2 - Truck transported container 11 to yard
Time 412.617: Vessel 2 - Crane moved container 12
Time 414.018: Vessel 1 - Truck transported container 12 to yard
Time 414.018: Vessel 1 - Crane moved container 13
Time 415.617: Vessel 2 - Container 12 loaded onto truck
Time 417.018: Vessel 1 - Container 13 loaded onto truck
Time 421.617: Vessel 2 - Truck transported container 12 to yard
Time 421.617: Vessel 2 - Crane moved container 13
Time 423.018: Vessel 1 - Truck transported container 13 to yard
Time 423.018: Vessel 1 - Crane moved container 14
Time 424.617: Vessel 2 - Container 13 loaded onto truck
Time 426.018: Vessel 1 - Container 14 loaded onto truck
Time 430.617: Vessel 2 - Truck transported container 13 to yard
Time 430.617: Vessel 2 - Crane moved container 14
Time 432.018: Vessel 1 - Truck transported container 14 to yard
Time 432.018: Vessel 1 - Crane moved container 15
Time 433.617: Vessel 2 - Container 14 loaded onto truck
Time 435.018: Vessel 1 - Container 15 loaded onto truck
Time 439.617: Vessel 2 - Truck transported container 14 to yard
Time 439.617: Vessel 2 - Crane moved container 15
Time 441.018: Vessel 1 - Truck transported container 15 to yard
Time 441.018: Vessel 1 - Crane moved container 16
Time 442.617: Vessel 2 - Container 15 loaded onto truck
Time 444.018: Vessel 1 - Container 16 loaded onto truck
Time 448.617: Vessel 2 - Truck transported container 15 to yard
Time 448.617: Vessel 2 - Crane moved container 16
Time 450.018: Vessel 1 - Truck transported container 16 to yard
Time 450.018: Vessel 1 - Crane moved container 17
Time 451.617: Vessel 2 - Container 16 loaded onto truck
Time 453.018: Vessel 1 - Container 17 loaded onto truck
Time 457.617: Vessel 2 - Truck transported container 16 to yard
Time 457.617: Vessel 2 - Crane moved container 17
Time 459.018: Vessel 1 - Truck transported container 17 to yard
Time 459.018: Vessel 1 - Crane moved container 18
Time 460.617: Vessel 2 - Container 17 loaded onto truck
Time 462.018: Vessel 1 - Container 18 loaded onto truck
Time 466.617: Vessel 2 - Truck transported container 17 to yard
Time 466.617: Vessel 2 - Crane moved container 18
Time 468.018: Vessel 1 - Truck transported container 18 to yard
Time 468.018: Vessel 1 - Crane moved container 19
Time 469.617: Vessel 2 - Container 18 loaded onto truck
Time 471.018: Vessel 1 - Container 19 loaded onto truck
Time 475.617: Vessel 2 - Truck transported container 18 to yard
Time 475.617: Vessel 2 - Crane moved container 19
Time 477.018: Vessel 1 - Truck transported container 19 to yard
Time 477.018: Vessel 1 - Crane moved container 20
Time 478.617: Vessel 2 - Container 19 loaded onto truck
Time 480.018: Vessel 1 - Container 20 loaded onto truck
Time 484.617: Vessel 2 - Truck transported container 19 to yard
Time 484.617: Vessel 2 - Crane moved container 20
Time 485.880: Vessel 4 Arrived
Time 485.880: Vessel 4 Waiting for a berth
Time 486.018: Vessel 1 - Truck transported container 20 to yard
Time 486.018: Vessel 1 - Crane moved container 21
Time 487.617: Vessel 2 - Container 20 loaded onto truck
Time 489.018: Vessel 1 - Container 21 loaded onto truck
Time 493.617: Vessel 2 - Truck transported container 20 to yard
Time 493.617: Vessel 2 - Crane moved container 21
Time 495.018: Vessel 1 - Truck transported container 21 to yard
Time 495.018: Vessel 1 - Crane moved container 22
Time 496.617: Vessel 2 - Container 21 loaded onto truck
Time 498.018: Vessel 1 - Container 22 loaded onto truck
Time 502.617: Vessel 2 - Truck transported container 21 to yard
Time 502.617: Vessel 2 - Crane moved container 22
Time 504.018: Vessel 1 - Truck transported container 22 to yard
Time 504.018: Vessel 1 - Crane moved container 23
Time 505.617: Vessel 2 - Container 22 loaded onto truck
Time 507.018: Vessel 1 - Container 23 loaded onto truck
Time 511.617: Vessel 2 - Truck transported container 22 to yard
Time 511.617: Vessel 2 - Crane moved container 23
Time 513.018: Vessel 1 - Truck transported container 23 to yard
Time 513.018: Vessel 1 - Crane moved container 24
Time 514.617: Vessel 2 - Container 23 loaded onto truck
Time 516.018: Vessel 1 - Container 24 loaded onto truck
Time 520.617: Vessel 2 - Truck transported container 23 to yard
Time 520.617: Vessel 2 - Crane moved container 24
Time 522.018: Vessel 1 - Truck transported container 24 to yard
Time 522.018: Vessel 1 - Crane moved container 25
Time 523.617: Vessel 2 - Container 24 loaded onto truck
Time 525.018: Vessel 1 - Container 25 loaded onto truck
Time 529.617: Vessel 2 - Truck transported container 24 to yard
Time 529.617: Vessel 2 - Crane moved container 25
Time 531.018: Vessel 1 - Truck transported container 25 to yard
Time 531.018: Vessel 1 - Crane moved container 26
Time 532.617: Vessel 2 - Container 25 loaded onto truck
Time 534.018: Vessel 1 - Container 26 loaded onto truck
Time 538.617: Vessel 2 - Truck transported container 25 to yard
Time 538.617: Vessel 2 - Crane moved container 26
Time 540.018: Vessel 1 - Truck transported container 26 to yard
Time 540.018: Vessel 1 - Crane moved container 27
Time 541.617: Vessel 2 - Container 26 loaded onto truck
Time 543.018: Vessel 1 - Container 27 loaded onto truck
Time 547.617: Vessel 2 - Truck transported container 26 to yard
Time 547.617: Vessel 2 - Crane moved container 27
Time 549.018: Vessel 1 - Truck transported container 27 to yard
Time 549.018: Vessel 1 - Crane moved container 28
Time 550.617: Vessel 2 - Container 27 loaded onto truck
Time 552.018: Vessel 1 - Container 28 loaded onto truck
Time 556.617: Vessel 2 - Truck transported container 27 to yard
Time 556.617: Vessel 2 - Crane moved container 28
Time 558.018: Vessel 1 - Truck transported container 28 to yard
Time 558.018: Vessel 1 - Crane moved container 29
Time 559.617: Vessel 2 - Container 28 loaded onto truck
Time 561.018: Vessel 1 - Container 29 loaded onto truck
Time 565.617: Vessel 2 - Truck transported container 28 to yard
Time 565.617: Vessel 2 - Crane moved container 29
Time 567.018: Vessel 1 - Truck transported container 29 to yard
Time 567.018: Vessel 1 - Crane moved container 30
Time 568.617: Vessel 2 - Container 29 loaded onto truck
Time 570.018: Vessel 1 - Container 30 loaded onto truck
Time 574.617: Vessel 2 - Truck transported container 29 to yard
Time 574.617: Vessel 2 - Crane moved container 30
Time 576.018: Vessel 1 - Truck transported container 30 to yard
Time 576.018: Vessel 1 - Crane moved container 31
Time 577.617: Vessel 2 - Container 30 loaded onto truck
Time 579.018: Vessel 1 - Container 31 loaded onto truck
Time 583.617: Vessel 2 - Truck transported container 30 to yard
Time 583.617: Vessel 2 - Crane moved container 31
Time 585.018: Vessel 1 - Truck transported container 31 to yard
Time 585.018: Vessel 1 - Crane moved container 32
Time 586.617: Vessel 2 - Container 31 loaded onto truck
Time 588.018: Vessel 1 - Container 32 loaded onto truck
Time 592.617: Vessel 2 - Truck transported container 31 to yard
Time 592.617: Vessel 2 - Crane moved container 32
Time 594.018: Vessel 1 - Truck transported container 32 to yard
Time 594.018: Vessel 1 - Crane moved container 33
Time 595.617: Vessel 2 - Container 32 loaded onto truck
Time 597.018: Vessel 1 - Container 33 loaded onto truck
Time 601.617: Vessel 2 - Truck transported container 32 to yard
Time 601.617: Vessel 2 - Crane moved container 33
Time 603.018: Vessel 1 - Truck transported container 33 to yard
Time 603.018: Vessel 1 - Crane moved container 34
Time 604.617: Vessel 2 - Container 33 loaded onto truck
Time 606.018: Vessel 1 - Container 34 loaded onto truck
Time 610.617: Vessel 2 - Truck transported container 33 to yard
Time 610.617: Vessel 2 - Crane moved container 34
Time 612.018: Vessel 1 - Truck transported container 34 to yard
Time 612.018: Vessel 1 - Crane moved container 35
Time 613.617: Vessel 2 - Container 34 loaded onto truck
Time 615.018: Vessel 1 - Container 35 loaded onto truck
Time 619.617: Vessel 2 - Truck transported container 34 to yard
Time 619.617: Vessel 2 - Crane moved container 35
Time 621.018: Vessel 1 - Truck transported container 35 to yard
Time 621.018: Vessel 1 - Crane moved container 36
Time 622.617: Vessel 2 - Container 35 loaded onto truck
Time 624.018: Vessel 1 - Container 36 loaded onto truck
Time 628.617: Vessel 2 - Truck transported container 35 to yard
Time 628.617: Vessel 2 - Crane moved container 36
Time 630.018: Vessel 1 - Truck transported container 36 to yard
Time 630.018: Vessel 1 - Crane moved container 37
Time 631.617: Vessel 2 - Container 36 loaded onto truck
Time 633.018: Vessel 1 - Container 37 loaded onto truck
Time 637.617: Vessel 2 - Truck transported container 36 to yard
Time 637.617: Vessel 2 - Crane moved container 37
Time 639.018: Vessel 1 - Truck transported container 37 to yard
Time 639.018: Vessel 1 - Crane moved container 38
Time 640.617: Vessel 2 - Container 37 loaded onto truck
Time 642.018: Vessel 1 - Container 38 loaded onto truck
Time 646.617: Vessel 2 - Truck transported container 37 to yard
Time 646.617: Vessel 2 - Crane moved container 38
Time 648.018: Vessel 1 - Truck transported container 38 to yard
Time 648.018: Vessel 1 - Crane moved container 39
Time 649.617: Vessel 2 - Container 38 loaded onto truck
Time 651.018: Vessel 1 - Container 39 loaded onto truck
Time 655.617: Vessel 2 - Truck transported container 38 to yard
Time 655.617: Vessel 2 - Crane moved container 39
Time 657.018: Vessel 1 - Truck transported container 39 to yard
Time 657.018: Vessel 1 - Crane moved container 40
Time 658.617: Vessel 2 - Container 39 loaded onto truck
Time 660.018: Vessel 1 - Container 40 loaded onto truck
Time 664.617: Vessel 2 - Truck transported container 39 to yard
Time 664.617: Vessel 2 - Crane moved container 40
Time 666.018: Vessel 1 - Truck transported container 40 to yard
Time 666.018: Vessel 1 - Crane moved container 41
Time 667.617: Vessel 2 - Container 40 loaded onto truck
Time 669.018: Vessel 1 - Container 41 loaded onto truck
Time 673.617: Vessel 2 - Truck transported container 40 to yard
Time 673.617: Vessel 2 - Crane moved container 41
Time 675.018: Vessel 1 - Truck transported container 41 to yard
Time 675.018: Vessel 1 - Crane moved container 42
Time 676.617: Vessel 2 - Container 41 loaded onto truck
Time 678.018: Vessel 1 - Container 42 loaded onto truck
Time 682.617: Vessel 2 - Truck transported container 41 to yard
Time 682.617: Vessel 2 - Crane moved container 42
Time 684.018: Vessel 1 - Truck transported container 42 to yard
Time 684.018: Vessel 1 - Crane moved container 43
Time 685.617: Vessel 2 - Container 42 loaded onto truck
Time 687.018: Vessel 1 - Container 43 loaded onto truck
Time 691.617: Vessel 2 - Truck transported container 42 to yard
Time 691.617: Vessel 2 - Crane moved container 43
Time 693.018: Vessel 1 - Truck transported container 43 to yard
Time 693.018: Vessel 1 - Crane moved container 44
Time 694.617: Vessel 2 - Container 43 loaded onto truck
Time 696.018: Vessel 1 - Container 44 loaded onto truck
Time 700.617: Vessel 2 - Truck transported container 43 to yard
Time 700.617: Vessel 2 - Crane moved container 44
Time 702.018: Vessel 1 - Truck transported container 44 to yard
Time 702.018: Vessel 1 - Crane moved container 45
Time 703.617: Vessel 2 - Container 44 loaded onto truck
Time 705.018: Vessel 1 - Container 45 loaded onto truck
Time 709.617: Vessel 2 - Truck transported container 44 to yard
Time 709.617: Vessel 2 - Crane moved container 45
Time 711.018: Vessel 1 - Truck transported container 45 to yard
Time 711.018: Vessel 1 - Crane moved container 46
Time 712.617: Vessel 2 - Container 45 loaded onto truck
Time 714.018: Vessel 1 - Container 46 loaded onto truck
Time 718.617: Vessel 2 - Truck transported container 45 to yard
Time 718.617: Vessel 2 - Crane moved container 46
Time 720.018: Vessel 1 - Truck transported container 46 to yard
Time 720.018: Vessel 1 - Crane moved container 47
Time 721.617: Vessel 2 - Container 46 loaded onto truck
Time 723.018: Vessel 1 - Container 47 loaded onto truck
Time 727.617: Vessel 2 - Truck transported container 46 to yard
Time 727.617: Vessel 2 - Crane moved container 47
Time 729.018: Vessel 1 - Truck transported container 47 to yard
Time 729.018: Vessel 1 - Crane moved container 48
Time 730.617: Vessel 2 - Container 47 loaded onto truck
Time 732.018: Vessel 1 - Container 48 loaded onto truck
Time 736.617: Vessel 2 - Truck transported container 47 to yard
Time 736.617: Vessel 2 - Crane moved container 48
Time 738.018: Vessel 1 - Truck transported container 48 to yard
Time 738.018: Vessel 1 - Crane moved container 49
Time 739.617: Vessel 2 - Container 48 loaded onto truck
Time 741.018: Vessel 1 - Container 49 loaded onto truck
Time 745.617: Vessel 2 - Truck transported container 48 to yard
Time 745.617: Vessel 2 - Crane moved container 49
Time 747.018: Vessel 1 - Truck transported container 49 to yard
Time 747.018: Vessel 1 - Crane moved container 50
Time 748.617: Vessel 2 - Container 49 loaded onto truck
Time 750.018: Vessel 1 - Container 50 loaded onto truck
Time 754.617: Vessel 2 - Truck transported container 49 to yard
Time 754.617: Vessel 2 - Crane moved container 50
Time 756.018: Vessel 1 - Truck transported container 50 to yard
Time 756.018: Vessel 1 - Crane moved container 51
Time 757.617: Vessel 2 - Container 50 loaded onto truck
Time 759.018: Vessel 1 - Container 51 loaded onto truck
Time 763.617: Vessel 2 - Truck transported container 50 to yard
Time 763.617: Vessel 2 - Crane moved container 51
Time 765.018: Vessel 1 - Truck transported container 51 to yard
Time 765.018: Vessel 1 - Crane moved container 52
Time 766.617: Vessel 2 - Container 51 loaded onto truck
Time 768.018: Vessel 1 - Container 52 loaded onto truck
Time 772.617: Vessel 2 - Truck transported container 51 to yard
Time 772.617: Vessel 2 - Crane moved container 52
Time 774.018: Vessel 1 - Truck transported container 52 to yard
Time 774.018: Vessel 1 - Crane moved container 53
Time 775.617: Vessel 2 - Container 52 loaded onto truck
Time 777.018: Vessel 1 - Container 53 loaded onto truck
Time 781.617: Vessel 2 - Truck transported container 52 to yard
Time 781.617: Vessel 2 - Crane moved container 53
Time 783.018: Vessel 1 - Truck transported container 53 to yard
Time 783.018: Vessel 1 - Crane moved container 54
Time 784.617: Vessel 2 - Container 53 loaded onto truck
Time 786.018: Vessel 1 - Container 54 loaded onto truck
Time 790.617: Vessel 2 - Truck transported container 53 to yard
Time 790.617: Vessel 2 - Crane moved container 54
Time 792.018: Vessel 1 - Truck transported container 54 to yard
Time 792.018: Vessel 1 - Crane moved container 55
Time 793.617: Vessel 2 - Container 54 loaded onto truck
Time 795.018: Vessel 1 - Container 55 loaded onto truck
Time 799.617: Vessel 2 - Truck transported container 54 to yard
Time 799.617: Vessel 2 - Crane moved container 55
Time 801.018: Vessel 1 - Truck transported container 55 to yard
Time 801.018: Vessel 1 - Crane moved container 56
Time 802.617: Vessel 2 - Container 55 loaded onto truck
Time 804.018: Vessel 1 - Container 56 loaded onto truck
Time 808.617: Vessel 2 - Truck transported container 55 to yard
Time 808.617: Vessel 2 - Crane moved container 56
Time 810.018: Vessel 1 - Truck transported container 56 to yard
Time 810.018: Vessel 1 - Crane moved container 57
Time 811.617: Vessel 2 - Container 56 loaded onto truck
Time 813.018: Vessel 1 - Container 57 loaded onto truck
Time 817.617: Vessel 2 - Truck transported container 56 to yard
Time 817.617: Vessel 2 - Crane moved container 57
Time 819.018: Vessel 1 - Truck transported container 57 to yard
Time 819.018: Vessel 1 - Crane moved container 58
Time 820.617: Vessel 2 - Container 57 loaded onto truck
Time 822.018: Vessel 1 - Container 58 loaded onto truck
Time 826.617: Vessel 2 - Truck transported container 57 to yard
Time 826.617: Vessel 2 - Crane moved container 58
Time 828.018: Vessel 1 - Truck transported container 58 to yard
Time 828.018: Vessel 1 - Crane moved container 59
Time 829.617: Vessel 2 - Container 58 loaded onto truck
Time 831.018: Vessel 1 - Container 59 loaded onto truck
Time 835.617: Vessel 2 - Truck transported container 58 to yard
Time 835.617: Vessel 2 - Crane moved container 59
Time 837.018: Vessel 1 - Truck transported container 59 to yard
Time 837.018: Vessel 1 - Crane moved container 60
Time 838.617: Vessel 2 - Container 59 loaded onto truck
Time 840.018: Vessel 1 - Container 60 loaded onto truck
Time 844.617: Vessel 2 - Truck transported container 59 to yard
Time 844.617: Vessel 2 - Crane moved container 60
Time 846.018: Vessel 1 - Truck transported container 60 to yard
Time 846.018: Vessel 1 - Crane moved container 61
Time 847.617: Vessel 2 - Container 60 loaded onto truck
Time 849.018: Vessel 1 - Container 61 loaded onto truck
Time 853.617: Vessel 2 - Truck transported container 60 to yard
Time 853.617: Vessel 2 - Crane moved container 61
Time 855.018: Vessel 1 - Truck transported container 61 to yard
Time 855.018: Vessel 1 - Crane moved container 62
Time 856.617: Vessel 2 - Container 61 loaded onto truck
Time 858.018: Vessel 1 - Container 62 loaded onto truck
Time 862.617: Vessel 2 - Truck transported container 61 to yard
Time 862.617: Vessel 2 - Crane moved container 62
Time 864.018: Vessel 1 - Truck transported container 62 to yard
Time 864.018: Vessel 1 - Crane moved container 63
Time 865.617: Vessel 2 - Container 62 loaded onto truck
Time 867.018: Vessel 1 - Container 63 loaded onto truck
Time 871.617: Vessel 2 - Truck transported container 62 to yard
Time 871.617: Vessel 2 - Crane moved container 63
Time 873.018: Vessel 1 - Truck transported container 63 to yard
Time 873.018: Vessel 1 - Crane moved container 64
Time 874.617: Vessel 2 - Container 63 loaded onto truck
Time 876.018: Vessel 1 - Container 64 loaded onto truck
Time 880.617: Vessel 2 - Truck transported container 63 to yard
Time 880.617: Vessel 2 - Crane moved container 64
Time 882.018: Vessel 1 - Truck transported container 64 to yard
Time 882.018: Vessel 1 - Crane moved container 65
Time 883.617: Vessel 2 - Container 64 loaded onto truck
Time 885.018: Vessel 1 - Container 65 loaded onto truck
Time 885.958: Vessel 5 Arrived
Time 885.958: Vessel 5 Waiting for a berth
Time 889.617: Vessel 2 - Truck transported container 64 to yard
Time 889.617: Vessel 2 - Crane moved container 65
Time 891.018: Vessel 1 - Truck transported container 65 to yard
Time 891.018: Vessel 1 - Crane moved container 66
Time 892.617: Vessel 2 - Container 65 loaded onto truck
Time 894.018: Vessel 1 - Container 66 loaded onto truck
Time 898.617: Vessel 2 - Truck transported container 65 to yard
Time 898.617: Vessel 2 - Crane moved container 66
Time 900.018: Vessel 1 - Truck transported container 66 to yard
Time 900.018: Vessel 1 - Crane moved container 67
Time 901.617: Vessel 2 - Container 66 loaded onto truck
Time 903.018: Vessel 1 - Container 67 loaded onto truck
Time 907.617: Vessel 2 - Truck transported container 66 to yard
Time 907.617: Vessel 2 - Crane moved container 67
Time 909.018: Vessel 1 - Truck transported container 67 to yard
Time 909.018: Vessel 1 - Crane moved container 68
Time 910.617: Vessel 2 - Container 67 loaded onto truck
Time 912.018: Vessel 1 - Container 68 loaded onto truck
Time 916.617: Vessel 2 - Truck transported container 67 to yard
Time 916.617: Vessel 2 - Crane moved container 68
Time 918.018: Vessel 1 - Truck transported container 68 to yard
Time 918.018: Vessel 1 - Crane moved container 69
Time 919.617: Vessel 2 - Container 68 loaded onto truck
Time 921.018: Vessel 1 - Container 69 loaded onto truck
Time 925.617: Vessel 2 - Truck transported container 68 to yard
Time 925.617: Vessel 2 - Crane moved container 69
Time 927.018: Vessel 1 - Truck transported container 69 to yard
Time 927.018: Vessel 1 - Crane moved container 70
Time 928.617: Vessel 2 - Container 69 loaded onto truck
Time 930.018: Vessel 1 - Container 70 loaded onto truck
Time 934.617: Vessel 2 - Truck transported container 69 to yard
Time 934.617: Vessel 2 - Crane moved container 70
Time 936.018: Vessel 1 - Truck transported container 70 to yard
Time 936.018: Vessel 1 - Crane moved container 71
Time 937.617: Vessel 2 - Container 70 loaded onto truck
Time 939.018: Vessel 1 - Container 71 loaded onto truck
Time 943.617: Vessel 2 - Truck transported container 70 to yard
Time 943.617: Vessel 2 - Crane moved container 71
Time 945.018: Vessel 1 - Truck transported container 71 to yard
Time 945.018: Vessel 1 - Crane moved container 72
Time 946.617: Vessel 2 - Container 71 loaded onto truck
Time 948.018: Vessel 1 - Container 72 loaded onto truck
Time 952.617: Vessel 2 - Truck transported container 71 to yard
Time 952.617: Vessel 2 - Crane moved container 72
Time 954.018: Vessel 1 - Truck transported container 72 to yard
Time 954.018: Vessel 1 - Crane moved container 73
Time 955.617: Vessel 2 - Container 72 loaded onto truck
Time 957.018: Vessel 1 - Container 73 loaded onto truck
Time 961.617: Vessel 2 - Truck transported container 72 to yard
Time 961.617: Vessel 2 - Crane moved container 73
Time 963.018: Vessel 1 - Truck transported container 73 to yard
Time 963.018: Vessel 1 - Crane moved container 74
Time 964.617: Vessel 2 - Container 73 loaded onto truck
Time 966.018: Vessel 1 - Container 74 loaded onto truck
Time 970.617: Vessel 2 - Truck transported container 73 to yard
Time 970.617: Vessel 2 - Crane moved container 74
Time 972.018: Vessel 1 - Truck transported container 74 to yard
Time 972.018: Vessel 1 - Crane moved container 75
Time 973.617: Vessel 2 - Container 74 loaded onto truck
Time 975.018: Vessel 1 - Container 75 loaded onto truck
Time 979.617: Vessel 2 - Truck transported container 74 to yard
Time 979.617: Vessel 2 - Crane moved container 75
Time 981.018: Vessel 1 - Truck transported container 75 to yard
Time 981.018: Vessel 1 - Crane moved container 76
Time 982.617: Vessel 2 - Container 75 loaded onto truck
Time 984.018: Vessel 1 - Container 76 loaded onto truck
Time 988.617: Vessel 2 - Truck transported container 75 to yard
Time 988.617: Vessel 2 - Crane moved container 76
Time 990.018: Vessel 1 - Truck transported container 76 to yard
Time 990.018: Vessel 1 - Crane moved container 77
Time 991.617: Vessel 2 - Container 76 loaded onto truck
Time 993.018: Vessel 1 - Container 77 loaded onto truck
Time 997.617: Vessel 2 - Truck transported container 76 to yard
Time 997.617: Vessel 2 - Crane moved container 77
Time 999.018: Vessel 1 - Truck transported container 77 to yard
Time 999.018: Vessel 1 - Crane moved container 78
