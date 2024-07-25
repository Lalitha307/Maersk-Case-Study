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
Total simulation time: 10000 minutes
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
Time 1000.617: Vessel 2 - Container 77 loaded onto truck
Time 1002.018: Vessel 1 - Container 78 loaded onto truck
Time 1006.617: Vessel 2 - Truck transported container 77 to yard
Time 1006.617: Vessel 2 - Crane moved container 78
Time 1008.018: Vessel 1 - Truck transported container 78 to yard
Time 1008.018: Vessel 1 - Crane moved container 79
Time 1009.617: Vessel 2 - Container 78 loaded onto truck
Time 1011.018: Vessel 1 - Container 79 loaded onto truck
Time 1015.617: Vessel 2 - Truck transported container 78 to yard
Time 1015.617: Vessel 2 - Crane moved container 79
Time 1017.018: Vessel 1 - Truck transported container 79 to yard
Time 1017.018: Vessel 1 - Crane moved container 80
Time 1018.617: Vessel 2 - Container 79 loaded onto truck
Time 1020.018: Vessel 1 - Container 80 loaded onto truck
Time 1024.617: Vessel 2 - Truck transported container 79 to yard
Time 1024.617: Vessel 2 - Crane moved container 80
Time 1026.018: Vessel 1 - Truck transported container 80 to yard
Time 1026.018: Vessel 1 - Crane moved container 81
Time 1027.617: Vessel 2 - Container 80 loaded onto truck
Time 1029.018: Vessel 1 - Container 81 loaded onto truck
Time 1033.617: Vessel 2 - Truck transported container 80 to yard
Time 1033.617: Vessel 2 - Crane moved container 81
Time 1035.018: Vessel 1 - Truck transported container 81 to yard
Time 1035.018: Vessel 1 - Crane moved container 82
Time 1036.617: Vessel 2 - Container 81 loaded onto truck
Time 1038.018: Vessel 1 - Container 82 loaded onto truck
Time 1042.617: Vessel 2 - Truck transported container 81 to yard
Time 1042.617: Vessel 2 - Crane moved container 82
Time 1044.018: Vessel 1 - Truck transported container 82 to yard
Time 1044.018: Vessel 1 - Crane moved container 83
Time 1045.617: Vessel 2 - Container 82 loaded onto truck
Time 1047.018: Vessel 1 - Container 83 loaded onto truck
Time 1051.617: Vessel 2 - Truck transported container 82 to yard
Time 1051.617: Vessel 2 - Crane moved container 83
Time 1053.018: Vessel 1 - Truck transported container 83 to yard
Time 1053.018: Vessel 1 - Crane moved container 84
Time 1054.617: Vessel 2 - Container 83 loaded onto truck
Time 1056.018: Vessel 1 - Container 84 loaded onto truck
Time 1060.617: Vessel 2 - Truck transported container 83 to yard
Time 1060.617: Vessel 2 - Crane moved container 84
Time 1062.018: Vessel 1 - Truck transported container 84 to yard
Time 1062.018: Vessel 1 - Crane moved container 85
Time 1063.617: Vessel 2 - Container 84 loaded onto truck
Time 1065.018: Vessel 1 - Container 85 loaded onto truck
Time 1069.617: Vessel 2 - Truck transported container 84 to yard
Time 1069.617: Vessel 2 - Crane moved container 85
Time 1071.018: Vessel 1 - Truck transported container 85 to yard
Time 1071.018: Vessel 1 - Crane moved container 86
Time 1072.617: Vessel 2 - Container 85 loaded onto truck
Time 1074.018: Vessel 1 - Container 86 loaded onto truck
Time 1078.617: Vessel 2 - Truck transported container 85 to yard
Time 1078.617: Vessel 2 - Crane moved container 86
Time 1080.018: Vessel 1 - Truck transported container 86 to yard
Time 1080.018: Vessel 1 - Crane moved container 87
Time 1081.617: Vessel 2 - Container 86 loaded onto truck
Time 1083.018: Vessel 1 - Container 87 loaded onto truck
Time 1087.617: Vessel 2 - Truck transported container 86 to yard
Time 1087.617: Vessel 2 - Crane moved container 87
Time 1089.018: Vessel 1 - Truck transported container 87 to yard
Time 1089.018: Vessel 1 - Crane moved container 88
Time 1090.617: Vessel 2 - Container 87 loaded onto truck
Time 1092.018: Vessel 1 - Container 88 loaded onto truck
Time 1096.617: Vessel 2 - Truck transported container 87 to yard
Time 1096.617: Vessel 2 - Crane moved container 88
Time 1098.018: Vessel 1 - Truck transported container 88 to yard
Time 1098.018: Vessel 1 - Crane moved container 89
Time 1099.617: Vessel 2 - Container 88 loaded onto truck
Time 1101.018: Vessel 1 - Container 89 loaded onto truck
Time 1105.617: Vessel 2 - Truck transported container 88 to yard
Time 1105.617: Vessel 2 - Crane moved container 89
Time 1107.018: Vessel 1 - Truck transported container 89 to yard
Time 1107.018: Vessel 1 - Crane moved container 90
Time 1108.617: Vessel 2 - Container 89 loaded onto truck
Time 1110.018: Vessel 1 - Container 90 loaded onto truck
Time 1114.617: Vessel 2 - Truck transported container 89 to yard
Time 1114.617: Vessel 2 - Crane moved container 90
Time 1116.018: Vessel 1 - Truck transported container 90 to yard
Time 1116.018: Vessel 1 - Crane moved container 91
Time 1117.617: Vessel 2 - Container 90 loaded onto truck
Time 1119.018: Vessel 1 - Container 91 loaded onto truck
Time 1123.617: Vessel 2 - Truck transported container 90 to yard
Time 1123.617: Vessel 2 - Crane moved container 91
Time 1125.018: Vessel 1 - Truck transported container 91 to yard
Time 1125.018: Vessel 1 - Crane moved container 92
Time 1126.617: Vessel 2 - Container 91 loaded onto truck
Time 1128.018: Vessel 1 - Container 92 loaded onto truck
Time 1132.617: Vessel 2 - Truck transported container 91 to yard
Time 1132.617: Vessel 2 - Crane moved container 92
Time 1134.018: Vessel 1 - Truck transported container 92 to yard
Time 1134.018: Vessel 1 - Crane moved container 93
Time 1135.617: Vessel 2 - Container 92 loaded onto truck
Time 1137.018: Vessel 1 - Container 93 loaded onto truck
Time 1141.617: Vessel 2 - Truck transported container 92 to yard
Time 1141.617: Vessel 2 - Crane moved container 93
Time 1143.018: Vessel 1 - Truck transported container 93 to yard
Time 1143.018: Vessel 1 - Crane moved container 94
Time 1144.617: Vessel 2 - Container 93 loaded onto truck
Time 1146.018: Vessel 1 - Container 94 loaded onto truck
Time 1150.617: Vessel 2 - Truck transported container 93 to yard
Time 1150.617: Vessel 2 - Crane moved container 94
Time 1152.018: Vessel 1 - Truck transported container 94 to yard
Time 1152.018: Vessel 1 - Crane moved container 95
Time 1153.617: Vessel 2 - Container 94 loaded onto truck
Time 1155.018: Vessel 1 - Container 95 loaded onto truck
Time 1159.617: Vessel 2 - Truck transported container 94 to yard
Time 1159.617: Vessel 2 - Crane moved container 95
Time 1161.018: Vessel 1 - Truck transported container 95 to yard
Time 1161.018: Vessel 1 - Crane moved container 96
Time 1162.617: Vessel 2 - Container 95 loaded onto truck
Time 1164.018: Vessel 1 - Container 96 loaded onto truck
Time 1168.617: Vessel 2 - Truck transported container 95 to yard
Time 1168.617: Vessel 2 - Crane moved container 96
Time 1170.018: Vessel 1 - Truck transported container 96 to yard
Time 1170.018: Vessel 1 - Crane moved container 97
Time 1171.617: Vessel 2 - Container 96 loaded onto truck
Time 1173.018: Vessel 1 - Container 97 loaded onto truck
Time 1177.617: Vessel 2 - Truck transported container 96 to yard
Time 1177.617: Vessel 2 - Crane moved container 97
Time 1179.018: Vessel 1 - Truck transported container 97 to yard
Time 1179.018: Vessel 1 - Crane moved container 98
Time 1180.617: Vessel 2 - Container 97 loaded onto truck
Time 1182.018: Vessel 1 - Container 98 loaded onto truck
Time 1186.617: Vessel 2 - Truck transported container 97 to yard
Time 1186.617: Vessel 2 - Crane moved container 98
Time 1188.018: Vessel 1 - Truck transported container 98 to yard
Time 1188.018: Vessel 1 - Crane moved container 99
Time 1189.617: Vessel 2 - Container 98 loaded onto truck
Time 1191.018: Vessel 1 - Container 99 loaded onto truck
Time 1195.617: Vessel 2 - Truck transported container 98 to yard
Time 1195.617: Vessel 2 - Crane moved container 99
Time 1197.018: Vessel 1 - Truck transported container 99 to yard
Time 1197.018: Vessel 1 - Crane moved container 100
Time 1198.617: Vessel 2 - Container 99 loaded onto truck
Time 1200.018: Vessel 1 - Container 100 loaded onto truck
Time 1204.617: Vessel 2 - Truck transported container 99 to yard
Time 1204.617: Vessel 2 - Crane moved container 100
Time 1206.018: Vessel 1 - Truck transported container 100 to yard
Time 1206.018: Vessel 1 - Crane moved container 101
Time 1207.617: Vessel 2 - Container 100 loaded onto truck
Time 1209.018: Vessel 1 - Container 101 loaded onto truck
Time 1213.617: Vessel 2 - Truck transported container 100 to yard
Time 1213.617: Vessel 2 - Crane moved container 101
Time 1215.018: Vessel 1 - Truck transported container 101 to yard
Time 1215.018: Vessel 1 - Crane moved container 102
Time 1216.617: Vessel 2 - Container 101 loaded onto truck
Time 1218.018: Vessel 1 - Container 102 loaded onto truck
Time 1222.617: Vessel 2 - Truck transported container 101 to yard
Time 1222.617: Vessel 2 - Crane moved container 102
Time 1224.018: Vessel 1 - Truck transported container 102 to yard
Time 1224.018: Vessel 1 - Crane moved container 103
Time 1224.710: Vessel 6 Arrived
Time 1224.710: Vessel 6 Waiting for a berth
Time 1225.617: Vessel 2 - Container 102 loaded onto truck
Time 1227.018: Vessel 1 - Container 103 loaded onto truck
Time 1231.617: Vessel 2 - Truck transported container 102 to yard
Time 1231.617: Vessel 2 - Crane moved container 103
Time 1233.018: Vessel 1 - Truck transported container 103 to yard
Time 1233.018: Vessel 1 - Crane moved container 104
Time 1234.617: Vessel 2 - Container 103 loaded onto truck
Time 1236.018: Vessel 1 - Container 104 loaded onto truck
Time 1240.617: Vessel 2 - Truck transported container 103 to yard
Time 1240.617: Vessel 2 - Crane moved container 104
Time 1242.018: Vessel 1 - Truck transported container 104 to yard
Time 1242.018: Vessel 1 - Crane moved container 105
Time 1243.617: Vessel 2 - Container 104 loaded onto truck
Time 1245.018: Vessel 1 - Container 105 loaded onto truck
Time 1249.617: Vessel 2 - Truck transported container 104 to yard
Time 1249.617: Vessel 2 - Crane moved container 105
Time 1251.018: Vessel 1 - Truck transported container 105 to yard
Time 1251.018: Vessel 1 - Crane moved container 106
Time 1252.617: Vessel 2 - Container 105 loaded onto truck
Time 1254.018: Vessel 1 - Container 106 loaded onto truck
Time 1258.617: Vessel 2 - Truck transported container 105 to yard
Time 1258.617: Vessel 2 - Crane moved container 106
Time 1260.018: Vessel 1 - Truck transported container 106 to yard
Time 1260.018: Vessel 1 - Crane moved container 107
Time 1261.617: Vessel 2 - Container 106 loaded onto truck
Time 1263.018: Vessel 1 - Container 107 loaded onto truck
Time 1267.617: Vessel 2 - Truck transported container 106 to yard
Time 1267.617: Vessel 2 - Crane moved container 107
Time 1269.018: Vessel 1 - Truck transported container 107 to yard
Time 1269.018: Vessel 1 - Crane moved container 108
Time 1270.617: Vessel 2 - Container 107 loaded onto truck
Time 1272.018: Vessel 1 - Container 108 loaded onto truck
Time 1276.617: Vessel 2 - Truck transported container 107 to yard
Time 1276.617: Vessel 2 - Crane moved container 108
Time 1278.018: Vessel 1 - Truck transported container 108 to yard
Time 1278.018: Vessel 1 - Crane moved container 109
Time 1279.617: Vessel 2 - Container 108 loaded onto truck
Time 1281.018: Vessel 1 - Container 109 loaded onto truck
Time 1285.617: Vessel 2 - Truck transported container 108 to yard
Time 1285.617: Vessel 2 - Crane moved container 109
Time 1287.018: Vessel 1 - Truck transported container 109 to yard
Time 1287.018: Vessel 1 - Crane moved container 110
Time 1288.617: Vessel 2 - Container 109 loaded onto truck
Time 1290.018: Vessel 1 - Container 110 loaded onto truck
Time 1294.617: Vessel 2 - Truck transported container 109 to yard
Time 1294.617: Vessel 2 - Crane moved container 110
Time 1296.018: Vessel 1 - Truck transported container 110 to yard
Time 1296.018: Vessel 1 - Crane moved container 111
Time 1297.617: Vessel 2 - Container 110 loaded onto truck
Time 1299.018: Vessel 1 - Container 111 loaded onto truck
Time 1303.617: Vessel 2 - Truck transported container 110 to yard
Time 1303.617: Vessel 2 - Crane moved container 111
Time 1305.018: Vessel 1 - Truck transported container 111 to yard
Time 1305.018: Vessel 1 - Crane moved container 112
Time 1306.617: Vessel 2 - Container 111 loaded onto truck
Time 1308.018: Vessel 1 - Container 112 loaded onto truck
Time 1312.617: Vessel 2 - Truck transported container 111 to yard
Time 1312.617: Vessel 2 - Crane moved container 112
Time 1314.018: Vessel 1 - Truck transported container 112 to yard
Time 1314.018: Vessel 1 - Crane moved container 113
Time 1315.617: Vessel 2 - Container 112 loaded onto truck
Time 1317.018: Vessel 1 - Container 113 loaded onto truck
Time 1321.617: Vessel 2 - Truck transported container 112 to yard
Time 1321.617: Vessel 2 - Crane moved container 113
Time 1323.018: Vessel 1 - Truck transported container 113 to yard
Time 1323.018: Vessel 1 - Crane moved container 114
Time 1324.617: Vessel 2 - Container 113 loaded onto truck
Time 1326.018: Vessel 1 - Container 114 loaded onto truck
Time 1330.617: Vessel 2 - Truck transported container 113 to yard
Time 1330.617: Vessel 2 - Crane moved container 114
Time 1332.018: Vessel 1 - Truck transported container 114 to yard
Time 1332.018: Vessel 1 - Crane moved container 115
Time 1333.617: Vessel 2 - Container 114 loaded onto truck
Time 1335.018: Vessel 1 - Container 115 loaded onto truck
Time 1339.617: Vessel 2 - Truck transported container 114 to yard
Time 1339.617: Vessel 2 - Crane moved container 115
Time 1341.018: Vessel 1 - Truck transported container 115 to yard
Time 1341.018: Vessel 1 - Crane moved container 116
Time 1342.617: Vessel 2 - Container 115 loaded onto truck
Time 1344.018: Vessel 1 - Container 116 loaded onto truck
Time 1348.617: Vessel 2 - Truck transported container 115 to yard
Time 1348.617: Vessel 2 - Crane moved container 116
Time 1350.018: Vessel 1 - Truck transported container 116 to yard
Time 1350.018: Vessel 1 - Crane moved container 117
Time 1351.617: Vessel 2 - Container 116 loaded onto truck
Time 1353.018: Vessel 1 - Container 117 loaded onto truck
Time 1357.617: Vessel 2 - Truck transported container 116 to yard
Time 1357.617: Vessel 2 - Crane moved container 117
Time 1359.018: Vessel 1 - Truck transported container 117 to yard
Time 1359.018: Vessel 1 - Crane moved container 118
Time 1360.617: Vessel 2 - Container 117 loaded onto truck
Time 1362.018: Vessel 1 - Container 118 loaded onto truck
Time 1366.617: Vessel 2 - Truck transported container 117 to yard
Time 1366.617: Vessel 2 - Crane moved container 118
Time 1368.018: Vessel 1 - Truck transported container 118 to yard
Time 1368.018: Vessel 1 - Crane moved container 119
Time 1369.617: Vessel 2 - Container 118 loaded onto truck
Time 1371.018: Vessel 1 - Container 119 loaded onto truck
Time 1375.617: Vessel 2 - Truck transported container 118 to yard
Time 1375.617: Vessel 2 - Crane moved container 119
Time 1377.018: Vessel 1 - Truck transported container 119 to yard
Time 1377.018: Vessel 1 - Crane moved container 120
Time 1378.617: Vessel 2 - Container 119 loaded onto truck
Time 1380.018: Vessel 1 - Container 120 loaded onto truck
Time 1384.617: Vessel 2 - Truck transported container 119 to yard
Time 1384.617: Vessel 2 - Crane moved container 120
Time 1386.018: Vessel 1 - Truck transported container 120 to yard
Time 1386.018: Vessel 1 - Crane moved container 121
Time 1387.617: Vessel 2 - Container 120 loaded onto truck
Time 1389.018: Vessel 1 - Container 121 loaded onto truck
Time 1393.617: Vessel 2 - Truck transported container 120 to yard
Time 1393.617: Vessel 2 - Crane moved container 121
Time 1395.018: Vessel 1 - Truck transported container 121 to yard
Time 1395.018: Vessel 1 - Crane moved container 122
Time 1396.617: Vessel 2 - Container 121 loaded onto truck
Time 1398.018: Vessel 1 - Container 122 loaded onto truck
Time 1402.617: Vessel 2 - Truck transported container 121 to yard
Time 1402.617: Vessel 2 - Crane moved container 122
Time 1404.018: Vessel 1 - Truck transported container 122 to yard
Time 1404.018: Vessel 1 - Crane moved container 123
Time 1405.617: Vessel 2 - Container 122 loaded onto truck
Time 1407.018: Vessel 1 - Container 123 loaded onto truck
Time 1411.617: Vessel 2 - Truck transported container 122 to yard
Time 1411.617: Vessel 2 - Crane moved container 123
Time 1413.018: Vessel 1 - Truck transported container 123 to yard
Time 1413.018: Vessel 1 - Crane moved container 124
Time 1414.617: Vessel 2 - Container 123 loaded onto truck
Time 1416.018: Vessel 1 - Container 124 loaded onto truck
Time 1420.617: Vessel 2 - Truck transported container 123 to yard
Time 1420.617: Vessel 2 - Crane moved container 124
Time 1422.018: Vessel 1 - Truck transported container 124 to yard
Time 1422.018: Vessel 1 - Crane moved container 125
Time 1423.617: Vessel 2 - Container 124 loaded onto truck
Time 1425.018: Vessel 1 - Container 125 loaded onto truck
Time 1429.617: Vessel 2 - Truck transported container 124 to yard
Time 1429.617: Vessel 2 - Crane moved container 125
Time 1431.018: Vessel 1 - Truck transported container 125 to yard
Time 1431.018: Vessel 1 - Crane moved container 126
Time 1432.617: Vessel 2 - Container 125 loaded onto truck
Time 1434.018: Vessel 1 - Container 126 loaded onto truck
Time 1438.617: Vessel 2 - Truck transported container 125 to yard
Time 1438.617: Vessel 2 - Crane moved container 126
Time 1440.018: Vessel 1 - Truck transported container 126 to yard
Time 1440.018: Vessel 1 - Crane moved container 127
Time 1441.617: Vessel 2 - Container 126 loaded onto truck
Time 1443.018: Vessel 1 - Container 127 loaded onto truck
Time 1447.617: Vessel 2 - Truck transported container 126 to yard
Time 1447.617: Vessel 2 - Crane moved container 127
Time 1449.018: Vessel 1 - Truck transported container 127 to yard
Time 1449.018: Vessel 1 - Crane moved container 128
Time 1450.617: Vessel 2 - Container 127 loaded onto truck
Time 1452.018: Vessel 1 - Container 128 loaded onto truck
Time 1456.617: Vessel 2 - Truck transported container 127 to yard
Time 1456.617: Vessel 2 - Crane moved container 128
Time 1458.018: Vessel 1 - Truck transported container 128 to yard
Time 1458.018: Vessel 1 - Crane moved container 129
Time 1459.617: Vessel 2 - Container 128 loaded onto truck
Time 1461.018: Vessel 1 - Container 129 loaded onto truck
Time 1465.617: Vessel 2 - Truck transported container 128 to yard
Time 1465.617: Vessel 2 - Crane moved container 129
Time 1467.018: Vessel 1 - Truck transported container 129 to yard
Time 1467.018: Vessel 1 - Crane moved container 130
Time 1468.617: Vessel 2 - Container 129 loaded onto truck
Time 1470.018: Vessel 1 - Container 130 loaded onto truck
Time 1474.617: Vessel 2 - Truck transported container 129 to yard
Time 1474.617: Vessel 2 - Crane moved container 130
Time 1476.018: Vessel 1 - Truck transported container 130 to yard
Time 1476.018: Vessel 1 - Crane moved container 131
Time 1477.617: Vessel 2 - Container 130 loaded onto truck
Time 1479.018: Vessel 1 - Container 131 loaded onto truck
Time 1483.617: Vessel 2 - Truck transported container 130 to yard
Time 1483.617: Vessel 2 - Crane moved container 131
Time 1485.018: Vessel 1 - Truck transported container 131 to yard
Time 1485.018: Vessel 1 - Crane moved container 132
Time 1486.617: Vessel 2 - Container 131 loaded onto truck
Time 1488.018: Vessel 1 - Container 132 loaded onto truck
Time 1492.617: Vessel 2 - Truck transported container 131 to yard
Time 1492.617: Vessel 2 - Crane moved container 132
Time 1494.018: Vessel 1 - Truck transported container 132 to yard
Time 1494.018: Vessel 1 - Crane moved container 133
Time 1495.617: Vessel 2 - Container 132 loaded onto truck
Time 1497.018: Vessel 1 - Container 133 loaded onto truck
Time 1501.617: Vessel 2 - Truck transported container 132 to yard
Time 1501.617: Vessel 2 - Crane moved container 133
Time 1503.018: Vessel 1 - Truck transported container 133 to yard
Time 1503.018: Vessel 1 - Crane moved container 134
Time 1504.617: Vessel 2 - Container 133 loaded onto truck
Time 1506.018: Vessel 1 - Container 134 loaded onto truck
Time 1510.617: Vessel 2 - Truck transported container 133 to yard
Time 1510.617: Vessel 2 - Crane moved container 134
Time 1512.018: Vessel 1 - Truck transported container 134 to yard
Time 1512.018: Vessel 1 - Crane moved container 135
Time 1513.617: Vessel 2 - Container 134 loaded onto truck
Time 1515.018: Vessel 1 - Container 135 loaded onto truck
Time 1519.617: Vessel 2 - Truck transported container 134 to yard
Time 1519.617: Vessel 2 - Crane moved container 135
Time 1521.018: Vessel 1 - Truck transported container 135 to yard
Time 1521.018: Vessel 1 - Crane moved container 136
Time 1522.617: Vessel 2 - Container 135 loaded onto truck
Time 1524.018: Vessel 1 - Container 136 loaded onto truck
Time 1528.617: Vessel 2 - Truck transported container 135 to yard
Time 1528.617: Vessel 2 - Crane moved container 136
Time 1530.018: Vessel 1 - Truck transported container 136 to yard
Time 1530.018: Vessel 1 - Crane moved container 137
Time 1531.617: Vessel 2 - Container 136 loaded onto truck
Time 1533.018: Vessel 1 - Container 137 loaded onto truck
Time 1537.617: Vessel 2 - Truck transported container 136 to yard
Time 1537.617: Vessel 2 - Crane moved container 137
Time 1539.018: Vessel 1 - Truck transported container 137 to yard
Time 1539.018: Vessel 1 - Crane moved container 138
Time 1540.617: Vessel 2 - Container 137 loaded onto truck
Time 1542.018: Vessel 1 - Container 138 loaded onto truck
Time 1546.617: Vessel 2 - Truck transported container 137 to yard
Time 1546.617: Vessel 2 - Crane moved container 138
Time 1548.018: Vessel 1 - Truck transported container 138 to yard
Time 1548.018: Vessel 1 - Crane moved container 139
Time 1549.617: Vessel 2 - Container 138 loaded onto truck
Time 1551.018: Vessel 1 - Container 139 loaded onto truck
Time 1555.617: Vessel 2 - Truck transported container 138 to yard
Time 1555.617: Vessel 2 - Crane moved container 139
Time 1557.018: Vessel 1 - Truck transported container 139 to yard
Time 1557.018: Vessel 1 - Crane moved container 140
Time 1558.617: Vessel 2 - Container 139 loaded onto truck
Time 1560.018: Vessel 1 - Container 140 loaded onto truck
Time 1564.617: Vessel 2 - Truck transported container 139 to yard
Time 1564.617: Vessel 2 - Crane moved container 140
Time 1566.018: Vessel 1 - Truck transported container 140 to yard
Time 1566.018: Vessel 1 - Crane moved container 141
Time 1567.617: Vessel 2 - Container 140 loaded onto truck
Time 1569.018: Vessel 1 - Container 141 loaded onto truck
Time 1573.617: Vessel 2 - Truck transported container 140 to yard
Time 1573.617: Vessel 2 - Crane moved container 141
Time 1575.018: Vessel 1 - Truck transported container 141 to yard
Time 1575.018: Vessel 1 - Crane moved container 142
Time 1576.617: Vessel 2 - Container 141 loaded onto truck
Time 1578.018: Vessel 1 - Container 142 loaded onto truck
Time 1582.617: Vessel 2 - Truck transported container 141 to yard
Time 1582.617: Vessel 2 - Crane moved container 142
Time 1584.018: Vessel 1 - Truck transported container 142 to yard
Time 1584.018: Vessel 1 - Crane moved container 143
Time 1585.617: Vessel 2 - Container 142 loaded onto truck
Time 1587.018: Vessel 1 - Container 143 loaded onto truck
Time 1591.617: Vessel 2 - Truck transported container 142 to yard
Time 1591.617: Vessel 2 - Crane moved container 143
Time 1593.018: Vessel 1 - Truck transported container 143 to yard
Time 1593.018: Vessel 1 - Crane moved container 144
Time 1594.617: Vessel 2 - Container 143 loaded onto truck
Time 1596.018: Vessel 1 - Container 144 loaded onto truck
Time 1600.617: Vessel 2 - Truck transported container 143 to yard
Time 1600.617: Vessel 2 - Crane moved container 144
Time 1602.018: Vessel 1 - Truck transported container 144 to yard
Time 1602.018: Vessel 1 - Crane moved container 145
Time 1603.617: Vessel 2 - Container 144 loaded onto truck
Time 1605.018: Vessel 1 - Container 145 loaded onto truck
Time 1609.617: Vessel 2 - Truck transported container 144 to yard
Time 1609.617: Vessel 2 - Crane moved container 145
Time 1611.018: Vessel 1 - Truck transported container 145 to yard
Time 1611.018: Vessel 1 - Crane moved container 146
Time 1612.617: Vessel 2 - Container 145 loaded onto truck
Time 1614.018: Vessel 1 - Container 146 loaded onto truck
Time 1618.617: Vessel 2 - Truck transported container 145 to yard
Time 1618.617: Vessel 2 - Crane moved container 146
Time 1620.018: Vessel 1 - Truck transported container 146 to yard
Time 1620.018: Vessel 1 - Crane moved container 147
Time 1621.617: Vessel 2 - Container 146 loaded onto truck
Time 1623.018: Vessel 1 - Container 147 loaded onto truck
Time 1627.617: Vessel 2 - Truck transported container 146 to yard
Time 1627.617: Vessel 2 - Crane moved container 147
Time 1629.018: Vessel 1 - Truck transported container 147 to yard
Time 1629.018: Vessel 1 - Crane moved container 148
Time 1630.617: Vessel 2 - Container 147 loaded onto truck
Time 1632.018: Vessel 1 - Container 148 loaded onto truck
Time 1636.617: Vessel 2 - Truck transported container 147 to yard
Time 1636.617: Vessel 2 - Crane moved container 148
Time 1638.018: Vessel 1 - Truck transported container 148 to yard
Time 1638.018: Vessel 1 - Crane moved container 149
Time 1639.617: Vessel 2 - Container 148 loaded onto truck
Time 1641.018: Vessel 1 - Container 149 loaded onto truck
Time 1645.617: Vessel 2 - Truck transported container 148 to yard
Time 1645.617: Vessel 2 - Crane moved container 149
Time 1647.018: Vessel 1 - Truck transported container 149 to yard
Time 1647.018: Vessel 1 - Crane moved container 150
Time 1648.617: Vessel 2 - Container 149 loaded onto truck
Time 1650.018: Vessel 1 - Container 150 loaded onto truck
Time 1654.617: Vessel 2 - Truck transported container 149 to yard
Time 1654.617: Vessel 2 - Crane moved container 150
Time 1656.018: Vessel 1 - Truck transported container 150 to yard
Time 1656.018: Vessel 1 finished unloading and leaves
Time 1656.018: Vessel 3 berthed
Time 1656.018: Vessel 3 - Crane allocated
Time 1656.018: Vessel 3 - Crane moved container 1
Time 1657.617: Vessel 2 - Container 150 loaded onto truck
Time 1659.018: Vessel 3 - Container 1 loaded onto truck
Time 1663.617: Vessel 2 - Truck transported container 150 to yard
Time 1663.617: Vessel 2 finished unloading and leaves
Time 1663.617: Vessel 4 berthed
Time 1663.617: Vessel 4 - Crane allocated
Time 1663.617: Vessel 4 - Crane moved container 1
Time 1665.018: Vessel 3 - Truck transported container 1 to yard
Time 1665.018: Vessel 3 - Crane moved container 2
Time 1666.617: Vessel 4 - Container 1 loaded onto truck
Time 1668.018: Vessel 3 - Container 2 loaded onto truck
Time 1672.617: Vessel 4 - Truck transported container 1 to yard
Time 1672.617: Vessel 4 - Crane moved container 2
Time 1674.018: Vessel 3 - Truck transported container 2 to yard
Time 1674.018: Vessel 3 - Crane moved container 3
Time 1675.617: Vessel 4 - Container 2 loaded onto truck
Time 1677.018: Vessel 3 - Container 3 loaded onto truck
Time 1681.617: Vessel 4 - Truck transported container 2 to yard
Time 1681.617: Vessel 4 - Crane moved container 3
Time 1683.018: Vessel 3 - Truck transported container 3 to yard
Time 1683.018: Vessel 3 - Crane moved container 4
Time 1684.617: Vessel 4 - Container 3 loaded onto truck
Time 1686.018: Vessel 3 - Container 4 loaded onto truck
Time 1690.617: Vessel 4 - Truck transported container 3 to yard
Time 1690.617: Vessel 4 - Crane moved container 4
Time 1692.018: Vessel 3 - Truck transported container 4 to yard
Time 1692.018: Vessel 3 - Crane moved container 5
Time 1693.617: Vessel 4 - Container 4 loaded onto truck
Time 1695.018: Vessel 3 - Container 5 loaded onto truck
Time 1699.617: Vessel 4 - Truck transported container 4 to yard
Time 1699.617: Vessel 4 - Crane moved container 5
Time 1701.018: Vessel 3 - Truck transported container 5 to yard
Time 1701.018: Vessel 3 - Crane moved container 6
Time 1702.617: Vessel 4 - Container 5 loaded onto truck
Time 1704.018: Vessel 3 - Container 6 loaded onto truck
Time 1708.617: Vessel 4 - Truck transported container 5 to yard
Time 1708.617: Vessel 4 - Crane moved container 6
Time 1710.018: Vessel 3 - Truck transported container 6 to yard
Time 1710.018: Vessel 3 - Crane moved container 7
Time 1711.617: Vessel 4 - Container 6 loaded onto truck
Time 1713.018: Vessel 3 - Container 7 loaded onto truck
Time 1717.617: Vessel 4 - Truck transported container 6 to yard
Time 1717.617: Vessel 4 - Crane moved container 7
Time 1719.018: Vessel 3 - Truck transported container 7 to yard
Time 1719.018: Vessel 3 - Crane moved container 8
Time 1720.617: Vessel 4 - Container 7 loaded onto truck
Time 1722.018: Vessel 3 - Container 8 loaded onto truck
Time 1726.617: Vessel 4 - Truck transported container 7 to yard
Time 1726.617: Vessel 4 - Crane moved container 8
Time 1728.018: Vessel 3 - Truck transported container 8 to yard
Time 1728.018: Vessel 3 - Crane moved container 9
Time 1729.617: Vessel 4 - Container 8 loaded onto truck
Time 1731.018: Vessel 3 - Container 9 loaded onto truck
Time 1735.617: Vessel 4 - Truck transported container 8 to yard
Time 1735.617: Vessel 4 - Crane moved container 9
Time 1737.018: Vessel 3 - Truck transported container 9 to yard
Time 1737.018: Vessel 3 - Crane moved container 10
Time 1738.617: Vessel 4 - Container 9 loaded onto truck
Time 1740.018: Vessel 3 - Container 10 loaded onto truck
Time 1744.617: Vessel 4 - Truck transported container 9 to yard
Time 1744.617: Vessel 4 - Crane moved container 10
Time 1746.018: Vessel 3 - Truck transported container 10 to yard
Time 1746.018: Vessel 3 - Crane moved container 11
Time 1747.617: Vessel 4 - Container 10 loaded onto truck
Time 1749.018: Vessel 3 - Container 11 loaded onto truck
Time 1753.617: Vessel 4 - Truck transported container 10 to yard
Time 1753.617: Vessel 4 - Crane moved container 11
Time 1755.018: Vessel 3 - Truck transported container 11 to yard
Time 1755.018: Vessel 3 - Crane moved container 12
Time 1756.617: Vessel 4 - Container 11 loaded onto truck
Time 1758.018: Vessel 3 - Container 12 loaded onto truck
Time 1762.617: Vessel 4 - Truck transported container 11 to yard
Time 1762.617: Vessel 4 - Crane moved container 12
Time 1764.018: Vessel 3 - Truck transported container 12 to yard
Time 1764.018: Vessel 3 - Crane moved container 13
Time 1765.617: Vessel 4 - Container 12 loaded onto truck
Time 1767.018: Vessel 3 - Container 13 loaded onto truck
Time 1771.617: Vessel 4 - Truck transported container 12 to yard
Time 1771.617: Vessel 4 - Crane moved container 13
Time 1773.018: Vessel 3 - Truck transported container 13 to yard
Time 1773.018: Vessel 3 - Crane moved container 14
Time 1774.617: Vessel 4 - Container 13 loaded onto truck
Time 1776.018: Vessel 3 - Container 14 loaded onto truck
Time 1780.617: Vessel 4 - Truck transported container 13 to yard
Time 1780.617: Vessel 4 - Crane moved container 14
Time 1782.018: Vessel 3 - Truck transported container 14 to yard
Time 1782.018: Vessel 3 - Crane moved container 15
Time 1783.617: Vessel 4 - Container 14 loaded onto truck
Time 1785.018: Vessel 3 - Container 15 loaded onto truck
Time 1789.617: Vessel 4 - Truck transported container 14 to yard
Time 1789.617: Vessel 4 - Crane moved container 15
Time 1791.018: Vessel 3 - Truck transported container 15 to yard
Time 1791.018: Vessel 3 - Crane moved container 16
Time 1792.617: Vessel 4 - Container 15 loaded onto truck
Time 1794.018: Vessel 3 - Container 16 loaded onto truck
Time 1798.617: Vessel 4 - Truck transported container 15 to yard
Time 1798.617: Vessel 4 - Crane moved container 16
Time 1800.018: Vessel 3 - Truck transported container 16 to yard
Time 1800.018: Vessel 3 - Crane moved container 17
Time 1801.617: Vessel 4 - Container 16 loaded onto truck
Time 1803.018: Vessel 3 - Container 17 loaded onto truck
Time 1807.617: Vessel 4 - Truck transported container 16 to yard
Time 1807.617: Vessel 4 - Crane moved container 17
Time 1809.018: Vessel 3 - Truck transported container 17 to yard
Time 1809.018: Vessel 3 - Crane moved container 18
Time 1810.617: Vessel 4 - Container 17 loaded onto truck
Time 1812.018: Vessel 3 - Container 18 loaded onto truck
Time 1816.617: Vessel 4 - Truck transported container 17 to yard
Time 1816.617: Vessel 4 - Crane moved container 18
Time 1818.018: Vessel 3 - Truck transported container 18 to yard
Time 1818.018: Vessel 3 - Crane moved container 19
Time 1819.617: Vessel 4 - Container 18 loaded onto truck
Time 1821.018: Vessel 3 - Container 19 loaded onto truck
Time 1825.617: Vessel 4 - Truck transported container 18 to yard
Time 1825.617: Vessel 4 - Crane moved container 19
Time 1827.018: Vessel 3 - Truck transported container 19 to yard
Time 1827.018: Vessel 3 - Crane moved container 20
Time 1828.617: Vessel 4 - Container 19 loaded onto truck
Time 1830.018: Vessel 3 - Container 20 loaded onto truck
Time 1834.617: Vessel 4 - Truck transported container 19 to yard
Time 1834.617: Vessel 4 - Crane moved container 20
Time 1836.018: Vessel 3 - Truck transported container 20 to yard
Time 1836.018: Vessel 3 - Crane moved container 21
Time 1837.617: Vessel 4 - Container 20 loaded onto truck
Time 1839.018: Vessel 3 - Container 21 loaded onto truck
Time 1843.617: Vessel 4 - Truck transported container 20 to yard
Time 1843.617: Vessel 4 - Crane moved container 21
Time 1845.018: Vessel 3 - Truck transported container 21 to yard
Time 1845.018: Vessel 3 - Crane moved container 22
Time 1846.617: Vessel 4 - Container 21 loaded onto truck
Time 1848.018: Vessel 3 - Container 22 loaded onto truck
Time 1852.617: Vessel 4 - Truck transported container 21 to yard
Time 1852.617: Vessel 4 - Crane moved container 22
Time 1854.018: Vessel 3 - Truck transported container 22 to yard
Time 1854.018: Vessel 3 - Crane moved container 23
Time 1855.617: Vessel 4 - Container 22 loaded onto truck
Time 1857.018: Vessel 3 - Container 23 loaded onto truck
Time 1861.617: Vessel 4 - Truck transported container 22 to yard
Time 1861.617: Vessel 4 - Crane moved container 23
Time 1863.018: Vessel 3 - Truck transported container 23 to yard
Time 1863.018: Vessel 3 - Crane moved container 24
Time 1864.617: Vessel 4 - Container 23 loaded onto truck
Time 1866.018: Vessel 3 - Container 24 loaded onto truck
Time 1870.617: Vessel 4 - Truck transported container 23 to yard
Time 1870.617: Vessel 4 - Crane moved container 24
Time 1872.018: Vessel 3 - Truck transported container 24 to yard
Time 1872.018: Vessel 3 - Crane moved container 25
Time 1873.617: Vessel 4 - Container 24 loaded onto truck
Time 1875.018: Vessel 3 - Container 25 loaded onto truck
Time 1879.617: Vessel 4 - Truck transported container 24 to yard
Time 1879.617: Vessel 4 - Crane moved container 25
Time 1881.018: Vessel 3 - Truck transported container 25 to yard
Time 1881.018: Vessel 3 - Crane moved container 26
Time 1882.617: Vessel 4 - Container 25 loaded onto truck
Time 1884.018: Vessel 3 - Container 26 loaded onto truck
Time 1888.617: Vessel 4 - Truck transported container 25 to yard
Time 1888.617: Vessel 4 - Crane moved container 26
Time 1890.018: Vessel 3 - Truck transported container 26 to yard
Time 1890.018: Vessel 3 - Crane moved container 27
Time 1891.617: Vessel 4 - Container 26 loaded onto truck
Time 1892.896: Vessel 7 Arrived
Time 1892.896: Vessel 7 Waiting for a berth
Time 1893.018: Vessel 3 - Container 27 loaded onto truck
Time 1897.617: Vessel 4 - Truck transported container 26 to yard
Time 1897.617: Vessel 4 - Crane moved container 27
Time 1899.018: Vessel 3 - Truck transported container 27 to yard
Time 1899.018: Vessel 3 - Crane moved container 28
Time 1900.617: Vessel 4 - Container 27 loaded onto truck
Time 1902.018: Vessel 3 - Container 28 loaded onto truck
Time 1906.617: Vessel 4 - Truck transported container 27 to yard
Time 1906.617: Vessel 4 - Crane moved container 28
Time 1908.018: Vessel 3 - Truck transported container 28 to yard
Time 1908.018: Vessel 3 - Crane moved container 29
Time 1909.617: Vessel 4 - Container 28 loaded onto truck
Time 1911.018: Vessel 3 - Container 29 loaded onto truck
Time 1915.617: Vessel 4 - Truck transported container 28 to yard
Time 1915.617: Vessel 4 - Crane moved container 29
Time 1917.018: Vessel 3 - Truck transported container 29 to yard
Time 1917.018: Vessel 3 - Crane moved container 30
Time 1918.617: Vessel 4 - Container 29 loaded onto truck
Time 1920.018: Vessel 3 - Container 30 loaded onto truck
Time 1920.182: Vessel 8 Arrived
Time 1920.182: Vessel 8 Waiting for a berth
Time 1924.617: Vessel 4 - Truck transported container 29 to yard
Time 1924.617: Vessel 4 - Crane moved container 30
Time 1926.018: Vessel 3 - Truck transported container 30 to yard
Time 1926.018: Vessel 3 - Crane moved container 31
Time 1927.617: Vessel 4 - Container 30 loaded onto truck
Time 1929.018: Vessel 3 - Container 31 loaded onto truck
Time 1933.617: Vessel 4 - Truck transported container 30 to yard
Time 1933.617: Vessel 4 - Crane moved container 31
Time 1935.018: Vessel 3 - Truck transported container 31 to yard
Time 1935.018: Vessel 3 - Crane moved container 32
Time 1936.617: Vessel 4 - Container 31 loaded onto truck
Time 1938.018: Vessel 3 - Container 32 loaded onto truck
Time 1942.617: Vessel 4 - Truck transported container 31 to yard
Time 1942.617: Vessel 4 - Crane moved container 32
Time 1944.018: Vessel 3 - Truck transported container 32 to yard
Time 1944.018: Vessel 3 - Crane moved container 33
Time 1945.617: Vessel 4 - Container 32 loaded onto truck
Time 1947.018: Vessel 3 - Container 33 loaded onto truck
Time 1951.617: Vessel 4 - Truck transported container 32 to yard
Time 1951.617: Vessel 4 - Crane moved container 33
Time 1953.018: Vessel 3 - Truck transported container 33 to yard
Time 1953.018: Vessel 3 - Crane moved container 34
Time 1954.617: Vessel 4 - Container 33 loaded onto truck
Time 1956.018: Vessel 3 - Container 34 loaded onto truck
Time 1960.617: Vessel 4 - Truck transported container 33 to yard
Time 1960.617: Vessel 4 - Crane moved container 34
Time 1962.018: Vessel 3 - Truck transported container 34 to yard
Time 1962.018: Vessel 3 - Crane moved container 35
Time 1963.617: Vessel 4 - Container 34 loaded onto truck
Time 1965.018: Vessel 3 - Container 35 loaded onto truck
Time 1969.617: Vessel 4 - Truck transported container 34 to yard
Time 1969.617: Vessel 4 - Crane moved container 35
Time 1971.018: Vessel 3 - Truck transported container 35 to yard
Time 1971.018: Vessel 3 - Crane moved container 36
Time 1972.617: Vessel 4 - Container 35 loaded onto truck
Time 1974.018: Vessel 3 - Container 36 loaded onto truck
Time 1978.617: Vessel 4 - Truck transported container 35 to yard
Time 1978.617: Vessel 4 - Crane moved container 36
Time 1980.018: Vessel 3 - Truck transported container 36 to yard
Time 1980.018: Vessel 3 - Crane moved container 37
Time 1981.617: Vessel 4 - Container 36 loaded onto truck
Time 1983.018: Vessel 3 - Container 37 loaded onto truck
Time 1987.617: Vessel 4 - Truck transported container 36 to yard
Time 1987.617: Vessel 4 - Crane moved container 37
Time 1989.018: Vessel 3 - Truck transported container 37 to yard
Time 1989.018: Vessel 3 - Crane moved container 38
Time 1990.617: Vessel 4 - Container 37 loaded onto truck
Time 1992.018: Vessel 3 - Container 38 loaded onto truck
Time 1996.617: Vessel 4 - Truck transported container 37 to yard
Time 1996.617: Vessel 4 - Crane moved container 38
Time 1998.018: Vessel 3 - Truck transported container 38 to yard
Time 1998.018: Vessel 3 - Crane moved container 39
Time 1999.617: Vessel 4 - Container 38 loaded onto truck
Time 2001.018: Vessel 3 - Container 39 loaded onto truck
Time 2005.617: Vessel 4 - Truck transported container 38 to yard
Time 2005.617: Vessel 4 - Crane moved container 39
Time 2007.018: Vessel 3 - Truck transported container 39 to yard
Time 2007.018: Vessel 3 - Crane moved container 40
Time 2008.617: Vessel 4 - Container 39 loaded onto truck
Time 2010.018: Vessel 3 - Container 40 loaded onto truck
Time 2014.617: Vessel 4 - Truck transported container 39 to yard
Time 2014.617: Vessel 4 - Crane moved container 40
Time 2016.018: Vessel 3 - Truck transported container 40 to yard
Time 2016.018: Vessel 3 - Crane moved container 41
Time 2017.617: Vessel 4 - Container 40 loaded onto truck
Time 2019.018: Vessel 3 - Container 41 loaded onto truck
Time 2023.617: Vessel 4 - Truck transported container 40 to yard
Time 2023.617: Vessel 4 - Crane moved container 41
Time 2025.018: Vessel 3 - Truck transported container 41 to yard
Time 2025.018: Vessel 3 - Crane moved container 42
Time 2026.617: Vessel 4 - Container 41 loaded onto truck
Time 2028.018: Vessel 3 - Container 42 loaded onto truck
Time 2032.617: Vessel 4 - Truck transported container 41 to yard
Time 2032.617: Vessel 4 - Crane moved container 42
Time 2034.018: Vessel 3 - Truck transported container 42 to yard
Time 2034.018: Vessel 3 - Crane moved container 43
Time 2035.617: Vessel 4 - Container 42 loaded onto truck
Time 2037.018: Vessel 3 - Container 43 loaded onto truck
Time 2041.617: Vessel 4 - Truck transported container 42 to yard
Time 2041.617: Vessel 4 - Crane moved container 43
Time 2043.018: Vessel 3 - Truck transported container 43 to yard
Time 2043.018: Vessel 3 - Crane moved container 44
Time 2044.617: Vessel 4 - Container 43 loaded onto truck
Time 2046.018: Vessel 3 - Container 44 loaded onto truck
Time 2050.617: Vessel 4 - Truck transported container 43 to yard
Time 2050.617: Vessel 4 - Crane moved container 44
Time 2052.018: Vessel 3 - Truck transported container 44 to yard
Time 2052.018: Vessel 3 - Crane moved container 45
Time 2053.617: Vessel 4 - Container 44 loaded onto truck
Time 2055.018: Vessel 3 - Container 45 loaded onto truck
Time 2059.617: Vessel 4 - Truck transported container 44 to yard
Time 2059.617: Vessel 4 - Crane moved container 45
Time 2061.018: Vessel 3 - Truck transported container 45 to yard
Time 2061.018: Vessel 3 - Crane moved container 46
Time 2062.617: Vessel 4 - Container 45 loaded onto truck
Time 2064.018: Vessel 3 - Container 46 loaded onto truck
Time 2068.617: Vessel 4 - Truck transported container 45 to yard
Time 2068.617: Vessel 4 - Crane moved container 46
Time 2070.018: Vessel 3 - Truck transported container 46 to yard
Time 2070.018: Vessel 3 - Crane moved container 47
Time 2071.617: Vessel 4 - Container 46 loaded onto truck
Time 2073.018: Vessel 3 - Container 47 loaded onto truck
Time 2077.617: Vessel 4 - Truck transported container 46 to yard
Time 2077.617: Vessel 4 - Crane moved container 47
Time 2079.018: Vessel 3 - Truck transported container 47 to yard
Time 2079.018: Vessel 3 - Crane moved container 48
Time 2080.617: Vessel 4 - Container 47 loaded onto truck
Time 2082.018: Vessel 3 - Container 48 loaded onto truck
Time 2084.596: Vessel 9 Arrived
Time 2084.596: Vessel 9 Waiting for a berth
Time 2086.617: Vessel 4 - Truck transported container 47 to yard
Time 2086.617: Vessel 4 - Crane moved container 48
Time 2088.018: Vessel 3 - Truck transported container 48 to yard
Time 2088.018: Vessel 3 - Crane moved container 49
Time 2089.617: Vessel 4 - Container 48 loaded onto truck
Time 2091.018: Vessel 3 - Container 49 loaded onto truck
Time 2093.671: Vessel 10 Arrived
Time 2093.671: Vessel 10 Waiting for a berth
Time 2095.617: Vessel 4 - Truck transported container 48 to yard
Time 2095.617: Vessel 4 - Crane moved container 49
Time 2097.018: Vessel 3 - Truck transported container 49 to yard
Time 2097.018: Vessel 3 - Crane moved container 50
Time 2098.617: Vessel 4 - Container 49 loaded onto truck
Time 2100.018: Vessel 3 - Container 50 loaded onto truck
Time 2104.617: Vessel 4 - Truck transported container 49 to yard
Time 2104.617: Vessel 4 - Crane moved container 50
Time 2106.018: Vessel 3 - Truck transported container 50 to yard
Time 2106.018: Vessel 3 - Crane moved container 51
Time 2107.617: Vessel 4 - Container 50 loaded onto truck
Time 2109.018: Vessel 3 - Container 51 loaded onto truck
Time 2113.617: Vessel 4 - Truck transported container 50 to yard
Time 2113.617: Vessel 4 - Crane moved container 51
Time 2115.018: Vessel 3 - Truck transported container 51 to yard
Time 2115.018: Vessel 3 - Crane moved container 52
Time 2116.617: Vessel 4 - Container 51 loaded onto truck
Time 2118.018: Vessel 3 - Container 52 loaded onto truck
Time 2122.617: Vessel 4 - Truck transported container 51 to yard
Time 2122.617: Vessel 4 - Crane moved container 52
Time 2124.018: Vessel 3 - Truck transported container 52 to yard
Time 2124.018: Vessel 3 - Crane moved container 53
Time 2125.617: Vessel 4 - Container 52 loaded onto truck
Time 2127.018: Vessel 3 - Container 53 loaded onto truck
Time 2131.617: Vessel 4 - Truck transported container 52 to yard
Time 2131.617: Vessel 4 - Crane moved container 53
Time 2133.018: Vessel 3 - Truck transported container 53 to yard
Time 2133.018: Vessel 3 - Crane moved container 54
Time 2134.617: Vessel 4 - Container 53 loaded onto truck
Time 2136.018: Vessel 3 - Container 54 loaded onto truck
Time 2140.617: Vessel 4 - Truck transported container 53 to yard
Time 2140.617: Vessel 4 - Crane moved container 54
Time 2142.018: Vessel 3 - Truck transported container 54 to yard
Time 2142.018: Vessel 3 - Crane moved container 55
Time 2143.617: Vessel 4 - Container 54 loaded onto truck
Time 2145.018: Vessel 3 - Container 55 loaded onto truck
Time 2149.617: Vessel 4 - Truck transported container 54 to yard
Time 2149.617: Vessel 4 - Crane moved container 55
Time 2151.018: Vessel 3 - Truck transported container 55 to yard
Time 2151.018: Vessel 3 - Crane moved container 56
Time 2152.617: Vessel 4 - Container 55 loaded onto truck
Time 2154.018: Vessel 3 - Container 56 loaded onto truck
Time 2158.617: Vessel 4 - Truck transported container 55 to yard
Time 2158.617: Vessel 4 - Crane moved container 56
Time 2160.018: Vessel 3 - Truck transported container 56 to yard
Time 2160.018: Vessel 3 - Crane moved container 57
Time 2161.617: Vessel 4 - Container 56 loaded onto truck
Time 2163.018: Vessel 3 - Container 57 loaded onto truck
Time 2167.617: Vessel 4 - Truck transported container 56 to yard
Time 2167.617: Vessel 4 - Crane moved container 57
Time 2167.686: Vessel 11 Arrived
Time 2167.686: Vessel 11 Waiting for a berth
Time 2169.018: Vessel 3 - Truck transported container 57 to yard
Time 2169.018: Vessel 3 - Crane moved container 58
Time 2170.617: Vessel 4 - Container 57 loaded onto truck
Time 2172.018: Vessel 3 - Container 58 loaded onto truck
Time 2176.617: Vessel 4 - Truck transported container 57 to yard
Time 2176.617: Vessel 4 - Crane moved container 58
Time 2178.018: Vessel 3 - Truck transported container 58 to yard
Time 2178.018: Vessel 3 - Crane moved container 59
Time 2179.617: Vessel 4 - Container 58 loaded onto truck
Time 2181.018: Vessel 3 - Container 59 loaded onto truck
Time 2185.617: Vessel 4 - Truck transported container 58 to yard
Time 2185.617: Vessel 4 - Crane moved container 59
Time 2187.018: Vessel 3 - Truck transported container 59 to yard
Time 2187.018: Vessel 3 - Crane moved container 60
Time 2188.617: Vessel 4 - Container 59 loaded onto truck
Time 2190.018: Vessel 3 - Container 60 loaded onto truck
Time 2194.617: Vessel 4 - Truck transported container 59 to yard
Time 2194.617: Vessel 4 - Crane moved container 60
Time 2196.018: Vessel 3 - Truck transported container 60 to yard
Time 2196.018: Vessel 3 - Crane moved container 61
Time 2197.617: Vessel 4 - Container 60 loaded onto truck
Time 2199.018: Vessel 3 - Container 61 loaded onto truck
Time 2203.617: Vessel 4 - Truck transported container 60 to yard
Time 2203.617: Vessel 4 - Crane moved container 61
Time 2205.018: Vessel 3 - Truck transported container 61 to yard
Time 2205.018: Vessel 3 - Crane moved container 62
Time 2206.617: Vessel 4 - Container 61 loaded onto truck
Time 2208.018: Vessel 3 - Container 62 loaded onto truck
Time 2212.617: Vessel 4 - Truck transported container 61 to yard
Time 2212.617: Vessel 4 - Crane moved container 62
Time 2214.018: Vessel 3 - Truck transported container 62 to yard
Time 2214.018: Vessel 3 - Crane moved container 63
Time 2215.617: Vessel 4 - Container 62 loaded onto truck
Time 2217.018: Vessel 3 - Container 63 loaded onto truck
Time 2221.617: Vessel 4 - Truck transported container 62 to yard
Time 2221.617: Vessel 4 - Crane moved container 63
Time 2223.018: Vessel 3 - Truck transported container 63 to yard
Time 2223.018: Vessel 3 - Crane moved container 64
Time 2224.617: Vessel 4 - Container 63 loaded onto truck
Time 2226.018: Vessel 3 - Container 64 loaded onto truck
Time 2230.617: Vessel 4 - Truck transported container 63 to yard
Time 2230.617: Vessel 4 - Crane moved container 64
Time 2232.018: Vessel 3 - Truck transported container 64 to yard
Time 2232.018: Vessel 3 - Crane moved container 65
Time 2233.617: Vessel 4 - Container 64 loaded onto truck
Time 2235.018: Vessel 3 - Container 65 loaded onto truck
Time 2239.617: Vessel 4 - Truck transported container 64 to yard
Time 2239.617: Vessel 4 - Crane moved container 65
Time 2241.018: Vessel 3 - Truck transported container 65 to yard
Time 2241.018: Vessel 3 - Crane moved container 66
Time 2242.617: Vessel 4 - Container 65 loaded onto truck
Time 2244.018: Vessel 3 - Container 66 loaded onto truck
Time 2248.617: Vessel 4 - Truck transported container 65 to yard
Time 2248.617: Vessel 4 - Crane moved container 66
Time 2250.018: Vessel 3 - Truck transported container 66 to yard
Time 2250.018: Vessel 3 - Crane moved container 67
Time 2251.617: Vessel 4 - Container 66 loaded onto truck
Time 2253.018: Vessel 3 - Container 67 loaded onto truck
Time 2257.617: Vessel 4 - Truck transported container 66 to yard
Time 2257.617: Vessel 4 - Crane moved container 67
Time 2259.018: Vessel 3 - Truck transported container 67 to yard
Time 2259.018: Vessel 3 - Crane moved container 68
Time 2260.617: Vessel 4 - Container 67 loaded onto truck
Time 2262.018: Vessel 3 - Container 68 loaded onto truck
Time 2266.617: Vessel 4 - Truck transported container 67 to yard
Time 2266.617: Vessel 4 - Crane moved container 68
Time 2268.018: Vessel 3 - Truck transported container 68 to yard
Time 2268.018: Vessel 3 - Crane moved container 69
Time 2269.617: Vessel 4 - Container 68 loaded onto truck
Time 2271.018: Vessel 3 - Container 69 loaded onto truck
Time 2275.617: Vessel 4 - Truck transported container 68 to yard
Time 2275.617: Vessel 4 - Crane moved container 69
Time 2277.018: Vessel 3 - Truck transported container 69 to yard
Time 2277.018: Vessel 3 - Crane moved container 70
Time 2278.617: Vessel 4 - Container 69 loaded onto truck
Time 2280.018: Vessel 3 - Container 70 loaded onto truck
Time 2284.617: Vessel 4 - Truck transported container 69 to yard
Time 2284.617: Vessel 4 - Crane moved container 70
Time 2286.018: Vessel 3 - Truck transported container 70 to yard
Time 2286.018: Vessel 3 - Crane moved container 71
Time 2287.617: Vessel 4 - Container 70 loaded onto truck
Time 2289.018: Vessel 3 - Container 71 loaded onto truck
Time 2293.617: Vessel 4 - Truck transported container 70 to yard
Time 2293.617: Vessel 4 - Crane moved container 71
Time 2295.018: Vessel 3 - Truck transported container 71 to yard
Time 2295.018: Vessel 3 - Crane moved container 72
Time 2296.617: Vessel 4 - Container 71 loaded onto truck
Time 2298.018: Vessel 3 - Container 72 loaded onto truck
Time 2302.617: Vessel 4 - Truck transported container 71 to yard
Time 2302.617: Vessel 4 - Crane moved container 72
Time 2304.018: Vessel 3 - Truck transported container 72 to yard
Time 2304.018: Vessel 3 - Crane moved container 73
Time 2305.617: Vessel 4 - Container 72 loaded onto truck
Time 2307.018: Vessel 3 - Container 73 loaded onto truck
Time 2311.617: Vessel 4 - Truck transported container 72 to yard
Time 2311.617: Vessel 4 - Crane moved container 73
Time 2313.018: Vessel 3 - Truck transported container 73 to yard
Time 2313.018: Vessel 3 - Crane moved container 74
Time 2314.617: Vessel 4 - Container 73 loaded onto truck
Time 2316.018: Vessel 3 - Container 74 loaded onto truck
Time 2320.617: Vessel 4 - Truck transported container 73 to yard
Time 2320.617: Vessel 4 - Crane moved container 74
Time 2322.018: Vessel 3 - Truck transported container 74 to yard
Time 2322.018: Vessel 3 - Crane moved container 75
Time 2323.617: Vessel 4 - Container 74 loaded onto truck
Time 2325.018: Vessel 3 - Container 75 loaded onto truck
Time 2329.617: Vessel 4 - Truck transported container 74 to yard
Time 2329.617: Vessel 4 - Crane moved container 75
Time 2331.018: Vessel 3 - Truck transported container 75 to yard
Time 2331.018: Vessel 3 - Crane moved container 76
Time 2332.617: Vessel 4 - Container 75 loaded onto truck
Time 2334.018: Vessel 3 - Container 76 loaded onto truck
Time 2338.617: Vessel 4 - Truck transported container 75 to yard
Time 2338.617: Vessel 4 - Crane moved container 76
Time 2340.018: Vessel 3 - Truck transported container 76 to yard
Time 2340.018: Vessel 3 - Crane moved container 77
Time 2341.617: Vessel 4 - Container 76 loaded onto truck
Time 2343.018: Vessel 3 - Container 77 loaded onto truck
Time 2347.617: Vessel 4 - Truck transported container 76 to yard
Time 2347.617: Vessel 4 - Crane moved container 77
Time 2349.018: Vessel 3 - Truck transported container 77 to yard
Time 2349.018: Vessel 3 - Crane moved container 78
Time 2350.617: Vessel 4 - Container 77 loaded onto truck
Time 2352.018: Vessel 3 - Container 78 loaded onto truck
Time 2356.617: Vessel 4 - Truck transported container 77 to yard
Time 2356.617: Vessel 4 - Crane moved container 78
Time 2358.018: Vessel 3 - Truck transported container 78 to yard
Time 2358.018: Vessel 3 - Crane moved container 79
Time 2359.617: Vessel 4 - Container 78 loaded onto truck
Time 2361.018: Vessel 3 - Container 79 loaded onto truck
Time 2365.617: Vessel 4 - Truck transported container 78 to yard
Time 2365.617: Vessel 4 - Crane moved container 79
Time 2367.018: Vessel 3 - Truck transported container 79 to yard
Time 2367.018: Vessel 3 - Crane moved container 80
Time 2368.617: Vessel 4 - Container 79 loaded onto truck
Time 2370.018: Vessel 3 - Container 80 loaded onto truck
Time 2374.617: Vessel 4 - Truck transported container 79 to yard
Time 2374.617: Vessel 4 - Crane moved container 80
Time 2376.018: Vessel 3 - Truck transported container 80 to yard
Time 2376.018: Vessel 3 - Crane moved container 81
Time 2377.617: Vessel 4 - Container 80 loaded onto truck
Time 2378.860: Vessel 12 Arrived
Time 2378.860: Vessel 12 Waiting for a berth
Time 2379.018: Vessel 3 - Container 81 loaded onto truck
Time 2383.617: Vessel 4 - Truck transported container 80 to yard
Time 2383.617: Vessel 4 - Crane moved container 81
Time 2385.018: Vessel 3 - Truck transported container 81 to yard
Time 2385.018: Vessel 3 - Crane moved container 82
Time 2386.617: Vessel 4 - Container 81 loaded onto truck
Time 2386.929: Vessel 13 Arrived
Time 2386.929: Vessel 13 Waiting for a berth
Time 2388.018: Vessel 3 - Container 82 loaded onto truck
Time 2392.617: Vessel 4 - Truck transported container 81 to yard
Time 2392.617: Vessel 4 - Crane moved container 82
Time 2394.018: Vessel 3 - Truck transported container 82 to yard
Time 2394.018: Vessel 3 - Crane moved container 83
Time 2395.617: Vessel 4 - Container 82 loaded onto truck
Time 2397.018: Vessel 3 - Container 83 loaded onto truck
Time 2401.617: Vessel 4 - Truck transported container 82 to yard
Time 2401.617: Vessel 4 - Crane moved container 83
Time 2403.018: Vessel 3 - Truck transported container 83 to yard
Time 2403.018: Vessel 3 - Crane moved container 84
Time 2404.617: Vessel 4 - Container 83 loaded onto truck
Time 2406.018: Vessel 3 - Container 84 loaded onto truck
Time 2410.617: Vessel 4 - Truck transported container 83 to yard
Time 2410.617: Vessel 4 - Crane moved container 84
Time 2412.018: Vessel 3 - Truck transported container 84 to yard
Time 2412.018: Vessel 3 - Crane moved container 85
Time 2413.617: Vessel 4 - Container 84 loaded onto truck
Time 2415.018: Vessel 3 - Container 85 loaded onto truck
Time 2419.617: Vessel 4 - Truck transported container 84 to yard
Time 2419.617: Vessel 4 - Crane moved container 85
Time 2421.018: Vessel 3 - Truck transported container 85 to yard
Time 2421.018: Vessel 3 - Crane moved container 86
Time 2422.617: Vessel 4 - Container 85 loaded onto truck
Time 2424.018: Vessel 3 - Container 86 loaded onto truck
Time 2428.617: Vessel 4 - Truck transported container 85 to yard
Time 2428.617: Vessel 4 - Crane moved container 86
Time 2430.018: Vessel 3 - Truck transported container 86 to yard
Time 2430.018: Vessel 3 - Crane moved container 87
Time 2431.617: Vessel 4 - Container 86 loaded onto truck
Time 2433.018: Vessel 3 - Container 87 loaded onto truck
Time 2437.617: Vessel 4 - Truck transported container 86 to yard
Time 2437.617: Vessel 4 - Crane moved container 87
Time 2439.018: Vessel 3 - Truck transported container 87 to yard
Time 2439.018: Vessel 3 - Crane moved container 88
Time 2440.617: Vessel 4 - Container 87 loaded onto truck
Time 2442.018: Vessel 3 - Container 88 loaded onto truck
Time 2446.617: Vessel 4 - Truck transported container 87 to yard
Time 2446.617: Vessel 4 - Crane moved container 88
Time 2448.018: Vessel 3 - Truck transported container 88 to yard
Time 2448.018: Vessel 3 - Crane moved container 89
Time 2449.617: Vessel 4 - Container 88 loaded onto truck
Time 2451.018: Vessel 3 - Container 89 loaded onto truck
Time 2453.436: Vessel 14 Arrived
Time 2453.436: Vessel 14 Waiting for a berth
Time 2455.617: Vessel 4 - Truck transported container 88 to yard
Time 2455.617: Vessel 4 - Crane moved container 89
Time 2457.018: Vessel 3 - Truck transported container 89 to yard
Time 2457.018: Vessel 3 - Crane moved container 90
Time 2458.617: Vessel 4 - Container 89 loaded onto truck
Time 2460.018: Vessel 3 - Container 90 loaded onto truck
Time 2464.617: Vessel 4 - Truck transported container 89 to yard
Time 2464.617: Vessel 4 - Crane moved container 90
Time 2466.018: Vessel 3 - Truck transported container 90 to yard
Time 2466.018: Vessel 3 - Crane moved container 91
Time 2467.617: Vessel 4 - Container 90 loaded onto truck
Time 2469.018: Vessel 3 - Container 91 loaded onto truck
Time 2473.617: Vessel 4 - Truck transported container 90 to yard
Time 2473.617: Vessel 4 - Crane moved container 91
Time 2475.018: Vessel 3 - Truck transported container 91 to yard
Time 2475.018: Vessel 3 - Crane moved container 92
Time 2476.617: Vessel 4 - Container 91 loaded onto truck
Time 2478.018: Vessel 3 - Container 92 loaded onto truck
Time 2482.617: Vessel 4 - Truck transported container 91 to yard
Time 2482.617: Vessel 4 - Crane moved container 92
Time 2484.018: Vessel 3 - Truck transported container 92 to yard
Time 2484.018: Vessel 3 - Crane moved container 93
Time 2485.617: Vessel 4 - Container 92 loaded onto truck
Time 2487.018: Vessel 3 - Container 93 loaded onto truck
Time 2491.617: Vessel 4 - Truck transported container 92 to yard
Time 2491.617: Vessel 4 - Crane moved container 93
Time 2493.018: Vessel 3 - Truck transported container 93 to yard
Time 2493.018: Vessel 3 - Crane moved container 94
Time 2494.617: Vessel 4 - Container 93 loaded onto truck
Time 2496.018: Vessel 3 - Container 94 loaded onto truck
Time 2500.617: Vessel 4 - Truck transported container 93 to yard
Time 2500.617: Vessel 4 - Crane moved container 94
Time 2502.018: Vessel 3 - Truck transported container 94 to yard
Time 2502.018: Vessel 3 - Crane moved container 95
Time 2503.617: Vessel 4 - Container 94 loaded onto truck
Time 2505.018: Vessel 3 - Container 95 loaded onto truck
Time 2509.617: Vessel 4 - Truck transported container 94 to yard
Time 2509.617: Vessel 4 - Crane moved container 95
Time 2511.018: Vessel 3 - Truck transported container 95 to yard
Time 2511.018: Vessel 3 - Crane moved container 96
Time 2512.617: Vessel 4 - Container 95 loaded onto truck
Time 2514.018: Vessel 3 - Container 96 loaded onto truck
Time 2518.617: Vessel 4 - Truck transported container 95 to yard
Time 2518.617: Vessel 4 - Crane moved container 96
Time 2520.018: Vessel 3 - Truck transported container 96 to yard
Time 2520.018: Vessel 3 - Crane moved container 97
Time 2521.617: Vessel 4 - Container 96 loaded onto truck
Time 2523.018: Vessel 3 - Container 97 loaded onto truck
Time 2527.617: Vessel 4 - Truck transported container 96 to yard
Time 2527.617: Vessel 4 - Crane moved container 97
Time 2529.018: Vessel 3 - Truck transported container 97 to yard
Time 2529.018: Vessel 3 - Crane moved container 98
Time 2530.617: Vessel 4 - Container 97 loaded onto truck
Time 2532.018: Vessel 3 - Container 98 loaded onto truck
Time 2536.617: Vessel 4 - Truck transported container 97 to yard
Time 2536.617: Vessel 4 - Crane moved container 98
Time 2538.018: Vessel 3 - Truck transported container 98 to yard
Time 2538.018: Vessel 3 - Crane moved container 99
Time 2539.617: Vessel 4 - Container 98 loaded onto truck
Time 2541.018: Vessel 3 - Container 99 loaded onto truck
Time 2545.617: Vessel 4 - Truck transported container 98 to yard
Time 2545.617: Vessel 4 - Crane moved container 99
Time 2547.018: Vessel 3 - Truck transported container 99 to yard
Time 2547.018: Vessel 3 - Crane moved container 100
Time 2548.617: Vessel 4 - Container 99 loaded onto truck
Time 2550.018: Vessel 3 - Container 100 loaded onto truck
Time 2554.617: Vessel 4 - Truck transported container 99 to yard
Time 2554.617: Vessel 4 - Crane moved container 100
Time 2556.018: Vessel 3 - Truck transported container 100 to yard
Time 2556.018: Vessel 3 - Crane moved container 101
Time 2557.617: Vessel 4 - Container 100 loaded onto truck
Time 2559.018: Vessel 3 - Container 101 loaded onto truck
Time 2563.617: Vessel 4 - Truck transported container 100 to yard
Time 2563.617: Vessel 4 - Crane moved container 101
Time 2565.018: Vessel 3 - Truck transported container 101 to yard
Time 2565.018: Vessel 3 - Crane moved container 102
Time 2566.617: Vessel 4 - Container 101 loaded onto truck
Time 2568.018: Vessel 3 - Container 102 loaded onto truck
Time 2572.617: Vessel 4 - Truck transported container 101 to yard
Time 2572.617: Vessel 4 - Crane moved container 102
Time 2574.018: Vessel 3 - Truck transported container 102 to yard
Time 2574.018: Vessel 3 - Crane moved container 103
Time 2575.617: Vessel 4 - Container 102 loaded onto truck
Time 2577.018: Vessel 3 - Container 103 loaded onto truck
Time 2581.617: Vessel 4 - Truck transported container 102 to yard
Time 2581.617: Vessel 4 - Crane moved container 103
Time 2583.018: Vessel 3 - Truck transported container 103 to yard
Time 2583.018: Vessel 3 - Crane moved container 104
Time 2584.617: Vessel 4 - Container 103 loaded onto truck
Time 2586.018: Vessel 3 - Container 104 loaded onto truck
Time 2590.617: Vessel 4 - Truck transported container 103 to yard
Time 2590.617: Vessel 4 - Crane moved container 104
Time 2592.018: Vessel 3 - Truck transported container 104 to yard
Time 2592.018: Vessel 3 - Crane moved container 105
Time 2593.617: Vessel 4 - Container 104 loaded onto truck
Time 2595.018: Vessel 3 - Container 105 loaded onto truck
Time 2599.617: Vessel 4 - Truck transported container 104 to yard
Time 2599.617: Vessel 4 - Crane moved container 105
Time 2601.018: Vessel 3 - Truck transported container 105 to yard
Time 2601.018: Vessel 3 - Crane moved container 106
Time 2602.617: Vessel 4 - Container 105 loaded onto truck
Time 2604.018: Vessel 3 - Container 106 loaded onto truck
Time 2608.617: Vessel 4 - Truck transported container 105 to yard
Time 2608.617: Vessel 4 - Crane moved container 106
Time 2610.018: Vessel 3 - Truck transported container 106 to yard
Time 2610.018: Vessel 3 - Crane moved container 107
Time 2611.617: Vessel 4 - Container 106 loaded onto truck
Time 2613.018: Vessel 3 - Container 107 loaded onto truck
Time 2617.617: Vessel 4 - Truck transported container 106 to yard
Time 2617.617: Vessel 4 - Crane moved container 107
Time 2619.018: Vessel 3 - Truck transported container 107 to yard
Time 2619.018: Vessel 3 - Crane moved container 108
Time 2620.617: Vessel 4 - Container 107 loaded onto truck
Time 2622.018: Vessel 3 - Container 108 loaded onto truck
Time 2626.617: Vessel 4 - Truck transported container 107 to yard
Time 2626.617: Vessel 4 - Crane moved container 108
Time 2628.018: Vessel 3 - Truck transported container 108 to yard
Time 2628.018: Vessel 3 - Crane moved container 109
Time 2629.617: Vessel 4 - Container 108 loaded onto truck
Time 2631.018: Vessel 3 - Container 109 loaded onto truck
Time 2635.617: Vessel 4 - Truck transported container 108 to yard
Time 2635.617: Vessel 4 - Crane moved container 109
Time 2637.018: Vessel 3 - Truck transported container 109 to yard
Time 2637.018: Vessel 3 - Crane moved container 110
Time 2638.617: Vessel 4 - Container 109 loaded onto truck
Time 2640.018: Vessel 3 - Container 110 loaded onto truck
Time 2644.617: Vessel 4 - Truck transported container 109 to yard
Time 2644.617: Vessel 4 - Crane moved container 110
Time 2646.018: Vessel 3 - Truck transported container 110 to yard
Time 2646.018: Vessel 3 - Crane moved container 111
Time 2647.617: Vessel 4 - Container 110 loaded onto truck
Time 2649.018: Vessel 3 - Container 111 loaded onto truck
Time 2653.617: Vessel 4 - Truck transported container 110 to yard
Time 2653.617: Vessel 4 - Crane moved container 111
Time 2655.018: Vessel 3 - Truck transported container 111 to yard
Time 2655.018: Vessel 3 - Crane moved container 112
Time 2656.617: Vessel 4 - Container 111 loaded onto truck
Time 2658.018: Vessel 3 - Container 112 loaded onto truck
Time 2662.617: Vessel 4 - Truck transported container 111 to yard
Time 2662.617: Vessel 4 - Crane moved container 112
Time 2664.018: Vessel 3 - Truck transported container 112 to yard
Time 2664.018: Vessel 3 - Crane moved container 113
Time 2665.617: Vessel 4 - Container 112 loaded onto truck
Time 2667.018: Vessel 3 - Container 113 loaded onto truck
Time 2671.617: Vessel 4 - Truck transported container 112 to yard
Time 2671.617: Vessel 4 - Crane moved container 113
Time 2673.018: Vessel 3 - Truck transported container 113 to yard
Time 2673.018: Vessel 3 - Crane moved container 114
Time 2674.617: Vessel 4 - Container 113 loaded onto truck
Time 2676.018: Vessel 3 - Container 114 loaded onto truck
Time 2680.617: Vessel 4 - Truck transported container 113 to yard
Time 2680.617: Vessel 4 - Crane moved container 114
Time 2682.018: Vessel 3 - Truck transported container 114 to yard
Time 2682.018: Vessel 3 - Crane moved container 115
Time 2683.617: Vessel 4 - Container 114 loaded onto truck
Time 2685.018: Vessel 3 - Container 115 loaded onto truck
Time 2689.617: Vessel 4 - Truck transported container 114 to yard
Time 2689.617: Vessel 4 - Crane moved container 115
Time 2691.018: Vessel 3 - Truck transported container 115 to yard
Time 2691.018: Vessel 3 - Crane moved container 116
Time 2692.617: Vessel 4 - Container 115 loaded onto truck
Time 2694.018: Vessel 3 - Container 116 loaded onto truck
Time 2698.617: Vessel 4 - Truck transported container 115 to yard
Time 2698.617: Vessel 4 - Crane moved container 116
Time 2700.018: Vessel 3 - Truck transported container 116 to yard
Time 2700.018: Vessel 3 - Crane moved container 117
Time 2701.617: Vessel 4 - Container 116 loaded onto truck
Time 2703.018: Vessel 3 - Container 117 loaded onto truck
Time 2707.617: Vessel 4 - Truck transported container 116 to yard
Time 2707.617: Vessel 4 - Crane moved container 117
Time 2709.018: Vessel 3 - Truck transported container 117 to yard
Time 2709.018: Vessel 3 - Crane moved container 118
Time 2710.617: Vessel 4 - Container 117 loaded onto truck
Time 2712.018: Vessel 3 - Container 118 loaded onto truck
Time 2716.617: Vessel 4 - Truck transported container 117 to yard
Time 2716.617: Vessel 4 - Crane moved container 118
Time 2718.018: Vessel 3 - Truck transported container 118 to yard
Time 2718.018: Vessel 3 - Crane moved container 119
Time 2719.617: Vessel 4 - Container 118 loaded onto truck
Time 2721.018: Vessel 3 - Container 119 loaded onto truck
Time 2725.617: Vessel 4 - Truck transported container 118 to yard
Time 2725.617: Vessel 4 - Crane moved container 119
Time 2727.018: Vessel 3 - Truck transported container 119 to yard
Time 2727.018: Vessel 3 - Crane moved container 120
Time 2728.617: Vessel 4 - Container 119 loaded onto truck
Time 2730.018: Vessel 3 - Container 120 loaded onto truck
Time 2734.617: Vessel 4 - Truck transported container 119 to yard
Time 2734.617: Vessel 4 - Crane moved container 120
Time 2736.018: Vessel 3 - Truck transported container 120 to yard
Time 2736.018: Vessel 3 - Crane moved container 121
Time 2737.617: Vessel 4 - Container 120 loaded onto truck
Time 2739.018: Vessel 3 - Container 121 loaded onto truck
Time 2743.617: Vessel 4 - Truck transported container 120 to yard
Time 2743.617: Vessel 4 - Crane moved container 121
Time 2745.018: Vessel 3 - Truck transported container 121 to yard
Time 2745.018: Vessel 3 - Crane moved container 122
Time 2746.617: Vessel 4 - Container 121 loaded onto truck
Time 2748.018: Vessel 3 - Container 122 loaded onto truck
Time 2752.617: Vessel 4 - Truck transported container 121 to yard
Time 2752.617: Vessel 4 - Crane moved container 122
Time 2754.018: Vessel 3 - Truck transported container 122 to yard
Time 2754.018: Vessel 3 - Crane moved container 123
Time 2755.617: Vessel 4 - Container 122 loaded onto truck
Time 2757.018: Vessel 3 - Container 123 loaded onto truck
Time 2761.617: Vessel 4 - Truck transported container 122 to yard
Time 2761.617: Vessel 4 - Crane moved container 123
Time 2763.018: Vessel 3 - Truck transported container 123 to yard
Time 2763.018: Vessel 3 - Crane moved container 124
Time 2764.617: Vessel 4 - Container 123 loaded onto truck
Time 2766.018: Vessel 3 - Container 124 loaded onto truck
Time 2768.284: Vessel 15 Arrived
Time 2768.284: Vessel 15 Waiting for a berth
Time 2770.617: Vessel 4 - Truck transported container 123 to yard
Time 2770.617: Vessel 4 - Crane moved container 124
Time 2772.018: Vessel 3 - Truck transported container 124 to yard
Time 2772.018: Vessel 3 - Crane moved container 125
Time 2773.617: Vessel 4 - Container 124 loaded onto truck
Time 2775.018: Vessel 3 - Container 125 loaded onto truck
Time 2779.617: Vessel 4 - Truck transported container 124 to yard
Time 2779.617: Vessel 4 - Crane moved container 125
Time 2781.018: Vessel 3 - Truck transported container 125 to yard
Time 2781.018: Vessel 3 - Crane moved container 126
Time 2782.617: Vessel 4 - Container 125 loaded onto truck
Time 2784.018: Vessel 3 - Container 126 loaded onto truck
Time 2788.617: Vessel 4 - Truck transported container 125 to yard
Time 2788.617: Vessel 4 - Crane moved container 126
Time 2790.018: Vessel 3 - Truck transported container 126 to yard
Time 2790.018: Vessel 3 - Crane moved container 127
Time 2791.617: Vessel 4 - Container 126 loaded onto truck
Time 2793.018: Vessel 3 - Container 127 loaded onto truck
Time 2797.617: Vessel 4 - Truck transported container 126 to yard
Time 2797.617: Vessel 4 - Crane moved container 127
Time 2799.018: Vessel 3 - Truck transported container 127 to yard
Time 2799.018: Vessel 3 - Crane moved container 128
Time 2800.617: Vessel 4 - Container 127 loaded onto truck
Time 2802.018: Vessel 3 - Container 128 loaded onto truck
Time 2806.617: Vessel 4 - Truck transported container 127 to yard
Time 2806.617: Vessel 4 - Crane moved container 128
Time 2808.018: Vessel 3 - Truck transported container 128 to yard
Time 2808.018: Vessel 3 - Crane moved container 129
Time 2809.617: Vessel 4 - Container 128 loaded onto truck
Time 2811.018: Vessel 3 - Container 129 loaded onto truck
Time 2815.617: Vessel 4 - Truck transported container 128 to yard
Time 2815.617: Vessel 4 - Crane moved container 129
Time 2817.018: Vessel 3 - Truck transported container 129 to yard
Time 2817.018: Vessel 3 - Crane moved container 130
Time 2818.617: Vessel 4 - Container 129 loaded onto truck
Time 2820.018: Vessel 3 - Container 130 loaded onto truck
Time 2824.617: Vessel 4 - Truck transported container 129 to yard
Time 2824.617: Vessel 4 - Crane moved container 130
Time 2826.018: Vessel 3 - Truck transported container 130 to yard
Time 2826.018: Vessel 3 - Crane moved container 131
Time 2827.617: Vessel 4 - Container 130 loaded onto truck
Time 2829.018: Vessel 3 - Container 131 loaded onto truck
Time 2833.617: Vessel 4 - Truck transported container 130 to yard
Time 2833.617: Vessel 4 - Crane moved container 131
Time 2835.018: Vessel 3 - Truck transported container 131 to yard
Time 2835.018: Vessel 3 - Crane moved container 132
Time 2836.617: Vessel 4 - Container 131 loaded onto truck
Time 2838.018: Vessel 3 - Container 132 loaded onto truck
Time 2842.617: Vessel 4 - Truck transported container 131 to yard
Time 2842.617: Vessel 4 - Crane moved container 132
Time 2844.018: Vessel 3 - Truck transported container 132 to yard
Time 2844.018: Vessel 3 - Crane moved container 133
Time 2845.617: Vessel 4 - Container 132 loaded onto truck
Time 2847.018: Vessel 3 - Container 133 loaded onto truck
Time 2851.617: Vessel 4 - Truck transported container 132 to yard
Time 2851.617: Vessel 4 - Crane moved container 133
Time 2853.018: Vessel 3 - Truck transported container 133 to yard
Time 2853.018: Vessel 3 - Crane moved container 134
Time 2854.617: Vessel 4 - Container 133 loaded onto truck
Time 2856.018: Vessel 3 - Container 134 loaded onto truck
Time 2860.617: Vessel 4 - Truck transported container 133 to yard
Time 2860.617: Vessel 4 - Crane moved container 134
Time 2862.018: Vessel 3 - Truck transported container 134 to yard
Time 2862.018: Vessel 3 - Crane moved container 135
Time 2863.617: Vessel 4 - Container 134 loaded onto truck
Time 2865.018: Vessel 3 - Container 135 loaded onto truck
Time 2869.617: Vessel 4 - Truck transported container 134 to yard
Time 2869.617: Vessel 4 - Crane moved container 135
Time 2871.018: Vessel 3 - Truck transported container 135 to yard
Time 2871.018: Vessel 3 - Crane moved container 136
Time 2872.617: Vessel 4 - Container 135 loaded onto truck
Time 2874.018: Vessel 3 - Container 136 loaded onto truck
Time 2878.617: Vessel 4 - Truck transported container 135 to yard
Time 2878.617: Vessel 4 - Crane moved container 136
Time 2880.018: Vessel 3 - Truck transported container 136 to yard
Time 2880.018: Vessel 3 - Crane moved container 137
Time 2881.617: Vessel 4 - Container 136 loaded onto truck
Time 2883.018: Vessel 3 - Container 137 loaded onto truck
Time 2887.617: Vessel 4 - Truck transported container 136 to yard
Time 2887.617: Vessel 4 - Crane moved container 137
Time 2889.018: Vessel 3 - Truck transported container 137 to yard
Time 2889.018: Vessel 3 - Crane moved container 138
Time 2890.617: Vessel 4 - Container 137 loaded onto truck
Time 2892.018: Vessel 3 - Container 138 loaded onto truck
Time 2896.617: Vessel 4 - Truck transported container 137 to yard
Time 2896.617: Vessel 4 - Crane moved container 138
Time 2898.018: Vessel 3 - Truck transported container 138 to yard
Time 2898.018: Vessel 3 - Crane moved container 139
Time 2899.617: Vessel 4 - Container 138 loaded onto truck
Time 2901.018: Vessel 3 - Container 139 loaded onto truck
Time 2905.617: Vessel 4 - Truck transported container 138 to yard
Time 2905.617: Vessel 4 - Crane moved container 139
Time 2907.018: Vessel 3 - Truck transported container 139 to yard
Time 2907.018: Vessel 3 - Crane moved container 140
Time 2908.617: Vessel 4 - Container 139 loaded onto truck
Time 2910.018: Vessel 3 - Container 140 loaded onto truck
Time 2914.617: Vessel 4 - Truck transported container 139 to yard
Time 2914.617: Vessel 4 - Crane moved container 140
Time 2916.018: Vessel 3 - Truck transported container 140 to yard
Time 2916.018: Vessel 3 - Crane moved container 141
Time 2917.617: Vessel 4 - Container 140 loaded onto truck
Time 2919.018: Vessel 3 - Container 141 loaded onto truck
Time 2923.617: Vessel 4 - Truck transported container 140 to yard
Time 2923.617: Vessel 4 - Crane moved container 141
Time 2925.018: Vessel 3 - Truck transported container 141 to yard
Time 2925.018: Vessel 3 - Crane moved container 142
Time 2926.617: Vessel 4 - Container 141 loaded onto truck
Time 2928.018: Vessel 3 - Container 142 loaded onto truck
Time 2932.617: Vessel 4 - Truck transported container 141 to yard
Time 2932.617: Vessel 4 - Crane moved container 142
Time 2934.018: Vessel 3 - Truck transported container 142 to yard
Time 2934.018: Vessel 3 - Crane moved container 143
Time 2935.617: Vessel 4 - Container 142 loaded onto truck
Time 2937.018: Vessel 3 - Container 143 loaded onto truck
Time 2941.617: Vessel 4 - Truck transported container 142 to yard
Time 2941.617: Vessel 4 - Crane moved container 143
Time 2943.018: Vessel 3 - Truck transported container 143 to yard
Time 2943.018: Vessel 3 - Crane moved container 144
Time 2944.617: Vessel 4 - Container 143 loaded onto truck
Time 2946.018: Vessel 3 - Container 144 loaded onto truck
Time 2950.617: Vessel 4 - Truck transported container 143 to yard
Time 2950.617: Vessel 4 - Crane moved container 144
Time 2952.018: Vessel 3 - Truck transported container 144 to yard
Time 2952.018: Vessel 3 - Crane moved container 145
Time 2953.617: Vessel 4 - Container 144 loaded onto truck
Time 2955.018: Vessel 3 - Container 145 loaded onto truck
Time 2959.617: Vessel 4 - Truck transported container 144 to yard
Time 2959.617: Vessel 4 - Crane moved container 145
Time 2961.018: Vessel 3 - Truck transported container 145 to yard
Time 2961.018: Vessel 3 - Crane moved container 146
Time 2962.617: Vessel 4 - Container 145 loaded onto truck
Time 2964.018: Vessel 3 - Container 146 loaded onto truck
Time 2968.617: Vessel 4 - Truck transported container 145 to yard
Time 2968.617: Vessel 4 - Crane moved container 146
Time 2970.018: Vessel 3 - Truck transported container 146 to yard
Time 2970.018: Vessel 3 - Crane moved container 147
Time 2971.617: Vessel 4 - Container 146 loaded onto truck
Time 2973.018: Vessel 3 - Container 147 loaded onto truck
Time 2977.617: Vessel 4 - Truck transported container 146 to yard
Time 2977.617: Vessel 4 - Crane moved container 147
Time 2979.018: Vessel 3 - Truck transported container 147 to yard
Time 2979.018: Vessel 3 - Crane moved container 148
Time 2980.617: Vessel 4 - Container 147 loaded onto truck
Time 2982.018: Vessel 3 - Container 148 loaded onto truck
Time 2986.617: Vessel 4 - Truck transported container 147 to yard
Time 2986.617: Vessel 4 - Crane moved container 148
Time 2988.018: Vessel 3 - Truck transported container 148 to yard
Time 2988.018: Vessel 3 - Crane moved container 149
Time 2989.617: Vessel 4 - Container 148 loaded onto truck
Time 2991.018: Vessel 3 - Container 149 loaded onto truck
Time 2995.617: Vessel 4 - Truck transported container 148 to yard
Time 2995.617: Vessel 4 - Crane moved container 149
Time 2997.018: Vessel 3 - Truck transported container 149 to yard
Time 2997.018: Vessel 3 - Crane moved container 150
Time 2998.617: Vessel 4 - Container 149 loaded onto truck
Time 3000.018: Vessel 3 - Container 150 loaded onto truck
Time 3004.482: Vessel 16 Arrived
Time 3004.482: Vessel 16 Waiting for a berth
Time 3004.617: Vessel 4 - Truck transported container 149 to yard
Time 3004.617: Vessel 4 - Crane moved container 150
Time 3006.018: Vessel 3 - Truck transported container 150 to yard
Time 3006.018: Vessel 3 finished unloading and leaves
Time 3006.018: Vessel 5 berthed
Time 3006.018: Vessel 5 - Crane allocated
Time 3006.018: Vessel 5 - Crane moved container 1
Time 3007.617: Vessel 4 - Container 150 loaded onto truck
Time 3009.018: Vessel 5 - Container 1 loaded onto truck
Time 3013.617: Vessel 4 - Truck transported container 150 to yard
Time 3013.617: Vessel 4 finished unloading and leaves
Time 3013.617: Vessel 6 berthed
Time 3013.617: Vessel 6 - Crane allocated
Time 3013.617: Vessel 6 - Crane moved container 1
Time 3015.018: Vessel 5 - Truck transported container 1 to yard
Time 3015.018: Vessel 5 - Crane moved container 2
Time 3016.617: Vessel 6 - Container 1 loaded onto truck
Time 3018.018: Vessel 5 - Container 2 loaded onto truck
Time 3022.617: Vessel 6 - Truck transported container 1 to yard
Time 3022.617: Vessel 6 - Crane moved container 2
Time 3024.018: Vessel 5 - Truck transported container 2 to yard
Time 3024.018: Vessel 5 - Crane moved container 3
Time 3025.617: Vessel 6 - Container 2 loaded onto truck
Time 3027.018: Vessel 5 - Container 3 loaded onto truck
Time 3031.617: Vessel 6 - Truck transported container 2 to yard
Time 3031.617: Vessel 6 - Crane moved container 3
Time 3033.018: Vessel 5 - Truck transported container 3 to yard
Time 3033.018: Vessel 5 - Crane moved container 4
Time 3034.617: Vessel 6 - Container 3 loaded onto truck
Time 3036.018: Vessel 5 - Container 4 loaded onto truck
Time 3040.617: Vessel 6 - Truck transported container 3 to yard
Time 3040.617: Vessel 6 - Crane moved container 4
Time 3042.018: Vessel 5 - Truck transported container 4 to yard
Time 3042.018: Vessel 5 - Crane moved container 5
Time 3043.617: Vessel 6 - Container 4 loaded onto truck
Time 3045.018: Vessel 5 - Container 5 loaded onto truck
Time 3049.617: Vessel 6 - Truck transported container 4 to yard
Time 3049.617: Vessel 6 - Crane moved container 5
Time 3051.018: Vessel 5 - Truck transported container 5 to yard
Time 3051.018: Vessel 5 - Crane moved container 6
Time 3052.617: Vessel 6 - Container 5 loaded onto truck
Time 3054.018: Vessel 5 - Container 6 loaded onto truck
Time 3058.617: Vessel 6 - Truck transported container 5 to yard
Time 3058.617: Vessel 6 - Crane moved container 6
Time 3060.018: Vessel 5 - Truck transported container 6 to yard
Time 3060.018: Vessel 5 - Crane moved container 7
Time 3061.617: Vessel 6 - Container 6 loaded onto truck
Time 3063.018: Vessel 5 - Container 7 loaded onto truck
Time 3067.617: Vessel 6 - Truck transported container 6 to yard
Time 3067.617: Vessel 6 - Crane moved container 7
Time 3069.018: Vessel 5 - Truck transported container 7 to yard
Time 3069.018: Vessel 5 - Crane moved container 8
Time 3070.617: Vessel 6 - Container 7 loaded onto truck
Time 3072.018: Vessel 5 - Container 8 loaded onto truck
Time 3076.617: Vessel 6 - Truck transported container 7 to yard
Time 3076.617: Vessel 6 - Crane moved container 8
Time 3078.018: Vessel 5 - Truck transported container 8 to yard
Time 3078.018: Vessel 5 - Crane moved container 9
Time 3079.190: Vessel 17 Arrived
Time 3079.190: Vessel 17 Waiting for a berth
Time 3079.617: Vessel 6 - Container 8 loaded onto truck
Time 3081.018: Vessel 5 - Container 9 loaded onto truck
Time 3085.617: Vessel 6 - Truck transported container 8 to yard
Time 3085.617: Vessel 6 - Crane moved container 9
Time 3087.018: Vessel 5 - Truck transported container 9 to yard
Time 3087.018: Vessel 5 - Crane moved container 10
Time 3088.617: Vessel 6 - Container 9 loaded onto truck
Time 3090.018: Vessel 5 - Container 10 loaded onto truck
Time 3094.617: Vessel 6 - Truck transported container 9 to yard
Time 3094.617: Vessel 6 - Crane moved container 10
Time 3096.018: Vessel 5 - Truck transported container 10 to yard
Time 3096.018: Vessel 5 - Crane moved container 11
Time 3097.617: Vessel 6 - Container 10 loaded onto truck
Time 3099.018: Vessel 5 - Container 11 loaded onto truck
Time 3103.617: Vessel 6 - Truck transported container 10 to yard
Time 3103.617: Vessel 6 - Crane moved container 11
Time 3105.018: Vessel 5 - Truck transported container 11 to yard
Time 3105.018: Vessel 5 - Crane moved container 12
Time 3106.617: Vessel 6 - Container 11 loaded onto truck
Time 3108.018: Vessel 5 - Container 12 loaded onto truck
Time 3112.617: Vessel 6 - Truck transported container 11 to yard
Time 3112.617: Vessel 6 - Crane moved container 12
Time 3114.018: Vessel 5 - Truck transported container 12 to yard
Time 3114.018: Vessel 5 - Crane moved container 13
Time 3115.617: Vessel 6 - Container 12 loaded onto truck
Time 3117.018: Vessel 5 - Container 13 loaded onto truck
Time 3121.617: Vessel 6 - Truck transported container 12 to yard
Time 3121.617: Vessel 6 - Crane moved container 13
Time 3123.018: Vessel 5 - Truck transported container 13 to yard
Time 3123.018: Vessel 5 - Crane moved container 14
Time 3124.617: Vessel 6 - Container 13 loaded onto truck
Time 3126.018: Vessel 5 - Container 14 loaded onto truck
Time 3130.617: Vessel 6 - Truck transported container 13 to yard
Time 3130.617: Vessel 6 - Crane moved container 14
Time 3132.018: Vessel 5 - Truck transported container 14 to yard
Time 3132.018: Vessel 5 - Crane moved container 15
Time 3133.617: Vessel 6 - Container 14 loaded onto truck
Time 3135.018: Vessel 5 - Container 15 loaded onto truck
Time 3139.617: Vessel 6 - Truck transported container 14 to yard
Time 3139.617: Vessel 6 - Crane moved container 15
Time 3141.018: Vessel 5 - Truck transported container 15 to yard
Time 3141.018: Vessel 5 - Crane moved container 16
Time 3142.617: Vessel 6 - Container 15 loaded onto truck
Time 3144.018: Vessel 5 - Container 16 loaded onto truck
Time 3148.617: Vessel 6 - Truck transported container 15 to yard
Time 3148.617: Vessel 6 - Crane moved container 16
Time 3150.018: Vessel 5 - Truck transported container 16 to yard
Time 3150.018: Vessel 5 - Crane moved container 17
Time 3151.617: Vessel 6 - Container 16 loaded onto truck
Time 3153.018: Vessel 5 - Container 17 loaded onto truck
Time 3157.617: Vessel 6 - Truck transported container 16 to yard
Time 3157.617: Vessel 6 - Crane moved container 17
Time 3159.018: Vessel 5 - Truck transported container 17 to yard
Time 3159.018: Vessel 5 - Crane moved container 18
Time 3160.617: Vessel 6 - Container 17 loaded onto truck
Time 3162.018: Vessel 5 - Container 18 loaded onto truck
Time 3166.617: Vessel 6 - Truck transported container 17 to yard
Time 3166.617: Vessel 6 - Crane moved container 18
Time 3168.018: Vessel 5 - Truck transported container 18 to yard
Time 3168.018: Vessel 5 - Crane moved container 19
Time 3169.617: Vessel 6 - Container 18 loaded onto truck
Time 3171.018: Vessel 5 - Container 19 loaded onto truck
Time 3175.617: Vessel 6 - Truck transported container 18 to yard
Time 3175.617: Vessel 6 - Crane moved container 19
Time 3177.018: Vessel 5 - Truck transported container 19 to yard
Time 3177.018: Vessel 5 - Crane moved container 20
Time 3178.617: Vessel 6 - Container 19 loaded onto truck
Time 3180.018: Vessel 5 - Container 20 loaded onto truck
Time 3184.617: Vessel 6 - Truck transported container 19 to yard
Time 3184.617: Vessel 6 - Crane moved container 20
Time 3186.018: Vessel 5 - Truck transported container 20 to yard
Time 3186.018: Vessel 5 - Crane moved container 21
Time 3187.617: Vessel 6 - Container 20 loaded onto truck
Time 3189.018: Vessel 5 - Container 21 loaded onto truck
Time 3193.617: Vessel 6 - Truck transported container 20 to yard
Time 3193.617: Vessel 6 - Crane moved container 21
Time 3195.018: Vessel 5 - Truck transported container 21 to yard
Time 3195.018: Vessel 5 - Crane moved container 22
Time 3196.617: Vessel 6 - Container 21 loaded onto truck
Time 3198.018: Vessel 5 - Container 22 loaded onto truck
Time 3202.617: Vessel 6 - Truck transported container 21 to yard
Time 3202.617: Vessel 6 - Crane moved container 22
Time 3204.018: Vessel 5 - Truck transported container 22 to yard
Time 3204.018: Vessel 5 - Crane moved container 23
Time 3205.617: Vessel 6 - Container 22 loaded onto truck
Time 3207.018: Vessel 5 - Container 23 loaded onto truck
Time 3211.617: Vessel 6 - Truck transported container 22 to yard
Time 3211.617: Vessel 6 - Crane moved container 23
Time 3213.018: Vessel 5 - Truck transported container 23 to yard
Time 3213.018: Vessel 5 - Crane moved container 24
Time 3214.617: Vessel 6 - Container 23 loaded onto truck
Time 3216.018: Vessel 5 - Container 24 loaded onto truck
Time 3220.617: Vessel 6 - Truck transported container 23 to yard
Time 3220.617: Vessel 6 - Crane moved container 24
Time 3222.018: Vessel 5 - Truck transported container 24 to yard
Time 3222.018: Vessel 5 - Crane moved container 25
Time 3223.617: Vessel 6 - Container 24 loaded onto truck
Time 3225.018: Vessel 5 - Container 25 loaded onto truck
Time 3229.617: Vessel 6 - Truck transported container 24 to yard
Time 3229.617: Vessel 6 - Crane moved container 25
Time 3231.018: Vessel 5 - Truck transported container 25 to yard
Time 3231.018: Vessel 5 - Crane moved container 26
Time 3232.617: Vessel 6 - Container 25 loaded onto truck
Time 3234.018: Vessel 5 - Container 26 loaded onto truck
Time 3238.617: Vessel 6 - Truck transported container 25 to yard
Time 3238.617: Vessel 6 - Crane moved container 26
Time 3240.018: Vessel 5 - Truck transported container 26 to yard
Time 3240.018: Vessel 5 - Crane moved container 27
Time 3241.617: Vessel 6 - Container 26 loaded onto truck
Time 3243.018: Vessel 5 - Container 27 loaded onto truck
Time 3247.617: Vessel 6 - Truck transported container 26 to yard
Time 3247.617: Vessel 6 - Crane moved container 27
Time 3249.018: Vessel 5 - Truck transported container 27 to yard
Time 3249.018: Vessel 5 - Crane moved container 28
Time 3250.617: Vessel 6 - Container 27 loaded onto truck
Time 3252.018: Vessel 5 - Container 28 loaded onto truck
Time 3256.617: Vessel 6 - Truck transported container 27 to yard
Time 3256.617: Vessel 6 - Crane moved container 28
Time 3258.018: Vessel 5 - Truck transported container 28 to yard
Time 3258.018: Vessel 5 - Crane moved container 29
Time 3259.617: Vessel 6 - Container 28 loaded onto truck
Time 3261.018: Vessel 5 - Container 29 loaded onto truck
Time 3265.617: Vessel 6 - Truck transported container 28 to yard
Time 3265.617: Vessel 6 - Crane moved container 29
Time 3267.018: Vessel 5 - Truck transported container 29 to yard
Time 3267.018: Vessel 5 - Crane moved container 30
Time 3268.617: Vessel 6 - Container 29 loaded onto truck
Time 3270.018: Vessel 5 - Container 30 loaded onto truck
Time 3274.617: Vessel 6 - Truck transported container 29 to yard
Time 3274.617: Vessel 6 - Crane moved container 30
Time 3276.018: Vessel 5 - Truck transported container 30 to yard
Time 3276.018: Vessel 5 - Crane moved container 31
Time 3277.617: Vessel 6 - Container 30 loaded onto truck
Time 3279.018: Vessel 5 - Container 31 loaded onto truck
Time 3283.617: Vessel 6 - Truck transported container 30 to yard
Time 3283.617: Vessel 6 - Crane moved container 31
Time 3285.018: Vessel 5 - Truck transported container 31 to yard
Time 3285.018: Vessel 5 - Crane moved container 32
Time 3286.617: Vessel 6 - Container 31 loaded onto truck
Time 3288.018: Vessel 5 - Container 32 loaded onto truck
Time 3292.617: Vessel 6 - Truck transported container 31 to yard
Time 3292.617: Vessel 6 - Crane moved container 32
Time 3294.018: Vessel 5 - Truck transported container 32 to yard
Time 3294.018: Vessel 5 - Crane moved container 33
Time 3295.617: Vessel 6 - Container 32 loaded onto truck
Time 3297.018: Vessel 5 - Container 33 loaded onto truck
Time 3301.617: Vessel 6 - Truck transported container 32 to yard
Time 3301.617: Vessel 6 - Crane moved container 33
Time 3303.018: Vessel 5 - Truck transported container 33 to yard
Time 3303.018: Vessel 5 - Crane moved container 34
Time 3304.617: Vessel 6 - Container 33 loaded onto truck
Time 3306.018: Vessel 5 - Container 34 loaded onto truck
Time 3310.617: Vessel 6 - Truck transported container 33 to yard
Time 3310.617: Vessel 6 - Crane moved container 34
Time 3312.018: Vessel 5 - Truck transported container 34 to yard
Time 3312.018: Vessel 5 - Crane moved container 35
Time 3313.617: Vessel 6 - Container 34 loaded onto truck
Time 3315.018: Vessel 5 - Container 35 loaded onto truck
Time 3319.617: Vessel 6 - Truck transported container 34 to yard
Time 3319.617: Vessel 6 - Crane moved container 35
Time 3321.018: Vessel 5 - Truck transported container 35 to yard
Time 3321.018: Vessel 5 - Crane moved container 36
Time 3322.617: Vessel 6 - Container 35 loaded onto truck
Time 3324.018: Vessel 5 - Container 36 loaded onto truck
Time 3328.617: Vessel 6 - Truck transported container 35 to yard
Time 3328.617: Vessel 6 - Crane moved container 36
Time 3330.018: Vessel 5 - Truck transported container 36 to yard
Time 3330.018: Vessel 5 - Crane moved container 37
Time 3331.617: Vessel 6 - Container 36 loaded onto truck
Time 3333.018: Vessel 5 - Container 37 loaded onto truck
Time 3337.617: Vessel 6 - Truck transported container 36 to yard
Time 3337.617: Vessel 6 - Crane moved container 37
Time 3339.018: Vessel 5 - Truck transported container 37 to yard
Time 3339.018: Vessel 5 - Crane moved container 38
Time 3340.617: Vessel 6 - Container 37 loaded onto truck
Time 3342.018: Vessel 5 - Container 38 loaded onto truck
Time 3346.133: Vessel 18 Arrived
Time 3346.133: Vessel 18 Waiting for a berth
Time 3346.617: Vessel 6 - Truck transported container 37 to yard
Time 3346.617: Vessel 6 - Crane moved container 38
Time 3348.018: Vessel 5 - Truck transported container 38 to yard
Time 3348.018: Vessel 5 - Crane moved container 39
Time 3349.617: Vessel 6 - Container 38 loaded onto truck
Time 3351.018: Vessel 5 - Container 39 loaded onto truck
Time 3355.617: Vessel 6 - Truck transported container 38 to yard
Time 3355.617: Vessel 6 - Crane moved container 39
Time 3357.018: Vessel 5 - Truck transported container 39 to yard
Time 3357.018: Vessel 5 - Crane moved container 40
Time 3358.617: Vessel 6 - Container 39 loaded onto truck
Time 3360.018: Vessel 5 - Container 40 loaded onto truck
Time 3364.617: Vessel 6 - Truck transported container 39 to yard
Time 3364.617: Vessel 6 - Crane moved container 40
Time 3366.018: Vessel 5 - Truck transported container 40 to yard
Time 3366.018: Vessel 5 - Crane moved container 41
Time 3367.617: Vessel 6 - Container 40 loaded onto truck
Time 3369.018: Vessel 5 - Container 41 loaded onto truck
Time 3373.617: Vessel 6 - Truck transported container 40 to yard
Time 3373.617: Vessel 6 - Crane moved container 41
Time 3375.018: Vessel 5 - Truck transported container 41 to yard
Time 3375.018: Vessel 5 - Crane moved container 42
Time 3376.617: Vessel 6 - Container 41 loaded onto truck
Time 3378.018: Vessel 5 - Container 42 loaded onto truck
Time 3382.617: Vessel 6 - Truck transported container 41 to yard
Time 3382.617: Vessel 6 - Crane moved container 42
Time 3384.018: Vessel 5 - Truck transported container 42 to yard
Time 3384.018: Vessel 5 - Crane moved container 43
Time 3385.617: Vessel 6 - Container 42 loaded onto truck
Time 3387.018: Vessel 5 - Container 43 loaded onto truck
Time 3391.617: Vessel 6 - Truck transported container 42 to yard
Time 3391.617: Vessel 6 - Crane moved container 43
Time 3393.018: Vessel 5 - Truck transported container 43 to yard
Time 3393.018: Vessel 5 - Crane moved container 44
Time 3394.617: Vessel 6 - Container 43 loaded onto truck
Time 3396.018: Vessel 5 - Container 44 loaded onto truck
Time 3400.617: Vessel 6 - Truck transported container 43 to yard
Time 3400.617: Vessel 6 - Crane moved container 44
Time 3402.018: Vessel 5 - Truck transported container 44 to yard
Time 3402.018: Vessel 5 - Crane moved container 45
Time 3403.617: Vessel 6 - Container 44 loaded onto truck
Time 3405.018: Vessel 5 - Container 45 loaded onto truck
Time 3409.617: Vessel 6 - Truck transported container 44 to yard
Time 3409.617: Vessel 6 - Crane moved container 45
Time 3411.018: Vessel 5 - Truck transported container 45 to yard
Time 3411.018: Vessel 5 - Crane moved container 46
Time 3412.617: Vessel 6 - Container 45 loaded onto truck
Time 3414.018: Vessel 5 - Container 46 loaded onto truck
Time 3418.617: Vessel 6 - Truck transported container 45 to yard
Time 3418.617: Vessel 6 - Crane moved container 46
Time 3420.018: Vessel 5 - Truck transported container 46 to yard
Time 3420.018: Vessel 5 - Crane moved container 47
Time 3421.617: Vessel 6 - Container 46 loaded onto truck
Time 3423.018: Vessel 5 - Container 47 loaded onto truck
Time 3427.617: Vessel 6 - Truck transported container 46 to yard
Time 3427.617: Vessel 6 - Crane moved container 47
Time 3429.018: Vessel 5 - Truck transported container 47 to yard
Time 3429.018: Vessel 5 - Crane moved container 48
Time 3430.617: Vessel 6 - Container 47 loaded onto truck
Time 3432.018: Vessel 5 - Container 48 loaded onto truck
Time 3436.617: Vessel 6 - Truck transported container 47 to yard
Time 3436.617: Vessel 6 - Crane moved container 48
Time 3438.018: Vessel 5 - Truck transported container 48 to yard
Time 3438.018: Vessel 5 - Crane moved container 49
Time 3439.617: Vessel 6 - Container 48 loaded onto truck
Time 3441.018: Vessel 5 - Container 49 loaded onto truck
Time 3445.617: Vessel 6 - Truck transported container 48 to yard
Time 3445.617: Vessel 6 - Crane moved container 49
Time 3447.018: Vessel 5 - Truck transported container 49 to yard
Time 3447.018: Vessel 5 - Crane moved container 50
Time 3448.617: Vessel 6 - Container 49 loaded onto truck
Time 3450.018: Vessel 5 - Container 50 loaded onto truck
Time 3454.617: Vessel 6 - Truck transported container 49 to yard
Time 3454.617: Vessel 6 - Crane moved container 50
Time 3456.018: Vessel 5 - Truck transported container 50 to yard
Time 3456.018: Vessel 5 - Crane moved container 51
Time 3457.617: Vessel 6 - Container 50 loaded onto truck
Time 3459.018: Vessel 5 - Container 51 loaded onto truck
Time 3463.617: Vessel 6 - Truck transported container 50 to yard
Time 3463.617: Vessel 6 - Crane moved container 51
Time 3465.018: Vessel 5 - Truck transported container 51 to yard
Time 3465.018: Vessel 5 - Crane moved container 52
Time 3466.617: Vessel 6 - Container 51 loaded onto truck
Time 3468.018: Vessel 5 - Container 52 loaded onto truck
Time 3472.617: Vessel 6 - Truck transported container 51 to yard
Time 3472.617: Vessel 6 - Crane moved container 52
Time 3474.018: Vessel 5 - Truck transported container 52 to yard
Time 3474.018: Vessel 5 - Crane moved container 53
Time 3475.617: Vessel 6 - Container 52 loaded onto truck
Time 3477.018: Vessel 5 - Container 53 loaded onto truck
Time 3481.617: Vessel 6 - Truck transported container 52 to yard
Time 3481.617: Vessel 6 - Crane moved container 53
Time 3483.018: Vessel 5 - Truck transported container 53 to yard
Time 3483.018: Vessel 5 - Crane moved container 54
Time 3484.617: Vessel 6 - Container 53 loaded onto truck
Time 3486.018: Vessel 5 - Container 54 loaded onto truck
Time 3490.617: Vessel 6 - Truck transported container 53 to yard
Time 3490.617: Vessel 6 - Crane moved container 54
Time 3492.018: Vessel 5 - Truck transported container 54 to yard
Time 3492.018: Vessel 5 - Crane moved container 55
Time 3493.617: Vessel 6 - Container 54 loaded onto truck
Time 3495.018: Vessel 5 - Container 55 loaded onto truck
Time 3499.617: Vessel 6 - Truck transported container 54 to yard
Time 3499.617: Vessel 6 - Crane moved container 55
Time 3501.018: Vessel 5 - Truck transported container 55 to yard
Time 3501.018: Vessel 5 - Crane moved container 56
Time 3502.617: Vessel 6 - Container 55 loaded onto truck
Time 3504.018: Vessel 5 - Container 56 loaded onto truck
Time 3508.617: Vessel 6 - Truck transported container 55 to yard
Time 3508.617: Vessel 6 - Crane moved container 56
Time 3510.018: Vessel 5 - Truck transported container 56 to yard
Time 3510.018: Vessel 5 - Crane moved container 57
Time 3511.617: Vessel 6 - Container 56 loaded onto truck
Time 3513.018: Vessel 5 - Container 57 loaded onto truck
Time 3517.617: Vessel 6 - Truck transported container 56 to yard
Time 3517.617: Vessel 6 - Crane moved container 57
Time 3519.018: Vessel 5 - Truck transported container 57 to yard
Time 3519.018: Vessel 5 - Crane moved container 58
Time 3520.617: Vessel 6 - Container 57 loaded onto truck
Time 3522.018: Vessel 5 - Container 58 loaded onto truck
Time 3526.617: Vessel 6 - Truck transported container 57 to yard
Time 3526.617: Vessel 6 - Crane moved container 58
Time 3528.018: Vessel 5 - Truck transported container 58 to yard
Time 3528.018: Vessel 5 - Crane moved container 59
Time 3529.617: Vessel 6 - Container 58 loaded onto truck
Time 3531.018: Vessel 5 - Container 59 loaded onto truck
Time 3535.617: Vessel 6 - Truck transported container 58 to yard
Time 3535.617: Vessel 6 - Crane moved container 59
Time 3537.018: Vessel 5 - Truck transported container 59 to yard
Time 3537.018: Vessel 5 - Crane moved container 60
Time 3538.617: Vessel 6 - Container 59 loaded onto truck
Time 3540.018: Vessel 5 - Container 60 loaded onto truck
Time 3544.617: Vessel 6 - Truck transported container 59 to yard
Time 3544.617: Vessel 6 - Crane moved container 60
Time 3546.018: Vessel 5 - Truck transported container 60 to yard
Time 3546.018: Vessel 5 - Crane moved container 61
Time 3547.617: Vessel 6 - Container 60 loaded onto truck
Time 3549.018: Vessel 5 - Container 61 loaded onto truck
Time 3553.617: Vessel 6 - Truck transported container 60 to yard
Time 3553.617: Vessel 6 - Crane moved container 61
Time 3555.018: Vessel 5 - Truck transported container 61 to yard
Time 3555.018: Vessel 5 - Crane moved container 62
Time 3556.617: Vessel 6 - Container 61 loaded onto truck
Time 3558.018: Vessel 5 - Container 62 loaded onto truck
Time 3562.617: Vessel 6 - Truck transported container 61 to yard
Time 3562.617: Vessel 6 - Crane moved container 62
Time 3564.018: Vessel 5 - Truck transported container 62 to yard
Time 3564.018: Vessel 5 - Crane moved container 63
Time 3565.617: Vessel 6 - Container 62 loaded onto truck
Time 3567.018: Vessel 5 - Container 63 loaded onto truck
Time 3571.617: Vessel 6 - Truck transported container 62 to yard
Time 3571.617: Vessel 6 - Crane moved container 63
Time 3573.018: Vessel 5 - Truck transported container 63 to yard
Time 3573.018: Vessel 5 - Crane moved container 64
Time 3574.617: Vessel 6 - Container 63 loaded onto truck
Time 3576.018: Vessel 5 - Container 64 loaded onto truck
Time 3580.617: Vessel 6 - Truck transported container 63 to yard
Time 3580.617: Vessel 6 - Crane moved container 64
Time 3582.018: Vessel 5 - Truck transported container 64 to yard
Time 3582.018: Vessel 5 - Crane moved container 65
Time 3583.617: Vessel 6 - Container 64 loaded onto truck
Time 3585.018: Vessel 5 - Container 65 loaded onto truck
Time 3589.617: Vessel 6 - Truck transported container 64 to yard
Time 3589.617: Vessel 6 - Crane moved container 65
Time 3591.018: Vessel 5 - Truck transported container 65 to yard
Time 3591.018: Vessel 5 - Crane moved container 66
Time 3592.617: Vessel 6 - Container 65 loaded onto truck
Time 3594.018: Vessel 5 - Container 66 loaded onto truck
Time 3598.617: Vessel 6 - Truck transported container 65 to yard
Time 3598.617: Vessel 6 - Crane moved container 66
Time 3600.018: Vessel 5 - Truck transported container 66 to yard
Time 3600.018: Vessel 5 - Crane moved container 67
Time 3601.617: Vessel 6 - Container 66 loaded onto truck
Time 3603.018: Vessel 5 - Container 67 loaded onto truck
Time 3607.617: Vessel 6 - Truck transported container 66 to yard
Time 3607.617: Vessel 6 - Crane moved container 67
Time 3609.018: Vessel 5 - Truck transported container 67 to yard
Time 3609.018: Vessel 5 - Crane moved container 68
Time 3610.617: Vessel 6 - Container 67 loaded onto truck
Time 3612.018: Vessel 5 - Container 68 loaded onto truck
Time 3616.617: Vessel 6 - Truck transported container 67 to yard
Time 3616.617: Vessel 6 - Crane moved container 68
Time 3618.018: Vessel 5 - Truck transported container 68 to yard
Time 3618.018: Vessel 5 - Crane moved container 69
Time 3619.617: Vessel 6 - Container 68 loaded onto truck
Time 3621.018: Vessel 5 - Container 69 loaded onto truck
Time 3625.617: Vessel 6 - Truck transported container 68 to yard
Time 3625.617: Vessel 6 - Crane moved container 69
Time 3627.018: Vessel 5 - Truck transported container 69 to yard
Time 3627.018: Vessel 5 - Crane moved container 70
Time 3628.617: Vessel 6 - Container 69 loaded onto truck
Time 3630.018: Vessel 5 - Container 70 loaded onto truck
Time 3634.617: Vessel 6 - Truck transported container 69 to yard
Time 3634.617: Vessel 6 - Crane moved container 70
Time 3636.018: Vessel 5 - Truck transported container 70 to yard
Time 3636.018: Vessel 5 - Crane moved container 71
Time 3637.617: Vessel 6 - Container 70 loaded onto truck
Time 3639.018: Vessel 5 - Container 71 loaded onto truck
Time 3643.617: Vessel 6 - Truck transported container 70 to yard
Time 3643.617: Vessel 6 - Crane moved container 71
Time 3645.018: Vessel 5 - Truck transported container 71 to yard
Time 3645.018: Vessel 5 - Crane moved container 72
Time 3646.617: Vessel 6 - Container 71 loaded onto truck
Time 3648.018: Vessel 5 - Container 72 loaded onto truck
Time 3652.617: Vessel 6 - Truck transported container 71 to yard
Time 3652.617: Vessel 6 - Crane moved container 72
Time 3654.018: Vessel 5 - Truck transported container 72 to yard
Time 3654.018: Vessel 5 - Crane moved container 73
Time 3655.617: Vessel 6 - Container 72 loaded onto truck
Time 3657.018: Vessel 5 - Container 73 loaded onto truck
Time 3661.617: Vessel 6 - Truck transported container 72 to yard
Time 3661.617: Vessel 6 - Crane moved container 73
Time 3663.018: Vessel 5 - Truck transported container 73 to yard
Time 3663.018: Vessel 5 - Crane moved container 74
Time 3664.617: Vessel 6 - Container 73 loaded onto truck
Time 3666.018: Vessel 5 - Container 74 loaded onto truck
Time 3670.617: Vessel 6 - Truck transported container 73 to yard
Time 3670.617: Vessel 6 - Crane moved container 74
Time 3672.018: Vessel 5 - Truck transported container 74 to yard
Time 3672.018: Vessel 5 - Crane moved container 75
Time 3673.617: Vessel 6 - Container 74 loaded onto truck
Time 3675.018: Vessel 5 - Container 75 loaded onto truck
Time 3679.617: Vessel 6 - Truck transported container 74 to yard
Time 3679.617: Vessel 6 - Crane moved container 75
Time 3681.018: Vessel 5 - Truck transported container 75 to yard
Time 3681.018: Vessel 5 - Crane moved container 76
Time 3682.617: Vessel 6 - Container 75 loaded onto truck
Time 3684.018: Vessel 5 - Container 76 loaded onto truck
Time 3688.617: Vessel 6 - Truck transported container 75 to yard
Time 3688.617: Vessel 6 - Crane moved container 76
Time 3690.018: Vessel 5 - Truck transported container 76 to yard
Time 3690.018: Vessel 5 - Crane moved container 77
Time 3691.617: Vessel 6 - Container 76 loaded onto truck
Time 3693.018: Vessel 5 - Container 77 loaded onto truck
Time 3697.617: Vessel 6 - Truck transported container 76 to yard
Time 3697.617: Vessel 6 - Crane moved container 77
Time 3699.018: Vessel 5 - Truck transported container 77 to yard
Time 3699.018: Vessel 5 - Crane moved container 78
Time 3700.617: Vessel 6 - Container 77 loaded onto truck
Time 3702.018: Vessel 5 - Container 78 loaded onto truck
Time 3706.617: Vessel 6 - Truck transported container 77 to yard
Time 3706.617: Vessel 6 - Crane moved container 78
Time 3708.018: Vessel 5 - Truck transported container 78 to yard
Time 3708.018: Vessel 5 - Crane moved container 79
Time 3709.617: Vessel 6 - Container 78 loaded onto truck
Time 3711.018: Vessel 5 - Container 79 loaded onto truck
Time 3715.617: Vessel 6 - Truck transported container 78 to yard
Time 3715.617: Vessel 6 - Crane moved container 79
Time 3717.018: Vessel 5 - Truck transported container 79 to yard
Time 3717.018: Vessel 5 - Crane moved container 80
Time 3718.617: Vessel 6 - Container 79 loaded onto truck
Time 3720.018: Vessel 5 - Container 80 loaded onto truck
Time 3724.617: Vessel 6 - Truck transported container 79 to yard
Time 3724.617: Vessel 6 - Crane moved container 80
Time 3726.018: Vessel 5 - Truck transported container 80 to yard
Time 3726.018: Vessel 5 - Crane moved container 81
Time 3727.617: Vessel 6 - Container 80 loaded onto truck
Time 3729.018: Vessel 5 - Container 81 loaded onto truck
Time 3733.617: Vessel 6 - Truck transported container 80 to yard
Time 3733.617: Vessel 6 - Crane moved container 81
Time 3735.018: Vessel 5 - Truck transported container 81 to yard
Time 3735.018: Vessel 5 - Crane moved container 82
Time 3736.617: Vessel 6 - Container 81 loaded onto truck
Time 3738.018: Vessel 5 - Container 82 loaded onto truck
Time 3742.617: Vessel 6 - Truck transported container 81 to yard
Time 3742.617: Vessel 6 - Crane moved container 82
Time 3744.018: Vessel 5 - Truck transported container 82 to yard
Time 3744.018: Vessel 5 - Crane moved container 83
Time 3745.617: Vessel 6 - Container 82 loaded onto truck
Time 3747.018: Vessel 5 - Container 83 loaded onto truck
Time 3751.617: Vessel 6 - Truck transported container 82 to yard
Time 3751.617: Vessel 6 - Crane moved container 83
Time 3753.018: Vessel 5 - Truck transported container 83 to yard
Time 3753.018: Vessel 5 - Crane moved container 84
Time 3754.617: Vessel 6 - Container 83 loaded onto truck
Time 3756.018: Vessel 5 - Container 84 loaded onto truck
Time 3760.617: Vessel 6 - Truck transported container 83 to yard
Time 3760.617: Vessel 6 - Crane moved container 84
Time 3762.018: Vessel 5 - Truck transported container 84 to yard
Time 3762.018: Vessel 5 - Crane moved container 85
Time 3763.617: Vessel 6 - Container 84 loaded onto truck
Time 3765.018: Vessel 5 - Container 85 loaded onto truck
Time 3769.617: Vessel 6 - Truck transported container 84 to yard
Time 3769.617: Vessel 6 - Crane moved container 85
Time 3771.018: Vessel 5 - Truck transported container 85 to yard
Time 3771.018: Vessel 5 - Crane moved container 86
Time 3772.617: Vessel 6 - Container 85 loaded onto truck
Time 3774.018: Vessel 5 - Container 86 loaded onto truck
Time 3778.617: Vessel 6 - Truck transported container 85 to yard
Time 3778.617: Vessel 6 - Crane moved container 86
Time 3780.018: Vessel 5 - Truck transported container 86 to yard
Time 3780.018: Vessel 5 - Crane moved container 87
Time 3781.617: Vessel 6 - Container 86 loaded onto truck
Time 3783.018: Vessel 5 - Container 87 loaded onto truck
Time 3787.617: Vessel 6 - Truck transported container 86 to yard
Time 3787.617: Vessel 6 - Crane moved container 87
Time 3789.018: Vessel 5 - Truck transported container 87 to yard
Time 3789.018: Vessel 5 - Crane moved container 88
Time 3790.617: Vessel 6 - Container 87 loaded onto truck
Time 3792.018: Vessel 5 - Container 88 loaded onto truck
Time 3796.617: Vessel 6 - Truck transported container 87 to yard
Time 3796.617: Vessel 6 - Crane moved container 88
Time 3798.018: Vessel 5 - Truck transported container 88 to yard
Time 3798.018: Vessel 5 - Crane moved container 89
Time 3799.617: Vessel 6 - Container 88 loaded onto truck
Time 3801.018: Vessel 5 - Container 89 loaded onto truck
Time 3805.617: Vessel 6 - Truck transported container 88 to yard
Time 3805.617: Vessel 6 - Crane moved container 89
Time 3807.018: Vessel 5 - Truck transported container 89 to yard
Time 3807.018: Vessel 5 - Crane moved container 90
Time 3808.617: Vessel 6 - Container 89 loaded onto truck
Time 3810.018: Vessel 5 - Container 90 loaded onto truck
Time 3814.617: Vessel 6 - Truck transported container 89 to yard
Time 3814.617: Vessel 6 - Crane moved container 90
Time 3816.018: Vessel 5 - Truck transported container 90 to yard
Time 3816.018: Vessel 5 - Crane moved container 91
Time 3817.617: Vessel 6 - Container 90 loaded onto truck
Time 3819.018: Vessel 5 - Container 91 loaded onto truck
Time 3823.617: Vessel 6 - Truck transported container 90 to yard
Time 3823.617: Vessel 6 - Crane moved container 91
Time 3825.018: Vessel 5 - Truck transported container 91 to yard
Time 3825.018: Vessel 5 - Crane moved container 92
Time 3826.617: Vessel 6 - Container 91 loaded onto truck
Time 3828.018: Vessel 5 - Container 92 loaded onto truck
Time 3832.617: Vessel 6 - Truck transported container 91 to yard
Time 3832.617: Vessel 6 - Crane moved container 92
Time 3834.018: Vessel 5 - Truck transported container 92 to yard
Time 3834.018: Vessel 5 - Crane moved container 93
Time 3835.617: Vessel 6 - Container 92 loaded onto truck
Time 3837.018: Vessel 5 - Container 93 loaded onto truck
Time 3841.617: Vessel 6 - Truck transported container 92 to yard
Time 3841.617: Vessel 6 - Crane moved container 93
Time 3843.018: Vessel 5 - Truck transported container 93 to yard
Time 3843.018: Vessel 5 - Crane moved container 94
Time 3843.454: Vessel 19 Arrived
Time 3843.454: Vessel 19 Waiting for a berth
Time 3844.617: Vessel 6 - Container 93 loaded onto truck
Time 3845.410: Vessel 20 Arrived
Time 3845.410: Vessel 20 Waiting for a berth
Time 3846.018: Vessel 5 - Container 94 loaded onto truck
Time 3850.617: Vessel 6 - Truck transported container 93 to yard
Time 3850.617: Vessel 6 - Crane moved container 94
Time 3852.018: Vessel 5 - Truck transported container 94 to yard
Time 3852.018: Vessel 5 - Crane moved container 95
Time 3853.617: Vessel 6 - Container 94 loaded onto truck
Time 3855.018: Vessel 5 - Container 95 loaded onto truck
Time 3859.617: Vessel 6 - Truck transported container 94 to yard
Time 3859.617: Vessel 6 - Crane moved container 95
Time 3861.018: Vessel 5 - Truck transported container 95 to yard
Time 3861.018: Vessel 5 - Crane moved container 96
Time 3862.617: Vessel 6 - Container 95 loaded onto truck
Time 3864.018: Vessel 5 - Container 96 loaded onto truck
Time 3868.617: Vessel 6 - Truck transported container 95 to yard
Time 3868.617: Vessel 6 - Crane moved container 96
Time 3870.018: Vessel 5 - Truck transported container 96 to yard
Time 3870.018: Vessel 5 - Crane moved container 97
Time 3871.617: Vessel 6 - Container 96 loaded onto truck
Time 3873.018: Vessel 5 - Container 97 loaded onto truck
Time 3877.617: Vessel 6 - Truck transported container 96 to yard
Time 3877.617: Vessel 6 - Crane moved container 97
Time 3879.018: Vessel 5 - Truck transported container 97 to yard
Time 3879.018: Vessel 5 - Crane moved container 98
Time 3880.617: Vessel 6 - Container 97 loaded onto truck
Time 3882.018: Vessel 5 - Container 98 loaded onto truck
Time 3886.617: Vessel 6 - Truck transported container 97 to yard
Time 3886.617: Vessel 6 - Crane moved container 98
Time 3888.018: Vessel 5 - Truck transported container 98 to yard
Time 3888.018: Vessel 5 - Crane moved container 99
Time 3889.617: Vessel 6 - Container 98 loaded onto truck
Time 3891.018: Vessel 5 - Container 99 loaded onto truck
Time 3895.617: Vessel 6 - Truck transported container 98 to yard
Time 3895.617: Vessel 6 - Crane moved container 99
Time 3897.018: Vessel 5 - Truck transported container 99 to yard
Time 3897.018: Vessel 5 - Crane moved container 100
Time 3898.617: Vessel 6 - Container 99 loaded onto truck
Time 3900.018: Vessel 5 - Container 100 loaded onto truck
Time 3904.617: Vessel 6 - Truck transported container 99 to yard
Time 3904.617: Vessel 6 - Crane moved container 100
Time 3906.018: Vessel 5 - Truck transported container 100 to yard
Time 3906.018: Vessel 5 - Crane moved container 101
Time 3907.617: Vessel 6 - Container 100 loaded onto truck
Time 3909.018: Vessel 5 - Container 101 loaded onto truck
Time 3913.617: Vessel 6 - Truck transported container 100 to yard
Time 3913.617: Vessel 6 - Crane moved container 101
Time 3915.018: Vessel 5 - Truck transported container 101 to yard
Time 3915.018: Vessel 5 - Crane moved container 102
Time 3916.617: Vessel 6 - Container 101 loaded onto truck
Time 3918.018: Vessel 5 - Container 102 loaded onto truck
Time 3922.617: Vessel 6 - Truck transported container 101 to yard
Time 3922.617: Vessel 6 - Crane moved container 102
Time 3924.018: Vessel 5 - Truck transported container 102 to yard
Time 3924.018: Vessel 5 - Crane moved container 103
Time 3925.617: Vessel 6 - Container 102 loaded onto truck
Time 3927.018: Vessel 5 - Container 103 loaded onto truck
Time 3931.617: Vessel 6 - Truck transported container 102 to yard
Time 3931.617: Vessel 6 - Crane moved container 103
Time 3933.018: Vessel 5 - Truck transported container 103 to yard
Time 3933.018: Vessel 5 - Crane moved container 104
Time 3934.617: Vessel 6 - Container 103 loaded onto truck
Time 3936.018: Vessel 5 - Container 104 loaded onto truck
Time 3940.617: Vessel 6 - Truck transported container 103 to yard
Time 3940.617: Vessel 6 - Crane moved container 104
Time 3942.018: Vessel 5 - Truck transported container 104 to yard
Time 3942.018: Vessel 5 - Crane moved container 105
Time 3943.617: Vessel 6 - Container 104 loaded onto truck
Time 3945.018: Vessel 5 - Container 105 loaded onto truck
Time 3949.617: Vessel 6 - Truck transported container 104 to yard
Time 3949.617: Vessel 6 - Crane moved container 105
Time 3951.018: Vessel 5 - Truck transported container 105 to yard
Time 3951.018: Vessel 5 - Crane moved container 106
Time 3952.617: Vessel 6 - Container 105 loaded onto truck
Time 3954.018: Vessel 5 - Container 106 loaded onto truck
Time 3958.617: Vessel 6 - Truck transported container 105 to yard
Time 3958.617: Vessel 6 - Crane moved container 106
Time 3960.018: Vessel 5 - Truck transported container 106 to yard
Time 3960.018: Vessel 5 - Crane moved container 107
Time 3961.617: Vessel 6 - Container 106 loaded onto truck
Time 3963.018: Vessel 5 - Container 107 loaded onto truck
Time 3967.617: Vessel 6 - Truck transported container 106 to yard
Time 3967.617: Vessel 6 - Crane moved container 107
Time 3969.018: Vessel 5 - Truck transported container 107 to yard
Time 3969.018: Vessel 5 - Crane moved container 108
Time 3970.617: Vessel 6 - Container 107 loaded onto truck
Time 3972.018: Vessel 5 - Container 108 loaded onto truck
Time 3976.617: Vessel 6 - Truck transported container 107 to yard
Time 3976.617: Vessel 6 - Crane moved container 108
Time 3978.018: Vessel 5 - Truck transported container 108 to yard
Time 3978.018: Vessel 5 - Crane moved container 109
Time 3979.617: Vessel 6 - Container 108 loaded onto truck
Time 3981.018: Vessel 5 - Container 109 loaded onto truck
Time 3985.617: Vessel 6 - Truck transported container 108 to yard
Time 3985.617: Vessel 6 - Crane moved container 109
Time 3987.018: Vessel 5 - Truck transported container 109 to yard
Time 3987.018: Vessel 5 - Crane moved container 110
Time 3988.617: Vessel 6 - Container 109 loaded onto truck
Time 3990.018: Vessel 5 - Container 110 loaded onto truck
Time 3994.617: Vessel 6 - Truck transported container 109 to yard
Time 3994.617: Vessel 6 - Crane moved container 110
Time 3996.018: Vessel 5 - Truck transported container 110 to yard
Time 3996.018: Vessel 5 - Crane moved container 111
Time 3997.617: Vessel 6 - Container 110 loaded onto truck
Time 3999.018: Vessel 5 - Container 111 loaded onto truck
Time 4003.617: Vessel 6 - Truck transported container 110 to yard
Time 4003.617: Vessel 6 - Crane moved container 111
Time 4005.018: Vessel 5 - Truck transported container 111 to yard
Time 4005.018: Vessel 5 - Crane moved container 112
Time 4006.617: Vessel 6 - Container 111 loaded onto truck
Time 4008.018: Vessel 5 - Container 112 loaded onto truck
Time 4012.617: Vessel 6 - Truck transported container 111 to yard
Time 4012.617: Vessel 6 - Crane moved container 112
Time 4014.018: Vessel 5 - Truck transported container 112 to yard
Time 4014.018: Vessel 5 - Crane moved container 113
Time 4015.617: Vessel 6 - Container 112 loaded onto truck
Time 4017.018: Vessel 5 - Container 113 loaded onto truck
Time 4021.617: Vessel 6 - Truck transported container 112 to yard
Time 4021.617: Vessel 6 - Crane moved container 113
Time 4023.018: Vessel 5 - Truck transported container 113 to yard
Time 4023.018: Vessel 5 - Crane moved container 114
Time 4024.617: Vessel 6 - Container 113 loaded onto truck
Time 4026.018: Vessel 5 - Container 114 loaded onto truck
Time 4030.617: Vessel 6 - Truck transported container 113 to yard
Time 4030.617: Vessel 6 - Crane moved container 114
Time 4032.018: Vessel 5 - Truck transported container 114 to yard
Time 4032.018: Vessel 5 - Crane moved container 115
Time 4033.617: Vessel 6 - Container 114 loaded onto truck
Time 4035.018: Vessel 5 - Container 115 loaded onto truck
Time 4039.617: Vessel 6 - Truck transported container 114 to yard
Time 4039.617: Vessel 6 - Crane moved container 115
Time 4041.018: Vessel 5 - Truck transported container 115 to yard
Time 4041.018: Vessel 5 - Crane moved container 116
Time 4042.617: Vessel 6 - Container 115 loaded onto truck
Time 4044.018: Vessel 5 - Container 116 loaded onto truck
Time 4048.617: Vessel 6 - Truck transported container 115 to yard
Time 4048.617: Vessel 6 - Crane moved container 116
Time 4050.018: Vessel 5 - Truck transported container 116 to yard
Time 4050.018: Vessel 5 - Crane moved container 117
Time 4051.617: Vessel 6 - Container 116 loaded onto truck
Time 4053.018: Vessel 5 - Container 117 loaded onto truck
Time 4057.617: Vessel 6 - Truck transported container 116 to yard
Time 4057.617: Vessel 6 - Crane moved container 117
Time 4059.018: Vessel 5 - Truck transported container 117 to yard
Time 4059.018: Vessel 5 - Crane moved container 118
Time 4060.617: Vessel 6 - Container 117 loaded onto truck
Time 4062.018: Vessel 5 - Container 118 loaded onto truck
Time 4066.617: Vessel 6 - Truck transported container 117 to yard
Time 4066.617: Vessel 6 - Crane moved container 118
Time 4068.018: Vessel 5 - Truck transported container 118 to yard
Time 4068.018: Vessel 5 - Crane moved container 119
Time 4069.617: Vessel 6 - Container 118 loaded onto truck
Time 4071.018: Vessel 5 - Container 119 loaded onto truck
Time 4075.617: Vessel 6 - Truck transported container 118 to yard
Time 4075.617: Vessel 6 - Crane moved container 119
Time 4077.018: Vessel 5 - Truck transported container 119 to yard
Time 4077.018: Vessel 5 - Crane moved container 120
Time 4078.617: Vessel 6 - Container 119 loaded onto truck
Time 4080.018: Vessel 5 - Container 120 loaded onto truck
Time 4084.617: Vessel 6 - Truck transported container 119 to yard
Time 4084.617: Vessel 6 - Crane moved container 120
Time 4086.018: Vessel 5 - Truck transported container 120 to yard
Time 4086.018: Vessel 5 - Crane moved container 121
Time 4087.617: Vessel 6 - Container 120 loaded onto truck
Time 4089.018: Vessel 5 - Container 121 loaded onto truck
Time 4093.617: Vessel 6 - Truck transported container 120 to yard
Time 4093.617: Vessel 6 - Crane moved container 121
Time 4095.018: Vessel 5 - Truck transported container 121 to yard
Time 4095.018: Vessel 5 - Crane moved container 122
Time 4096.617: Vessel 6 - Container 121 loaded onto truck
Time 4098.018: Vessel 5 - Container 122 loaded onto truck
Time 4102.617: Vessel 6 - Truck transported container 121 to yard
Time 4102.617: Vessel 6 - Crane moved container 122
Time 4104.018: Vessel 5 - Truck transported container 122 to yard
Time 4104.018: Vessel 5 - Crane moved container 123
Time 4105.617: Vessel 6 - Container 122 loaded onto truck
Time 4107.018: Vessel 5 - Container 123 loaded onto truck
Time 4111.617: Vessel 6 - Truck transported container 122 to yard
Time 4111.617: Vessel 6 - Crane moved container 123
Time 4113.018: Vessel 5 - Truck transported container 123 to yard
Time 4113.018: Vessel 5 - Crane moved container 124
Time 4114.617: Vessel 6 - Container 123 loaded onto truck
Time 4116.018: Vessel 5 - Container 124 loaded onto truck
Time 4120.617: Vessel 6 - Truck transported container 123 to yard
Time 4120.617: Vessel 6 - Crane moved container 124
Time 4122.018: Vessel 5 - Truck transported container 124 to yard
Time 4122.018: Vessel 5 - Crane moved container 125
Time 4123.617: Vessel 6 - Container 124 loaded onto truck
Time 4125.018: Vessel 5 - Container 125 loaded onto truck
Time 4129.617: Vessel 6 - Truck transported container 124 to yard
Time 4129.617: Vessel 6 - Crane moved container 125
Time 4131.018: Vessel 5 - Truck transported container 125 to yard
Time 4131.018: Vessel 5 - Crane moved container 126
Time 4132.617: Vessel 6 - Container 125 loaded onto truck
Time 4134.018: Vessel 5 - Container 126 loaded onto truck
Time 4138.617: Vessel 6 - Truck transported container 125 to yard
Time 4138.617: Vessel 6 - Crane moved container 126
Time 4140.018: Vessel 5 - Truck transported container 126 to yard
Time 4140.018: Vessel 5 - Crane moved container 127
Time 4141.617: Vessel 6 - Container 126 loaded onto truck
Time 4143.018: Vessel 5 - Container 127 loaded onto truck
Time 4147.617: Vessel 6 - Truck transported container 126 to yard
Time 4147.617: Vessel 6 - Crane moved container 127
Time 4149.018: Vessel 5 - Truck transported container 127 to yard
Time 4149.018: Vessel 5 - Crane moved container 128
Time 4150.617: Vessel 6 - Container 127 loaded onto truck
Time 4152.018: Vessel 5 - Container 128 loaded onto truck
Time 4156.617: Vessel 6 - Truck transported container 127 to yard
Time 4156.617: Vessel 6 - Crane moved container 128
Time 4158.018: Vessel 5 - Truck transported container 128 to yard
Time 4158.018: Vessel 5 - Crane moved container 129
Time 4159.617: Vessel 6 - Container 128 loaded onto truck
Time 4161.018: Vessel 5 - Container 129 loaded onto truck
Time 4165.617: Vessel 6 - Truck transported container 128 to yard
Time 4165.617: Vessel 6 - Crane moved container 129
Time 4167.018: Vessel 5 - Truck transported container 129 to yard
Time 4167.018: Vessel 5 - Crane moved container 130
Time 4168.617: Vessel 6 - Container 129 loaded onto truck
Time 4170.018: Vessel 5 - Container 130 loaded onto truck
Time 4174.617: Vessel 6 - Truck transported container 129 to yard
Time 4174.617: Vessel 6 - Crane moved container 130
Time 4176.018: Vessel 5 - Truck transported container 130 to yard
Time 4176.018: Vessel 5 - Crane moved container 131
Time 4177.617: Vessel 6 - Container 130 loaded onto truck
Time 4179.018: Vessel 5 - Container 131 loaded onto truck
Time 4183.617: Vessel 6 - Truck transported container 130 to yard
Time 4183.617: Vessel 6 - Crane moved container 131
Time 4185.018: Vessel 5 - Truck transported container 131 to yard
Time 4185.018: Vessel 5 - Crane moved container 132
Time 4186.617: Vessel 6 - Container 131 loaded onto truck
Time 4188.018: Vessel 5 - Container 132 loaded onto truck
Time 4192.617: Vessel 6 - Truck transported container 131 to yard
Time 4192.617: Vessel 6 - Crane moved container 132
Time 4194.018: Vessel 5 - Truck transported container 132 to yard
Time 4194.018: Vessel 5 - Crane moved container 133
Time 4195.617: Vessel 6 - Container 132 loaded onto truck
Time 4197.018: Vessel 5 - Container 133 loaded onto truck
Time 4201.617: Vessel 6 - Truck transported container 132 to yard
Time 4201.617: Vessel 6 - Crane moved container 133
Time 4203.018: Vessel 5 - Truck transported container 133 to yard
Time 4203.018: Vessel 5 - Crane moved container 134
Time 4204.617: Vessel 6 - Container 133 loaded onto truck
Time 4206.018: Vessel 5 - Container 134 loaded onto truck
Time 4210.617: Vessel 6 - Truck transported container 133 to yard
Time 4210.617: Vessel 6 - Crane moved container 134
Time 4212.018: Vessel 5 - Truck transported container 134 to yard
Time 4212.018: Vessel 5 - Crane moved container 135
Time 4213.617: Vessel 6 - Container 134 loaded onto truck
Time 4215.018: Vessel 5 - Container 135 loaded onto truck
Time 4219.617: Vessel 6 - Truck transported container 134 to yard
Time 4219.617: Vessel 6 - Crane moved container 135
Time 4221.018: Vessel 5 - Truck transported container 135 to yard
Time 4221.018: Vessel 5 - Crane moved container 136
Time 4222.617: Vessel 6 - Container 135 loaded onto truck
Time 4224.018: Vessel 5 - Container 136 loaded onto truck
Time 4228.617: Vessel 6 - Truck transported container 135 to yard
Time 4228.617: Vessel 6 - Crane moved container 136
Time 4230.018: Vessel 5 - Truck transported container 136 to yard
Time 4230.018: Vessel 5 - Crane moved container 137
Time 4231.617: Vessel 6 - Container 136 loaded onto truck
Time 4233.018: Vessel 5 - Container 137 loaded onto truck
Time 4237.617: Vessel 6 - Truck transported container 136 to yard
Time 4237.617: Vessel 6 - Crane moved container 137
Time 4239.018: Vessel 5 - Truck transported container 137 to yard
Time 4239.018: Vessel 5 - Crane moved container 138
Time 4240.617: Vessel 6 - Container 137 loaded onto truck
Time 4242.018: Vessel 5 - Container 138 loaded onto truck
Time 4246.617: Vessel 6 - Truck transported container 137 to yard
Time 4246.617: Vessel 6 - Crane moved container 138
Time 4248.018: Vessel 5 - Truck transported container 138 to yard
Time 4248.018: Vessel 5 - Crane moved container 139
Time 4249.617: Vessel 6 - Container 138 loaded onto truck
Time 4251.018: Vessel 5 - Container 139 loaded onto truck
Time 4255.617: Vessel 6 - Truck transported container 138 to yard
Time 4255.617: Vessel 6 - Crane moved container 139
Time 4257.018: Vessel 5 - Truck transported container 139 to yard
Time 4257.018: Vessel 5 - Crane moved container 140
Time 4258.617: Vessel 6 - Container 139 loaded onto truck
Time 4260.018: Vessel 5 - Container 140 loaded onto truck
Time 4264.617: Vessel 6 - Truck transported container 139 to yard
Time 4264.617: Vessel 6 - Crane moved container 140
Time 4266.018: Vessel 5 - Truck transported container 140 to yard
Time 4266.018: Vessel 5 - Crane moved container 141
Time 4267.617: Vessel 6 - Container 140 loaded onto truck
Time 4269.018: Vessel 5 - Container 141 loaded onto truck
Time 4273.617: Vessel 6 - Truck transported container 140 to yard
Time 4273.617: Vessel 6 - Crane moved container 141
Time 4275.018: Vessel 5 - Truck transported container 141 to yard
Time 4275.018: Vessel 5 - Crane moved container 142
Time 4276.617: Vessel 6 - Container 141 loaded onto truck
Time 4278.018: Vessel 5 - Container 142 loaded onto truck
Time 4282.617: Vessel 6 - Truck transported container 141 to yard
Time 4282.617: Vessel 6 - Crane moved container 142
Time 4284.018: Vessel 5 - Truck transported container 142 to yard
Time 4284.018: Vessel 5 - Crane moved container 143
Time 4285.617: Vessel 6 - Container 142 loaded onto truck
Time 4287.018: Vessel 5 - Container 143 loaded onto truck
Time 4291.617: Vessel 6 - Truck transported container 142 to yard
Time 4291.617: Vessel 6 - Crane moved container 143
Time 4293.018: Vessel 5 - Truck transported container 143 to yard
Time 4293.018: Vessel 5 - Crane moved container 144
Time 4294.617: Vessel 6 - Container 143 loaded onto truck
Time 4296.018: Vessel 5 - Container 144 loaded onto truck
Time 4300.617: Vessel 6 - Truck transported container 143 to yard
Time 4300.617: Vessel 6 - Crane moved container 144
Time 4302.018: Vessel 5 - Truck transported container 144 to yard
Time 4302.018: Vessel 5 - Crane moved container 145
Time 4303.617: Vessel 6 - Container 144 loaded onto truck
Time 4305.018: Vessel 5 - Container 145 loaded onto truck
Time 4309.617: Vessel 6 - Truck transported container 144 to yard
Time 4309.617: Vessel 6 - Crane moved container 145
Time 4311.018: Vessel 5 - Truck transported container 145 to yard
Time 4311.018: Vessel 5 - Crane moved container 146
Time 4312.617: Vessel 6 - Container 145 loaded onto truck
Time 4314.018: Vessel 5 - Container 146 loaded onto truck
Time 4318.617: Vessel 6 - Truck transported container 145 to yard
Time 4318.617: Vessel 6 - Crane moved container 146
Time 4320.018: Vessel 5 - Truck transported container 146 to yard
Time 4320.018: Vessel 5 - Crane moved container 147
Time 4321.617: Vessel 6 - Container 146 loaded onto truck
Time 4323.018: Vessel 5 - Container 147 loaded onto truck
Time 4327.617: Vessel 6 - Truck transported container 146 to yard
Time 4327.617: Vessel 6 - Crane moved container 147
Time 4329.018: Vessel 5 - Truck transported container 147 to yard
Time 4329.018: Vessel 5 - Crane moved container 148
Time 4330.617: Vessel 6 - Container 147 loaded onto truck
Time 4332.018: Vessel 5 - Container 148 loaded onto truck
Time 4336.617: Vessel 6 - Truck transported container 147 to yard
Time 4336.617: Vessel 6 - Crane moved container 148
Time 4337.100: Vessel 21 Arrived
Time 4337.100: Vessel 21 Waiting for a berth
Time 4338.018: Vessel 5 - Truck transported container 148 to yard
Time 4338.018: Vessel 5 - Crane moved container 149
Time 4339.617: Vessel 6 - Container 148 loaded onto truck
Time 4341.018: Vessel 5 - Container 149 loaded onto truck
Time 4345.617: Vessel 6 - Truck transported container 148 to yard
Time 4345.617: Vessel 6 - Crane moved container 149
Time 4347.018: Vessel 5 - Truck transported container 149 to yard
Time 4347.018: Vessel 5 - Crane moved container 150
Time 4348.617: Vessel 6 - Container 149 loaded onto truck
Time 4350.018: Vessel 5 - Container 150 loaded onto truck
Time 4354.617: Vessel 6 - Truck transported container 149 to yard
Time 4354.617: Vessel 6 - Crane moved container 150
Time 4356.018: Vessel 5 - Truck transported container 150 to yard
Time 4356.018: Vessel 5 finished unloading and leaves
Time 4356.018: Vessel 7 berthed
Time 4356.018: Vessel 7 - Crane allocated
Time 4356.018: Vessel 7 - Crane moved container 1
Time 4357.617: Vessel 6 - Container 150 loaded onto truck
Time 4359.018: Vessel 7 - Container 1 loaded onto truck
Time 4363.617: Vessel 6 - Truck transported container 150 to yard
Time 4363.617: Vessel 6 finished unloading and leaves
Time 4363.617: Vessel 8 berthed
Time 4363.617: Vessel 8 - Crane allocated
Time 4363.617: Vessel 8 - Crane moved container 1
Time 4365.018: Vessel 7 - Truck transported container 1 to yard
Time 4365.018: Vessel 7 - Crane moved container 2
Time 4366.617: Vessel 8 - Container 1 loaded onto truck
Time 4368.018: Vessel 7 - Container 2 loaded onto truck
Time 4372.617: Vessel 8 - Truck transported container 1 to yard
Time 4372.617: Vessel 8 - Crane moved container 2
Time 4374.018: Vessel 7 - Truck transported container 2 to yard
Time 4374.018: Vessel 7 - Crane moved container 3
Time 4375.617: Vessel 8 - Container 2 loaded onto truck
Time 4377.018: Vessel 7 - Container 3 loaded onto truck
Time 4381.617: Vessel 8 - Truck transported container 2 to yard
Time 4381.617: Vessel 8 - Crane moved container 3
Time 4383.018: Vessel 7 - Truck transported container 3 to yard
Time 4383.018: Vessel 7 - Crane moved container 4
Time 4384.617: Vessel 8 - Container 3 loaded onto truck
Time 4386.018: Vessel 7 - Container 4 loaded onto truck
Time 4390.617: Vessel 8 - Truck transported container 3 to yard
Time 4390.617: Vessel 8 - Crane moved container 4
Time 4392.018: Vessel 7 - Truck transported container 4 to yard
Time 4392.018: Vessel 7 - Crane moved container 5
Time 4393.617: Vessel 8 - Container 4 loaded onto truck
Time 4395.018: Vessel 7 - Container 5 loaded onto truck
Time 4399.617: Vessel 8 - Truck transported container 4 to yard
Time 4399.617: Vessel 8 - Crane moved container 5
Time 4401.018: Vessel 7 - Truck transported container 5 to yard
Time 4401.018: Vessel 7 - Crane moved container 6
Time 4402.617: Vessel 8 - Container 5 loaded onto truck
Time 4404.018: Vessel 7 - Container 6 loaded onto truck
Time 4408.617: Vessel 8 - Truck transported container 5 to yard
Time 4408.617: Vessel 8 - Crane moved container 6
Time 4410.018: Vessel 7 - Truck transported container 6 to yard
Time 4410.018: Vessel 7 - Crane moved container 7
Time 4411.617: Vessel 8 - Container 6 loaded onto truck
Time 4413.018: Vessel 7 - Container 7 loaded onto truck
Time 4417.617: Vessel 8 - Truck transported container 6 to yard
Time 4417.617: Vessel 8 - Crane moved container 7
Time 4419.018: Vessel 7 - Truck transported container 7 to yard
Time 4419.018: Vessel 7 - Crane moved container 8
Time 4420.617: Vessel 8 - Container 7 loaded onto truck
Time 4422.018: Vessel 7 - Container 8 loaded onto truck
Time 4426.617: Vessel 8 - Truck transported container 7 to yard
Time 4426.617: Vessel 8 - Crane moved container 8
Time 4428.018: Vessel 7 - Truck transported container 8 to yard
Time 4428.018: Vessel 7 - Crane moved container 9
Time 4429.617: Vessel 8 - Container 8 loaded onto truck
Time 4431.018: Vessel 7 - Container 9 loaded onto truck
Time 4435.617: Vessel 8 - Truck transported container 8 to yard
Time 4435.617: Vessel 8 - Crane moved container 9
Time 4437.018: Vessel 7 - Truck transported container 9 to yard
Time 4437.018: Vessel 7 - Crane moved container 10
Time 4438.617: Vessel 8 - Container 9 loaded onto truck
Time 4440.018: Vessel 7 - Container 10 loaded onto truck
Time 4444.617: Vessel 8 - Truck transported container 9 to yard
Time 4444.617: Vessel 8 - Crane moved container 10
Time 4446.018: Vessel 7 - Truck transported container 10 to yard
Time 4446.018: Vessel 7 - Crane moved container 11
Time 4447.617: Vessel 8 - Container 10 loaded onto truck
Time 4449.018: Vessel 7 - Container 11 loaded onto truck
Time 4453.617: Vessel 8 - Truck transported container 10 to yard
Time 4453.617: Vessel 8 - Crane moved container 11
Time 4455.018: Vessel 7 - Truck transported container 11 to yard
Time 4455.018: Vessel 7 - Crane moved container 12
Time 4456.617: Vessel 8 - Container 11 loaded onto truck
Time 4458.018: Vessel 7 - Container 12 loaded onto truck
Time 4462.617: Vessel 8 - Truck transported container 11 to yard
Time 4462.617: Vessel 8 - Crane moved container 12
Time 4464.018: Vessel 7 - Truck transported container 12 to yard
Time 4464.018: Vessel 7 - Crane moved container 13
Time 4465.617: Vessel 8 - Container 12 loaded onto truck
Time 4467.018: Vessel 7 - Container 13 loaded onto truck
Time 4471.617: Vessel 8 - Truck transported container 12 to yard
Time 4471.617: Vessel 8 - Crane moved container 13
Time 4473.018: Vessel 7 - Truck transported container 13 to yard
Time 4473.018: Vessel 7 - Crane moved container 14
Time 4474.617: Vessel 8 - Container 13 loaded onto truck
Time 4476.018: Vessel 7 - Container 14 loaded onto truck
Time 4480.617: Vessel 8 - Truck transported container 13 to yard
Time 4480.617: Vessel 8 - Crane moved container 14
Time 4482.018: Vessel 7 - Truck transported container 14 to yard
Time 4482.018: Vessel 7 - Crane moved container 15
Time 4483.617: Vessel 8 - Container 14 loaded onto truck
Time 4485.018: Vessel 7 - Container 15 loaded onto truck
Time 4489.617: Vessel 8 - Truck transported container 14 to yard
Time 4489.617: Vessel 8 - Crane moved container 15
Time 4491.018: Vessel 7 - Truck transported container 15 to yard
Time 4491.018: Vessel 7 - Crane moved container 16
Time 4492.617: Vessel 8 - Container 15 loaded onto truck
Time 4494.018: Vessel 7 - Container 16 loaded onto truck
Time 4498.617: Vessel 8 - Truck transported container 15 to yard
Time 4498.617: Vessel 8 - Crane moved container 16
Time 4500.018: Vessel 7 - Truck transported container 16 to yard
Time 4500.018: Vessel 7 - Crane moved container 17
Time 4501.617: Vessel 8 - Container 16 loaded onto truck
Time 4503.018: Vessel 7 - Container 17 loaded onto truck
Time 4507.617: Vessel 8 - Truck transported container 16 to yard
Time 4507.617: Vessel 8 - Crane moved container 17
Time 4509.018: Vessel 7 - Truck transported container 17 to yard
Time 4509.018: Vessel 7 - Crane moved container 18
Time 4510.617: Vessel 8 - Container 17 loaded onto truck
Time 4512.018: Vessel 7 - Container 18 loaded onto truck
Time 4516.617: Vessel 8 - Truck transported container 17 to yard
Time 4516.617: Vessel 8 - Crane moved container 18
Time 4518.018: Vessel 7 - Truck transported container 18 to yard
Time 4518.018: Vessel 7 - Crane moved container 19
Time 4519.617: Vessel 8 - Container 18 loaded onto truck
Time 4521.018: Vessel 7 - Container 19 loaded onto truck
Time 4525.617: Vessel 8 - Truck transported container 18 to yard
Time 4525.617: Vessel 8 - Crane moved container 19
Time 4527.018: Vessel 7 - Truck transported container 19 to yard
Time 4527.018: Vessel 7 - Crane moved container 20
Time 4528.617: Vessel 8 - Container 19 loaded onto truck
Time 4530.018: Vessel 7 - Container 20 loaded onto truck
Time 4534.617: Vessel 8 - Truck transported container 19 to yard
Time 4534.617: Vessel 8 - Crane moved container 20
Time 4536.018: Vessel 7 - Truck transported container 20 to yard
Time 4536.018: Vessel 7 - Crane moved container 21
Time 4537.617: Vessel 8 - Container 20 loaded onto truck
Time 4539.018: Vessel 7 - Container 21 loaded onto truck
Time 4543.617: Vessel 8 - Truck transported container 20 to yard
Time 4543.617: Vessel 8 - Crane moved container 21
Time 4545.018: Vessel 7 - Truck transported container 21 to yard
Time 4545.018: Vessel 7 - Crane moved container 22
Time 4546.617: Vessel 8 - Container 21 loaded onto truck
Time 4548.018: Vessel 7 - Container 22 loaded onto truck
Time 4552.617: Vessel 8 - Truck transported container 21 to yard
Time 4552.617: Vessel 8 - Crane moved container 22
Time 4554.018: Vessel 7 - Truck transported container 22 to yard
Time 4554.018: Vessel 7 - Crane moved container 23
Time 4555.617: Vessel 8 - Container 22 loaded onto truck
Time 4557.018: Vessel 7 - Container 23 loaded onto truck
Time 4561.617: Vessel 8 - Truck transported container 22 to yard
Time 4561.617: Vessel 8 - Crane moved container 23
Time 4563.018: Vessel 7 - Truck transported container 23 to yard
Time 4563.018: Vessel 7 - Crane moved container 24
Time 4564.617: Vessel 8 - Container 23 loaded onto truck
Time 4566.018: Vessel 7 - Container 24 loaded onto truck
Time 4570.617: Vessel 8 - Truck transported container 23 to yard
Time 4570.617: Vessel 8 - Crane moved container 24
Time 4572.018: Vessel 7 - Truck transported container 24 to yard
Time 4572.018: Vessel 7 - Crane moved container 25
Time 4573.617: Vessel 8 - Container 24 loaded onto truck
Time 4575.018: Vessel 7 - Container 25 loaded onto truck
Time 4579.617: Vessel 8 - Truck transported container 24 to yard
Time 4579.617: Vessel 8 - Crane moved container 25
Time 4581.018: Vessel 7 - Truck transported container 25 to yard
Time 4581.018: Vessel 7 - Crane moved container 26
Time 4582.617: Vessel 8 - Container 25 loaded onto truck
Time 4584.018: Vessel 7 - Container 26 loaded onto truck
Time 4588.617: Vessel 8 - Truck transported container 25 to yard
Time 4588.617: Vessel 8 - Crane moved container 26
Time 4590.018: Vessel 7 - Truck transported container 26 to yard
Time 4590.018: Vessel 7 - Crane moved container 27
Time 4591.617: Vessel 8 - Container 26 loaded onto truck
Time 4593.018: Vessel 7 - Container 27 loaded onto truck
Time 4597.617: Vessel 8 - Truck transported container 26 to yard
Time 4597.617: Vessel 8 - Crane moved container 27
Time 4599.018: Vessel 7 - Truck transported container 27 to yard
Time 4599.018: Vessel 7 - Crane moved container 28
Time 4600.617: Vessel 8 - Container 27 loaded onto truck
Time 4602.018: Vessel 7 - Container 28 loaded onto truck
Time 4606.617: Vessel 8 - Truck transported container 27 to yard
Time 4606.617: Vessel 8 - Crane moved container 28
Time 4608.018: Vessel 7 - Truck transported container 28 to yard
Time 4608.018: Vessel 7 - Crane moved container 29
Time 4609.617: Vessel 8 - Container 28 loaded onto truck
Time 4611.018: Vessel 7 - Container 29 loaded onto truck
Time 4615.617: Vessel 8 - Truck transported container 28 to yard
Time 4615.617: Vessel 8 - Crane moved container 29
Time 4617.018: Vessel 7 - Truck transported container 29 to yard
Time 4617.018: Vessel 7 - Crane moved container 30
Time 4618.617: Vessel 8 - Container 29 loaded onto truck
Time 4620.018: Vessel 7 - Container 30 loaded onto truck
Time 4624.617: Vessel 8 - Truck transported container 29 to yard
Time 4624.617: Vessel 8 - Crane moved container 30
Time 4626.018: Vessel 7 - Truck transported container 30 to yard
Time 4626.018: Vessel 7 - Crane moved container 31
Time 4627.617: Vessel 8 - Container 30 loaded onto truck
Time 4629.018: Vessel 7 - Container 31 loaded onto truck
Time 4633.617: Vessel 8 - Truck transported container 30 to yard
Time 4633.617: Vessel 8 - Crane moved container 31
Time 4635.018: Vessel 7 - Truck transported container 31 to yard
Time 4635.018: Vessel 7 - Crane moved container 32
Time 4636.617: Vessel 8 - Container 31 loaded onto truck
Time 4638.018: Vessel 7 - Container 32 loaded onto truck
Time 4642.617: Vessel 8 - Truck transported container 31 to yard
Time 4642.617: Vessel 8 - Crane moved container 32
Time 4644.018: Vessel 7 - Truck transported container 32 to yard
Time 4644.018: Vessel 7 - Crane moved container 33
Time 4645.617: Vessel 8 - Container 32 loaded onto truck
Time 4647.018: Vessel 7 - Container 33 loaded onto truck
Time 4651.617: Vessel 8 - Truck transported container 32 to yard
Time 4651.617: Vessel 8 - Crane moved container 33
Time 4653.018: Vessel 7 - Truck transported container 33 to yard
Time 4653.018: Vessel 7 - Crane moved container 34
Time 4654.617: Vessel 8 - Container 33 loaded onto truck
Time 4656.018: Vessel 7 - Container 34 loaded onto truck
Time 4660.617: Vessel 8 - Truck transported container 33 to yard
Time 4660.617: Vessel 8 - Crane moved container 34
Time 4662.018: Vessel 7 - Truck transported container 34 to yard
Time 4662.018: Vessel 7 - Crane moved container 35
Time 4663.617: Vessel 8 - Container 34 loaded onto truck
Time 4665.018: Vessel 7 - Container 35 loaded onto truck
Time 4669.617: Vessel 8 - Truck transported container 34 to yard
Time 4669.617: Vessel 8 - Crane moved container 35
Time 4671.018: Vessel 7 - Truck transported container 35 to yard
Time 4671.018: Vessel 7 - Crane moved container 36
Time 4672.617: Vessel 8 - Container 35 loaded onto truck
Time 4674.018: Vessel 7 - Container 36 loaded onto truck
Time 4678.617: Vessel 8 - Truck transported container 35 to yard
Time 4678.617: Vessel 8 - Crane moved container 36
Time 4680.018: Vessel 7 - Truck transported container 36 to yard
Time 4680.018: Vessel 7 - Crane moved container 37
Time 4681.617: Vessel 8 - Container 36 loaded onto truck
Time 4683.018: Vessel 7 - Container 37 loaded onto truck
Time 4687.617: Vessel 8 - Truck transported container 36 to yard
Time 4687.617: Vessel 8 - Crane moved container 37
Time 4689.018: Vessel 7 - Truck transported container 37 to yard
Time 4689.018: Vessel 7 - Crane moved container 38
Time 4690.617: Vessel 8 - Container 37 loaded onto truck
Time 4692.018: Vessel 7 - Container 38 loaded onto truck
Time 4696.437: Vessel 22 Arrived
Time 4696.437: Vessel 22 Waiting for a berth
Time 4696.617: Vessel 8 - Truck transported container 37 to yard
Time 4696.617: Vessel 8 - Crane moved container 38
Time 4698.018: Vessel 7 - Truck transported container 38 to yard
Time 4698.018: Vessel 7 - Crane moved container 39
Time 4699.617: Vessel 8 - Container 38 loaded onto truck
Time 4701.018: Vessel 7 - Container 39 loaded onto truck
Time 4705.617: Vessel 8 - Truck transported container 38 to yard
Time 4705.617: Vessel 8 - Crane moved container 39
Time 4707.018: Vessel 7 - Truck transported container 39 to yard
Time 4707.018: Vessel 7 - Crane moved container 40
Time 4708.617: Vessel 8 - Container 39 loaded onto truck
Time 4710.018: Vessel 7 - Container 40 loaded onto truck
Time 4714.617: Vessel 8 - Truck transported container 39 to yard
Time 4714.617: Vessel 8 - Crane moved container 40
Time 4716.018: Vessel 7 - Truck transported container 40 to yard
Time 4716.018: Vessel 7 - Crane moved container 41
Time 4717.617: Vessel 8 - Container 40 loaded onto truck
Time 4719.018: Vessel 7 - Container 41 loaded onto truck
Time 4723.617: Vessel 8 - Truck transported container 40 to yard
Time 4723.617: Vessel 8 - Crane moved container 41
Time 4725.018: Vessel 7 - Truck transported container 41 to yard
Time 4725.018: Vessel 7 - Crane moved container 42
Time 4726.617: Vessel 8 - Container 41 loaded onto truck
Time 4728.018: Vessel 7 - Container 42 loaded onto truck
Time 4732.617: Vessel 8 - Truck transported container 41 to yard
Time 4732.617: Vessel 8 - Crane moved container 42
Time 4734.018: Vessel 7 - Truck transported container 42 to yard
Time 4734.018: Vessel 7 - Crane moved container 43
Time 4735.617: Vessel 8 - Container 42 loaded onto truck
Time 4737.018: Vessel 7 - Container 43 loaded onto truck
Time 4741.617: Vessel 8 - Truck transported container 42 to yard
Time 4741.617: Vessel 8 - Crane moved container 43
Time 4743.018: Vessel 7 - Truck transported container 43 to yard
Time 4743.018: Vessel 7 - Crane moved container 44
Time 4744.617: Vessel 8 - Container 43 loaded onto truck
Time 4746.018: Vessel 7 - Container 44 loaded onto truck
Time 4750.617: Vessel 8 - Truck transported container 43 to yard
Time 4750.617: Vessel 8 - Crane moved container 44
Time 4752.018: Vessel 7 - Truck transported container 44 to yard
Time 4752.018: Vessel 7 - Crane moved container 45
Time 4753.617: Vessel 8 - Container 44 loaded onto truck
Time 4755.018: Vessel 7 - Container 45 loaded onto truck
Time 4759.617: Vessel 8 - Truck transported container 44 to yard
Time 4759.617: Vessel 8 - Crane moved container 45
Time 4761.018: Vessel 7 - Truck transported container 45 to yard
Time 4761.018: Vessel 7 - Crane moved container 46
Time 4762.617: Vessel 8 - Container 45 loaded onto truck
Time 4764.018: Vessel 7 - Container 46 loaded onto truck
Time 4768.617: Vessel 8 - Truck transported container 45 to yard
Time 4768.617: Vessel 8 - Crane moved container 46
Time 4770.018: Vessel 7 - Truck transported container 46 to yard
Time 4770.018: Vessel 7 - Crane moved container 47
Time 4771.617: Vessel 8 - Container 46 loaded onto truck
Time 4773.018: Vessel 7 - Container 47 loaded onto truck
Time 4777.617: Vessel 8 - Truck transported container 46 to yard
Time 4777.617: Vessel 8 - Crane moved container 47
Time 4779.018: Vessel 7 - Truck transported container 47 to yard
Time 4779.018: Vessel 7 - Crane moved container 48
Time 4780.617: Vessel 8 - Container 47 loaded onto truck
Time 4782.018: Vessel 7 - Container 48 loaded onto truck
Time 4786.617: Vessel 8 - Truck transported container 47 to yard
Time 4786.617: Vessel 8 - Crane moved container 48
Time 4788.018: Vessel 7 - Truck transported container 48 to yard
Time 4788.018: Vessel 7 - Crane moved container 49
Time 4789.617: Vessel 8 - Container 48 loaded onto truck
Time 4791.018: Vessel 7 - Container 49 loaded onto truck
Time 4795.617: Vessel 8 - Truck transported container 48 to yard
Time 4795.617: Vessel 8 - Crane moved container 49
Time 4797.018: Vessel 7 - Truck transported container 49 to yard
Time 4797.018: Vessel 7 - Crane moved container 50
Time 4798.617: Vessel 8 - Container 49 loaded onto truck
Time 4800.018: Vessel 7 - Container 50 loaded onto truck
Time 4804.617: Vessel 8 - Truck transported container 49 to yard
Time 4804.617: Vessel 8 - Crane moved container 50
Time 4806.018: Vessel 7 - Truck transported container 50 to yard
Time 4806.018: Vessel 7 - Crane moved container 51
Time 4807.617: Vessel 8 - Container 50 loaded onto truck
Time 4809.018: Vessel 7 - Container 51 loaded onto truck
Time 4813.617: Vessel 8 - Truck transported container 50 to yard
Time 4813.617: Vessel 8 - Crane moved container 51
Time 4815.018: Vessel 7 - Truck transported container 51 to yard
Time 4815.018: Vessel 7 - Crane moved container 52
Time 4816.617: Vessel 8 - Container 51 loaded onto truck
Time 4818.018: Vessel 7 - Container 52 loaded onto truck
Time 4821.206: Vessel 23 Arrived
Time 4821.206: Vessel 23 Waiting for a berth
Time 4822.617: Vessel 8 - Truck transported container 51 to yard
Time 4822.617: Vessel 8 - Crane moved container 52
Time 4824.018: Vessel 7 - Truck transported container 52 to yard
Time 4824.018: Vessel 7 - Crane moved container 53
Time 4825.617: Vessel 8 - Container 52 loaded onto truck
Time 4827.018: Vessel 7 - Container 53 loaded onto truck
Time 4831.617: Vessel 8 - Truck transported container 52 to yard
Time 4831.617: Vessel 8 - Crane moved container 53
Time 4833.018: Vessel 7 - Truck transported container 53 to yard
Time 4833.018: Vessel 7 - Crane moved container 54
Time 4834.617: Vessel 8 - Container 53 loaded onto truck
Time 4836.018: Vessel 7 - Container 54 loaded onto truck
Time 4840.617: Vessel 8 - Truck transported container 53 to yard
Time 4840.617: Vessel 8 - Crane moved container 54
Time 4842.018: Vessel 7 - Truck transported container 54 to yard
Time 4842.018: Vessel 7 - Crane moved container 55
Time 4843.617: Vessel 8 - Container 54 loaded onto truck
Time 4845.018: Vessel 7 - Container 55 loaded onto truck
Time 4849.617: Vessel 8 - Truck transported container 54 to yard
Time 4849.617: Vessel 8 - Crane moved container 55
Time 4851.018: Vessel 7 - Truck transported container 55 to yard
Time 4851.018: Vessel 7 - Crane moved container 56
Time 4852.617: Vessel 8 - Container 55 loaded onto truck
Time 4854.018: Vessel 7 - Container 56 loaded onto truck
Time 4858.617: Vessel 8 - Truck transported container 55 to yard
Time 4858.617: Vessel 8 - Crane moved container 56
Time 4860.018: Vessel 7 - Truck transported container 56 to yard
Time 4860.018: Vessel 7 - Crane moved container 57
Time 4861.617: Vessel 8 - Container 56 loaded onto truck
Time 4863.018: Vessel 7 - Container 57 loaded onto truck
Time 4867.617: Vessel 8 - Truck transported container 56 to yard
Time 4867.617: Vessel 8 - Crane moved container 57
Time 4869.018: Vessel 7 - Truck transported container 57 to yard
Time 4869.018: Vessel 7 - Crane moved container 58
Time 4870.617: Vessel 8 - Container 57 loaded onto truck
Time 4871.902: Vessel 24 Arrived
Time 4871.902: Vessel 24 Waiting for a berth
Time 4872.018: Vessel 7 - Container 58 loaded onto truck
Time 4876.617: Vessel 8 - Truck transported container 57 to yard
Time 4876.617: Vessel 8 - Crane moved container 58
Time 4878.018: Vessel 7 - Truck transported container 58 to yard
Time 4878.018: Vessel 7 - Crane moved container 59
Time 4879.617: Vessel 8 - Container 58 loaded onto truck
Time 4881.018: Vessel 7 - Container 59 loaded onto truck
Time 4885.617: Vessel 8 - Truck transported container 58 to yard
Time 4885.617: Vessel 8 - Crane moved container 59
Time 4887.018: Vessel 7 - Truck transported container 59 to yard
Time 4887.018: Vessel 7 - Crane moved container 60
Time 4888.617: Vessel 8 - Container 59 loaded onto truck
Time 4890.018: Vessel 7 - Container 60 loaded onto truck
Time 4894.617: Vessel 8 - Truck transported container 59 to yard
Time 4894.617: Vessel 8 - Crane moved container 60
Time 4896.018: Vessel 7 - Truck transported container 60 to yard
Time 4896.018: Vessel 7 - Crane moved container 61
Time 4897.617: Vessel 8 - Container 60 loaded onto truck
Time 4899.018: Vessel 7 - Container 61 loaded onto truck
Time 4903.617: Vessel 8 - Truck transported container 60 to yard
Time 4903.617: Vessel 8 - Crane moved container 61
Time 4905.018: Vessel 7 - Truck transported container 61 to yard
Time 4905.018: Vessel 7 - Crane moved container 62
Time 4906.617: Vessel 8 - Container 61 loaded onto truck
Time 4908.018: Vessel 7 - Container 62 loaded onto truck
Time 4912.617: Vessel 8 - Truck transported container 61 to yard
Time 4912.617: Vessel 8 - Crane moved container 62
Time 4914.018: Vessel 7 - Truck transported container 62 to yard
Time 4914.018: Vessel 7 - Crane moved container 63
Time 4915.617: Vessel 8 - Container 62 loaded onto truck
Time 4917.018: Vessel 7 - Container 63 loaded onto truck
Time 4921.617: Vessel 8 - Truck transported container 62 to yard
Time 4921.617: Vessel 8 - Crane moved container 63
Time 4923.018: Vessel 7 - Truck transported container 63 to yard
Time 4923.018: Vessel 7 - Crane moved container 64
Time 4924.617: Vessel 8 - Container 63 loaded onto truck
Time 4926.018: Vessel 7 - Container 64 loaded onto truck
Time 4930.617: Vessel 8 - Truck transported container 63 to yard
Time 4930.617: Vessel 8 - Crane moved container 64
Time 4932.018: Vessel 7 - Truck transported container 64 to yard
Time 4932.018: Vessel 7 - Crane moved container 65
Time 4933.617: Vessel 8 - Container 64 loaded onto truck
Time 4935.018: Vessel 7 - Container 65 loaded onto truck
Time 4939.617: Vessel 8 - Truck transported container 64 to yard
Time 4939.617: Vessel 8 - Crane moved container 65
Time 4941.018: Vessel 7 - Truck transported container 65 to yard
Time 4941.018: Vessel 7 - Crane moved container 66
Time 4942.617: Vessel 8 - Container 65 loaded onto truck
Time 4944.018: Vessel 7 - Container 66 loaded onto truck
Time 4948.617: Vessel 8 - Truck transported container 65 to yard
Time 4948.617: Vessel 8 - Crane moved container 66
Time 4950.018: Vessel 7 - Truck transported container 66 to yard
Time 4950.018: Vessel 7 - Crane moved container 67
Time 4951.617: Vessel 8 - Container 66 loaded onto truck
Time 4953.018: Vessel 7 - Container 67 loaded onto truck
Time 4957.617: Vessel 8 - Truck transported container 66 to yard
Time 4957.617: Vessel 8 - Crane moved container 67
Time 4959.018: Vessel 7 - Truck transported container 67 to yard
Time 4959.018: Vessel 7 - Crane moved container 68
Time 4960.617: Vessel 8 - Container 67 loaded onto truck
Time 4962.018: Vessel 7 - Container 68 loaded onto truck
Time 4966.617: Vessel 8 - Truck transported container 67 to yard
Time 4966.617: Vessel 8 - Crane moved container 68
Time 4968.018: Vessel 7 - Truck transported container 68 to yard
Time 4968.018: Vessel 7 - Crane moved container 69
Time 4969.617: Vessel 8 - Container 68 loaded onto truck
Time 4971.018: Vessel 7 - Container 69 loaded onto truck
Time 4975.617: Vessel 8 - Truck transported container 68 to yard
Time 4975.617: Vessel 8 - Crane moved container 69
Time 4977.018: Vessel 7 - Truck transported container 69 to yard
Time 4977.018: Vessel 7 - Crane moved container 70
Time 4978.617: Vessel 8 - Container 69 loaded onto truck
Time 4980.018: Vessel 7 - Container 70 loaded onto truck
Time 4984.617: Vessel 8 - Truck transported container 69 to yard
Time 4984.617: Vessel 8 - Crane moved container 70
Time 4986.018: Vessel 7 - Truck transported container 70 to yard
Time 4986.018: Vessel 7 - Crane moved container 71
Time 4987.617: Vessel 8 - Container 70 loaded onto truck
Time 4989.018: Vessel 7 - Container 71 loaded onto truck
Time 4993.617: Vessel 8 - Truck transported container 70 to yard
Time 4993.617: Vessel 8 - Crane moved container 71
Time 4995.018: Vessel 7 - Truck transported container 71 to yard
Time 4995.018: Vessel 7 - Crane moved container 72
Time 4996.617: Vessel 8 - Container 71 loaded onto truck
Time 4998.018: Vessel 7 - Container 72 loaded onto truck
Time 5002.617: Vessel 8 - Truck transported container 71 to yard
Time 5002.617: Vessel 8 - Crane moved container 72
Time 5004.018: Vessel 7 - Truck transported container 72 to yard
Time 5004.018: Vessel 7 - Crane moved container 73
Time 5005.617: Vessel 8 - Container 72 loaded onto truck
Time 5007.018: Vessel 7 - Container 73 loaded onto truck
Time 5011.617: Vessel 8 - Truck transported container 72 to yard
Time 5011.617: Vessel 8 - Crane moved container 73
Time 5013.018: Vessel 7 - Truck transported container 73 to yard
Time 5013.018: Vessel 7 - Crane moved container 74
Time 5014.617: Vessel 8 - Container 73 loaded onto truck
Time 5016.018: Vessel 7 - Container 74 loaded onto truck
Time 5020.617: Vessel 8 - Truck transported container 73 to yard
Time 5020.617: Vessel 8 - Crane moved container 74
Time 5022.018: Vessel 7 - Truck transported container 74 to yard
Time 5022.018: Vessel 7 - Crane moved container 75
Time 5023.617: Vessel 8 - Container 74 loaded onto truck
Time 5025.018: Vessel 7 - Container 75 loaded onto truck
Time 5029.617: Vessel 8 - Truck transported container 74 to yard
Time 5029.617: Vessel 8 - Crane moved container 75
Time 5031.018: Vessel 7 - Truck transported container 75 to yard
Time 5031.018: Vessel 7 - Crane moved container 76
Time 5032.617: Vessel 8 - Container 75 loaded onto truck
Time 5034.018: Vessel 7 - Container 76 loaded onto truck
Time 5038.617: Vessel 8 - Truck transported container 75 to yard
Time 5038.617: Vessel 8 - Crane moved container 76
Time 5040.018: Vessel 7 - Truck transported container 76 to yard
Time 5040.018: Vessel 7 - Crane moved container 77
Time 5041.617: Vessel 8 - Container 76 loaded onto truck
Time 5043.018: Vessel 7 - Container 77 loaded onto truck
Time 5047.617: Vessel 8 - Truck transported container 76 to yard
Time 5047.617: Vessel 8 - Crane moved container 77
Time 5049.018: Vessel 7 - Truck transported container 77 to yard
Time 5049.018: Vessel 7 - Crane moved container 78
Time 5050.617: Vessel 8 - Container 77 loaded onto truck
Time 5052.018: Vessel 7 - Container 78 loaded onto truck
Time 5056.617: Vessel 8 - Truck transported container 77 to yard
Time 5056.617: Vessel 8 - Crane moved container 78
Time 5058.018: Vessel 7 - Truck transported container 78 to yard
Time 5058.018: Vessel 7 - Crane moved container 79
Time 5059.617: Vessel 8 - Container 78 loaded onto truck
Time 5061.018: Vessel 7 - Container 79 loaded onto truck
Time 5065.617: Vessel 8 - Truck transported container 78 to yard
Time 5065.617: Vessel 8 - Crane moved container 79
Time 5067.018: Vessel 7 - Truck transported container 79 to yard
Time 5067.018: Vessel 7 - Crane moved container 80
Time 5068.617: Vessel 8 - Container 79 loaded onto truck
Time 5070.018: Vessel 7 - Container 80 loaded onto truck
Time 5074.617: Vessel 8 - Truck transported container 79 to yard
Time 5074.617: Vessel 8 - Crane moved container 80
Time 5076.018: Vessel 7 - Truck transported container 80 to yard
Time 5076.018: Vessel 7 - Crane moved container 81
Time 5077.617: Vessel 8 - Container 80 loaded onto truck
Time 5079.018: Vessel 7 - Container 81 loaded onto truck
Time 5083.617: Vessel 8 - Truck transported container 80 to yard
Time 5083.617: Vessel 8 - Crane moved container 81
Time 5085.018: Vessel 7 - Truck transported container 81 to yard
Time 5085.018: Vessel 7 - Crane moved container 82
Time 5086.617: Vessel 8 - Container 81 loaded onto truck
Time 5088.018: Vessel 7 - Container 82 loaded onto truck
Time 5092.617: Vessel 8 - Truck transported container 81 to yard
Time 5092.617: Vessel 8 - Crane moved container 82
Time 5094.018: Vessel 7 - Truck transported container 82 to yard
Time 5094.018: Vessel 7 - Crane moved container 83
Time 5095.617: Vessel 8 - Container 82 loaded onto truck
Time 5097.018: Vessel 7 - Container 83 loaded onto truck
Time 5101.617: Vessel 8 - Truck transported container 82 to yard
Time 5101.617: Vessel 8 - Crane moved container 83
Time 5103.018: Vessel 7 - Truck transported container 83 to yard
Time 5103.018: Vessel 7 - Crane moved container 84
Time 5104.617: Vessel 8 - Container 83 loaded onto truck
Time 5106.018: Vessel 7 - Container 84 loaded onto truck
Time 5110.617: Vessel 8 - Truck transported container 83 to yard
Time 5110.617: Vessel 8 - Crane moved container 84
Time 5112.018: Vessel 7 - Truck transported container 84 to yard
Time 5112.018: Vessel 7 - Crane moved container 85
Time 5113.617: Vessel 8 - Container 84 loaded onto truck
Time 5115.018: Vessel 7 - Container 85 loaded onto truck
Time 5119.617: Vessel 8 - Truck transported container 84 to yard
Time 5119.617: Vessel 8 - Crane moved container 85
Time 5121.018: Vessel 7 - Truck transported container 85 to yard
Time 5121.018: Vessel 7 - Crane moved container 86
Time 5122.617: Vessel 8 - Container 85 loaded onto truck
Time 5124.018: Vessel 7 - Container 86 loaded onto truck
Time 5128.617: Vessel 8 - Truck transported container 85 to yard
Time 5128.617: Vessel 8 - Crane moved container 86
Time 5130.018: Vessel 7 - Truck transported container 86 to yard
Time 5130.018: Vessel 7 - Crane moved container 87
Time 5131.617: Vessel 8 - Container 86 loaded onto truck
Time 5133.018: Vessel 7 - Container 87 loaded onto truck
Time 5137.617: Vessel 8 - Truck transported container 86 to yard
Time 5137.617: Vessel 8 - Crane moved container 87
Time 5139.018: Vessel 7 - Truck transported container 87 to yard
Time 5139.018: Vessel 7 - Crane moved container 88
Time 5140.617: Vessel 8 - Container 87 loaded onto truck
Time 5142.018: Vessel 7 - Container 88 loaded onto truck
Time 5146.617: Vessel 8 - Truck transported container 87 to yard
Time 5146.617: Vessel 8 - Crane moved container 88
Time 5148.018: Vessel 7 - Truck transported container 88 to yard
Time 5148.018: Vessel 7 - Crane moved container 89
Time 5149.617: Vessel 8 - Container 88 loaded onto truck
Time 5151.018: Vessel 7 - Container 89 loaded onto truck
Time 5155.617: Vessel 8 - Truck transported container 88 to yard
Time 5155.617: Vessel 8 - Crane moved container 89
Time 5157.018: Vessel 7 - Truck transported container 89 to yard
Time 5157.018: Vessel 7 - Crane moved container 90
Time 5158.617: Vessel 8 - Container 89 loaded onto truck
Time 5160.018: Vessel 7 - Container 90 loaded onto truck
Time 5164.617: Vessel 8 - Truck transported container 89 to yard
Time 5164.617: Vessel 8 - Crane moved container 90
Time 5166.018: Vessel 7 - Truck transported container 90 to yard
Time 5166.018: Vessel 7 - Crane moved container 91
Time 5167.617: Vessel 8 - Container 90 loaded onto truck
Time 5169.018: Vessel 7 - Container 91 loaded onto truck
Time 5173.617: Vessel 8 - Truck transported container 90 to yard
Time 5173.617: Vessel 8 - Crane moved container 91
Time 5175.018: Vessel 7 - Truck transported container 91 to yard
Time 5175.018: Vessel 7 - Crane moved container 92
Time 5176.617: Vessel 8 - Container 91 loaded onto truck
Time 5178.018: Vessel 7 - Container 92 loaded onto truck
Time 5182.617: Vessel 8 - Truck transported container 91 to yard
Time 5182.617: Vessel 8 - Crane moved container 92
Time 5184.018: Vessel 7 - Truck transported container 92 to yard
Time 5184.018: Vessel 7 - Crane moved container 93
Time 5185.617: Vessel 8 - Container 92 loaded onto truck
Time 5187.018: Vessel 7 - Container 93 loaded onto truck
Time 5191.617: Vessel 8 - Truck transported container 92 to yard
Time 5191.617: Vessel 8 - Crane moved container 93
Time 5193.018: Vessel 7 - Truck transported container 93 to yard
Time 5193.018: Vessel 7 - Crane moved container 94
Time 5194.617: Vessel 8 - Container 93 loaded onto truck
Time 5196.018: Vessel 7 - Container 94 loaded onto truck
Time 5200.617: Vessel 8 - Truck transported container 93 to yard
Time 5200.617: Vessel 8 - Crane moved container 94
Time 5202.018: Vessel 7 - Truck transported container 94 to yard
Time 5202.018: Vessel 7 - Crane moved container 95
Time 5203.617: Vessel 8 - Container 94 loaded onto truck
Time 5205.018: Vessel 7 - Container 95 loaded onto truck
Time 5209.617: Vessel 8 - Truck transported container 94 to yard
Time 5209.617: Vessel 8 - Crane moved container 95
Time 5211.018: Vessel 7 - Truck transported container 95 to yard
Time 5211.018: Vessel 7 - Crane moved container 96
Time 5212.617: Vessel 8 - Container 95 loaded onto truck
Time 5214.018: Vessel 7 - Container 96 loaded onto truck
Time 5218.617: Vessel 8 - Truck transported container 95 to yard
Time 5218.617: Vessel 8 - Crane moved container 96
Time 5220.018: Vessel 7 - Truck transported container 96 to yard
Time 5220.018: Vessel 7 - Crane moved container 97
Time 5221.617: Vessel 8 - Container 96 loaded onto truck
Time 5223.018: Vessel 7 - Container 97 loaded onto truck
Time 5227.617: Vessel 8 - Truck transported container 96 to yard
Time 5227.617: Vessel 8 - Crane moved container 97
Time 5229.018: Vessel 7 - Truck transported container 97 to yard
Time 5229.018: Vessel 7 - Crane moved container 98
Time 5230.617: Vessel 8 - Container 97 loaded onto truck
Time 5232.018: Vessel 7 - Container 98 loaded onto truck
Time 5236.617: Vessel 8 - Truck transported container 97 to yard
Time 5236.617: Vessel 8 - Crane moved container 98
Time 5238.018: Vessel 7 - Truck transported container 98 to yard
Time 5238.018: Vessel 7 - Crane moved container 99
Time 5239.617: Vessel 8 - Container 98 loaded onto truck
Time 5241.018: Vessel 7 - Container 99 loaded onto truck
Time 5245.617: Vessel 8 - Truck transported container 98 to yard
Time 5245.617: Vessel 8 - Crane moved container 99
Time 5247.018: Vessel 7 - Truck transported container 99 to yard
Time 5247.018: Vessel 7 - Crane moved container 100
Time 5248.617: Vessel 8 - Container 99 loaded onto truck
Time 5250.018: Vessel 7 - Container 100 loaded onto truck
Time 5254.617: Vessel 8 - Truck transported container 99 to yard
Time 5254.617: Vessel 8 - Crane moved container 100
Time 5256.018: Vessel 7 - Truck transported container 100 to yard
Time 5256.018: Vessel 7 - Crane moved container 101
Time 5257.617: Vessel 8 - Container 100 loaded onto truck
Time 5259.018: Vessel 7 - Container 101 loaded onto truck
Time 5263.617: Vessel 8 - Truck transported container 100 to yard
Time 5263.617: Vessel 8 - Crane moved container 101
Time 5265.018: Vessel 7 - Truck transported container 101 to yard
Time 5265.018: Vessel 7 - Crane moved container 102
Time 5266.617: Vessel 8 - Container 101 loaded onto truck
Time 5268.018: Vessel 7 - Container 102 loaded onto truck
Time 5272.617: Vessel 8 - Truck transported container 101 to yard
Time 5272.617: Vessel 8 - Crane moved container 102
Time 5274.018: Vessel 7 - Truck transported container 102 to yard
Time 5274.018: Vessel 7 - Crane moved container 103
Time 5275.617: Vessel 8 - Container 102 loaded onto truck
Time 5277.018: Vessel 7 - Container 103 loaded onto truck
Time 5281.617: Vessel 8 - Truck transported container 102 to yard
Time 5281.617: Vessel 8 - Crane moved container 103
Time 5283.018: Vessel 7 - Truck transported container 103 to yard
Time 5283.018: Vessel 7 - Crane moved container 104
Time 5284.617: Vessel 8 - Container 103 loaded onto truck
Time 5286.018: Vessel 7 - Container 104 loaded onto truck
Time 5290.617: Vessel 8 - Truck transported container 103 to yard
Time 5290.617: Vessel 8 - Crane moved container 104
Time 5292.018: Vessel 7 - Truck transported container 104 to yard
Time 5292.018: Vessel 7 - Crane moved container 105
Time 5293.617: Vessel 8 - Container 104 loaded onto truck
Time 5295.018: Vessel 7 - Container 105 loaded onto truck
Time 5299.617: Vessel 8 - Truck transported container 104 to yard
Time 5299.617: Vessel 8 - Crane moved container 105
Time 5301.018: Vessel 7 - Truck transported container 105 to yard
Time 5301.018: Vessel 7 - Crane moved container 106
Time 5302.617: Vessel 8 - Container 105 loaded onto truck
Time 5304.018: Vessel 7 - Container 106 loaded onto truck
Time 5308.617: Vessel 8 - Truck transported container 105 to yard
Time 5308.617: Vessel 8 - Crane moved container 106
Time 5310.018: Vessel 7 - Truck transported container 106 to yard
Time 5310.018: Vessel 7 - Crane moved container 107
Time 5311.617: Vessel 8 - Container 106 loaded onto truck
Time 5313.018: Vessel 7 - Container 107 loaded onto truck
Time 5317.617: Vessel 8 - Truck transported container 106 to yard
Time 5317.617: Vessel 8 - Crane moved container 107
Time 5319.018: Vessel 7 - Truck transported container 107 to yard
Time 5319.018: Vessel 7 - Crane moved container 108
Time 5320.617: Vessel 8 - Container 107 loaded onto truck
Time 5322.018: Vessel 7 - Container 108 loaded onto truck
Time 5326.617: Vessel 8 - Truck transported container 107 to yard
Time 5326.617: Vessel 8 - Crane moved container 108
Time 5328.018: Vessel 7 - Truck transported container 108 to yard
Time 5328.018: Vessel 7 - Crane moved container 109
Time 5329.617: Vessel 8 - Container 108 loaded onto truck
Time 5331.018: Vessel 7 - Container 109 loaded onto truck
Time 5335.617: Vessel 8 - Truck transported container 108 to yard
Time 5335.617: Vessel 8 - Crane moved container 109
Time 5337.018: Vessel 7 - Truck transported container 109 to yard
Time 5337.018: Vessel 7 - Crane moved container 110
Time 5338.617: Vessel 8 - Container 109 loaded onto truck
Time 5340.018: Vessel 7 - Container 110 loaded onto truck
Time 5344.617: Vessel 8 - Truck transported container 109 to yard
Time 5344.617: Vessel 8 - Crane moved container 110
Time 5346.018: Vessel 7 - Truck transported container 110 to yard
Time 5346.018: Vessel 7 - Crane moved container 111
Time 5347.617: Vessel 8 - Container 110 loaded onto truck
Time 5349.018: Vessel 7 - Container 111 loaded onto truck
Time 5353.617: Vessel 8 - Truck transported container 110 to yard
Time 5353.617: Vessel 8 - Crane moved container 111
Time 5355.018: Vessel 7 - Truck transported container 111 to yard
Time 5355.018: Vessel 7 - Crane moved container 112
Time 5356.617: Vessel 8 - Container 111 loaded onto truck
Time 5358.018: Vessel 7 - Container 112 loaded onto truck
Time 5362.617: Vessel 8 - Truck transported container 111 to yard
Time 5362.617: Vessel 8 - Crane moved container 112
Time 5364.018: Vessel 7 - Truck transported container 112 to yard
Time 5364.018: Vessel 7 - Crane moved container 113
Time 5365.617: Vessel 8 - Container 112 loaded onto truck
Time 5367.018: Vessel 7 - Container 113 loaded onto truck
Time 5371.617: Vessel 8 - Truck transported container 112 to yard
Time 5371.617: Vessel 8 - Crane moved container 113
Time 5373.018: Vessel 7 - Truck transported container 113 to yard
Time 5373.018: Vessel 7 - Crane moved container 114
Time 5374.617: Vessel 8 - Container 113 loaded onto truck
Time 5376.018: Vessel 7 - Container 114 loaded onto truck
Time 5380.617: Vessel 8 - Truck transported container 113 to yard
Time 5380.617: Vessel 8 - Crane moved container 114
Time 5382.018: Vessel 7 - Truck transported container 114 to yard
Time 5382.018: Vessel 7 - Crane moved container 115
Time 5383.617: Vessel 8 - Container 114 loaded onto truck
Time 5385.018: Vessel 7 - Container 115 loaded onto truck
Time 5389.617: Vessel 8 - Truck transported container 114 to yard
Time 5389.617: Vessel 8 - Crane moved container 115
Time 5391.018: Vessel 7 - Truck transported container 115 to yard
Time 5391.018: Vessel 7 - Crane moved container 116
Time 5392.617: Vessel 8 - Container 115 loaded onto truck
Time 5394.018: Vessel 7 - Container 116 loaded onto truck
Time 5398.617: Vessel 8 - Truck transported container 115 to yard
Time 5398.617: Vessel 8 - Crane moved container 116
Time 5400.018: Vessel 7 - Truck transported container 116 to yard
Time 5400.018: Vessel 7 - Crane moved container 117
Time 5401.617: Vessel 8 - Container 116 loaded onto truck
Time 5403.018: Vessel 7 - Container 117 loaded onto truck
Time 5407.617: Vessel 8 - Truck transported container 116 to yard
Time 5407.617: Vessel 8 - Crane moved container 117
Time 5409.018: Vessel 7 - Truck transported container 117 to yard
Time 5409.018: Vessel 7 - Crane moved container 118
Time 5410.617: Vessel 8 - Container 117 loaded onto truck
Time 5412.018: Vessel 7 - Container 118 loaded onto truck
Time 5416.617: Vessel 8 - Truck transported container 117 to yard
Time 5416.617: Vessel 8 - Crane moved container 118
Time 5418.018: Vessel 7 - Truck transported container 118 to yard
Time 5418.018: Vessel 7 - Crane moved container 119
Time 5419.617: Vessel 8 - Container 118 loaded onto truck
Time 5421.018: Vessel 7 - Container 119 loaded onto truck
Time 5425.617: Vessel 8 - Truck transported container 118 to yard
Time 5425.617: Vessel 8 - Crane moved container 119
Time 5427.018: Vessel 7 - Truck transported container 119 to yard
Time 5427.018: Vessel 7 - Crane moved container 120
Time 5428.617: Vessel 8 - Container 119 loaded onto truck
Time 5430.018: Vessel 7 - Container 120 loaded onto truck
Time 5434.617: Vessel 8 - Truck transported container 119 to yard
Time 5434.617: Vessel 8 - Crane moved container 120
Time 5436.018: Vessel 7 - Truck transported container 120 to yard
Time 5436.018: Vessel 7 - Crane moved container 121
Time 5437.617: Vessel 8 - Container 120 loaded onto truck
Time 5439.018: Vessel 7 - Container 121 loaded onto truck
Time 5443.617: Vessel 8 - Truck transported container 120 to yard
Time 5443.617: Vessel 8 - Crane moved container 121
Time 5445.018: Vessel 7 - Truck transported container 121 to yard
Time 5445.018: Vessel 7 - Crane moved container 122
Time 5446.617: Vessel 8 - Container 121 loaded onto truck
Time 5448.018: Vessel 7 - Container 122 loaded onto truck
Time 5452.617: Vessel 8 - Truck transported container 121 to yard
Time 5452.617: Vessel 8 - Crane moved container 122
Time 5454.018: Vessel 7 - Truck transported container 122 to yard
Time 5454.018: Vessel 7 - Crane moved container 123
Time 5455.617: Vessel 8 - Container 122 loaded onto truck
Time 5457.018: Vessel 7 - Container 123 loaded onto truck
Time 5461.617: Vessel 8 - Truck transported container 122 to yard
Time 5461.617: Vessel 8 - Crane moved container 123
Time 5463.018: Vessel 7 - Truck transported container 123 to yard
Time 5463.018: Vessel 7 - Crane moved container 124
Time 5464.617: Vessel 8 - Container 123 loaded onto truck
Time 5466.018: Vessel 7 - Container 124 loaded onto truck
Time 5470.617: Vessel 8 - Truck transported container 123 to yard
Time 5470.617: Vessel 8 - Crane moved container 124
Time 5472.018: Vessel 7 - Truck transported container 124 to yard
Time 5472.018: Vessel 7 - Crane moved container 125
Time 5473.617: Vessel 8 - Container 124 loaded onto truck
Time 5475.018: Vessel 7 - Container 125 loaded onto truck
Time 5479.617: Vessel 8 - Truck transported container 124 to yard
Time 5479.617: Vessel 8 - Crane moved container 125
Time 5481.018: Vessel 7 - Truck transported container 125 to yard
Time 5481.018: Vessel 7 - Crane moved container 126
Time 5482.617: Vessel 8 - Container 125 loaded onto truck
Time 5484.018: Vessel 7 - Container 126 loaded onto truck
Time 5488.617: Vessel 8 - Truck transported container 125 to yard
Time 5488.617: Vessel 8 - Crane moved container 126
Time 5490.018: Vessel 7 - Truck transported container 126 to yard
Time 5490.018: Vessel 7 - Crane moved container 127
Time 5491.617: Vessel 8 - Container 126 loaded onto truck
Time 5493.018: Vessel 7 - Container 127 loaded onto truck
Time 5497.617: Vessel 8 - Truck transported container 126 to yard
Time 5497.617: Vessel 8 - Crane moved container 127
Time 5499.018: Vessel 7 - Truck transported container 127 to yard
Time 5499.018: Vessel 7 - Crane moved container 128
Time 5500.617: Vessel 8 - Container 127 loaded onto truck
Time 5502.018: Vessel 7 - Container 128 loaded onto truck
Time 5506.617: Vessel 8 - Truck transported container 127 to yard
Time 5506.617: Vessel 8 - Crane moved container 128
Time 5508.018: Vessel 7 - Truck transported container 128 to yard
Time 5508.018: Vessel 7 - Crane moved container 129
Time 5509.617: Vessel 8 - Container 128 loaded onto truck
Time 5511.018: Vessel 7 - Container 129 loaded onto truck
Time 5515.617: Vessel 8 - Truck transported container 128 to yard
Time 5515.617: Vessel 8 - Crane moved container 129
Time 5517.018: Vessel 7 - Truck transported container 129 to yard
Time 5517.018: Vessel 7 - Crane moved container 130
Time 5518.617: Vessel 8 - Container 129 loaded onto truck
Time 5520.018: Vessel 7 - Container 130 loaded onto truck
Time 5524.617: Vessel 8 - Truck transported container 129 to yard
Time 5524.617: Vessel 8 - Crane moved container 130
Time 5526.018: Vessel 7 - Truck transported container 130 to yard
Time 5526.018: Vessel 7 - Crane moved container 131
Time 5527.617: Vessel 8 - Container 130 loaded onto truck
Time 5529.018: Vessel 7 - Container 131 loaded onto truck
Time 5533.617: Vessel 8 - Truck transported container 130 to yard
Time 5533.617: Vessel 8 - Crane moved container 131
Time 5535.018: Vessel 7 - Truck transported container 131 to yard
Time 5535.018: Vessel 7 - Crane moved container 132
Time 5536.617: Vessel 8 - Container 131 loaded onto truck
Time 5538.018: Vessel 7 - Container 132 loaded onto truck
Time 5542.617: Vessel 8 - Truck transported container 131 to yard
Time 5542.617: Vessel 8 - Crane moved container 132
Time 5544.018: Vessel 7 - Truck transported container 132 to yard
Time 5544.018: Vessel 7 - Crane moved container 133
Time 5545.617: Vessel 8 - Container 132 loaded onto truck
Time 5547.018: Vessel 7 - Container 133 loaded onto truck
Time 5551.617: Vessel 8 - Truck transported container 132 to yard
Time 5551.617: Vessel 8 - Crane moved container 133
Time 5553.018: Vessel 7 - Truck transported container 133 to yard
Time 5553.018: Vessel 7 - Crane moved container 134
Time 5554.617: Vessel 8 - Container 133 loaded onto truck
Time 5556.018: Vessel 7 - Container 134 loaded onto truck
Time 5560.617: Vessel 8 - Truck transported container 133 to yard
Time 5560.617: Vessel 8 - Crane moved container 134
Time 5562.018: Vessel 7 - Truck transported container 134 to yard
Time 5562.018: Vessel 7 - Crane moved container 135
Time 5563.617: Vessel 8 - Container 134 loaded onto truck
Time 5565.018: Vessel 7 - Container 135 loaded onto truck
Time 5569.617: Vessel 8 - Truck transported container 134 to yard
Time 5569.617: Vessel 8 - Crane moved container 135
Time 5571.018: Vessel 7 - Truck transported container 135 to yard
Time 5571.018: Vessel 7 - Crane moved container 136
Time 5572.617: Vessel 8 - Container 135 loaded onto truck
Time 5574.018: Vessel 7 - Container 136 loaded onto truck
Time 5578.617: Vessel 8 - Truck transported container 135 to yard
Time 5578.617: Vessel 8 - Crane moved container 136
Time 5580.018: Vessel 7 - Truck transported container 136 to yard
Time 5580.018: Vessel 7 - Crane moved container 137
Time 5581.617: Vessel 8 - Container 136 loaded onto truck
Time 5583.018: Vessel 7 - Container 137 loaded onto truck
Time 5587.617: Vessel 8 - Truck transported container 136 to yard
Time 5587.617: Vessel 8 - Crane moved container 137
Time 5589.018: Vessel 7 - Truck transported container 137 to yard
Time 5589.018: Vessel 7 - Crane moved container 138
Time 5590.617: Vessel 8 - Container 137 loaded onto truck
Time 5592.018: Vessel 7 - Container 138 loaded onto truck
Time 5596.617: Vessel 8 - Truck transported container 137 to yard
Time 5596.617: Vessel 8 - Crane moved container 138
Time 5598.018: Vessel 7 - Truck transported container 138 to yard
Time 5598.018: Vessel 7 - Crane moved container 139
Time 5599.617: Vessel 8 - Container 138 loaded onto truck
Time 5601.018: Vessel 7 - Container 139 loaded onto truck
Time 5605.617: Vessel 8 - Truck transported container 138 to yard
Time 5605.617: Vessel 8 - Crane moved container 139
Time 5607.018: Vessel 7 - Truck transported container 139 to yard
Time 5607.018: Vessel 7 - Crane moved container 140
Time 5608.617: Vessel 8 - Container 139 loaded onto truck
Time 5610.018: Vessel 7 - Container 140 loaded onto truck
Time 5614.617: Vessel 8 - Truck transported container 139 to yard
Time 5614.617: Vessel 8 - Crane moved container 140
Time 5616.018: Vessel 7 - Truck transported container 140 to yard
Time 5616.018: Vessel 7 - Crane moved container 141
Time 5617.617: Vessel 8 - Container 140 loaded onto truck
Time 5619.018: Vessel 7 - Container 141 loaded onto truck
Time 5623.617: Vessel 8 - Truck transported container 140 to yard
Time 5623.617: Vessel 8 - Crane moved container 141
Time 5625.018: Vessel 7 - Truck transported container 141 to yard
Time 5625.018: Vessel 7 - Crane moved container 142
Time 5626.617: Vessel 8 - Container 141 loaded onto truck
Time 5628.018: Vessel 7 - Container 142 loaded onto truck
Time 5632.617: Vessel 8 - Truck transported container 141 to yard
Time 5632.617: Vessel 8 - Crane moved container 142
Time 5634.018: Vessel 7 - Truck transported container 142 to yard
Time 5634.018: Vessel 7 - Crane moved container 143
Time 5635.617: Vessel 8 - Container 142 loaded onto truck
Time 5637.018: Vessel 7 - Container 143 loaded onto truck
Time 5641.617: Vessel 8 - Truck transported container 142 to yard
Time 5641.617: Vessel 8 - Crane moved container 143
Time 5643.018: Vessel 7 - Truck transported container 143 to yard
Time 5643.018: Vessel 7 - Crane moved container 144
Time 5644.617: Vessel 8 - Container 143 loaded onto truck
Time 5646.018: Vessel 7 - Container 144 loaded onto truck
Time 5650.617: Vessel 8 - Truck transported container 143 to yard
Time 5650.617: Vessel 8 - Crane moved container 144
Time 5652.018: Vessel 7 - Truck transported container 144 to yard
Time 5652.018: Vessel 7 - Crane moved container 145
Time 5653.617: Vessel 8 - Container 144 loaded onto truck
Time 5655.018: Vessel 7 - Container 145 loaded onto truck
Time 5659.617: Vessel 8 - Truck transported container 144 to yard
Time 5659.617: Vessel 8 - Crane moved container 145
Time 5661.018: Vessel 7 - Truck transported container 145 to yard
Time 5661.018: Vessel 7 - Crane moved container 146
Time 5662.617: Vessel 8 - Container 145 loaded onto truck
Time 5664.018: Vessel 7 - Container 146 loaded onto truck
Time 5668.617: Vessel 8 - Truck transported container 145 to yard
Time 5668.617: Vessel 8 - Crane moved container 146
Time 5670.018: Vessel 7 - Truck transported container 146 to yard
Time 5670.018: Vessel 7 - Crane moved container 147
Time 5671.617: Vessel 8 - Container 146 loaded onto truck
Time 5673.018: Vessel 7 - Container 147 loaded onto truck
Time 5677.617: Vessel 8 - Truck transported container 146 to yard
Time 5677.617: Vessel 8 - Crane moved container 147
Time 5679.018: Vessel 7 - Truck transported container 147 to yard
Time 5679.018: Vessel 7 - Crane moved container 148
Time 5680.617: Vessel 8 - Container 147 loaded onto truck
Time 5682.018: Vessel 7 - Container 148 loaded onto truck
Time 5686.617: Vessel 8 - Truck transported container 147 to yard
Time 5686.617: Vessel 8 - Crane moved container 148
Time 5688.018: Vessel 7 - Truck transported container 148 to yard
Time 5688.018: Vessel 7 - Crane moved container 149
Time 5689.617: Vessel 8 - Container 148 loaded onto truck
Time 5691.018: Vessel 7 - Container 149 loaded onto truck
Time 5695.617: Vessel 8 - Truck transported container 148 to yard
Time 5695.617: Vessel 8 - Crane moved container 149
Time 5697.018: Vessel 7 - Truck transported container 149 to yard
Time 5697.018: Vessel 7 - Crane moved container 150
Time 5698.617: Vessel 8 - Container 149 loaded onto truck
Time 5700.018: Vessel 7 - Container 150 loaded onto truck
Time 5704.617: Vessel 8 - Truck transported container 149 to yard
Time 5704.617: Vessel 8 - Crane moved container 150
Time 5706.018: Vessel 7 - Truck transported container 150 to yard
Time 5706.018: Vessel 7 finished unloading and leaves
Time 5706.018: Vessel 9 berthed
Time 5706.018: Vessel 9 - Crane allocated
Time 5706.018: Vessel 9 - Crane moved container 1
Time 5707.617: Vessel 8 - Container 150 loaded onto truck
Time 5709.018: Vessel 9 - Container 1 loaded onto truck
Time 5713.617: Vessel 8 - Truck transported container 150 to yard
Time 5713.617: Vessel 8 finished unloading and leaves
Time 5713.617: Vessel 10 berthed
Time 5713.617: Vessel 10 - Crane allocated
Time 5713.617: Vessel 10 - Crane moved container 1
Time 5715.018: Vessel 9 - Truck transported container 1 to yard
Time 5715.018: Vessel 9 - Crane moved container 2
Time 5716.617: Vessel 10 - Container 1 loaded onto truck
Time 5718.018: Vessel 9 - Container 2 loaded onto truck
Time 5722.617: Vessel 10 - Truck transported container 1 to yard
Time 5722.617: Vessel 10 - Crane moved container 2
Time 5724.018: Vessel 9 - Truck transported container 2 to yard
Time 5724.018: Vessel 9 - Crane moved container 3
Time 5725.617: Vessel 10 - Container 2 loaded onto truck
Time 5727.018: Vessel 9 - Container 3 loaded onto truck
Time 5731.617: Vessel 10 - Truck transported container 2 to yard
Time 5731.617: Vessel 10 - Crane moved container 3
Time 5733.018: Vessel 9 - Truck transported container 3 to yard
Time 5733.018: Vessel 9 - Crane moved container 4
Time 5734.617: Vessel 10 - Container 3 loaded onto truck
Time 5736.018: Vessel 9 - Container 4 loaded onto truck
Time 5740.617: Vessel 10 - Truck transported container 3 to yard
Time 5740.617: Vessel 10 - Crane moved container 4
Time 5742.018: Vessel 9 - Truck transported container 4 to yard
Time 5742.018: Vessel 9 - Crane moved container 5
Time 5743.617: Vessel 10 - Container 4 loaded onto truck
Time 5745.018: Vessel 9 - Container 5 loaded onto truck
Time 5749.617: Vessel 10 - Truck transported container 4 to yard
Time 5749.617: Vessel 10 - Crane moved container 5
Time 5751.018: Vessel 9 - Truck transported container 5 to yard
Time 5751.018: Vessel 9 - Crane moved container 6
Time 5752.617: Vessel 10 - Container 5 loaded onto truck
Time 5754.018: Vessel 9 - Container 6 loaded onto truck
Time 5758.617: Vessel 10 - Truck transported container 5 to yard
Time 5758.617: Vessel 10 - Crane moved container 6
Time 5760.018: Vessel 9 - Truck transported container 6 to yard
Time 5760.018: Vessel 9 - Crane moved container 7
Time 5761.617: Vessel 10 - Container 6 loaded onto truck
Time 5763.018: Vessel 9 - Container 7 loaded onto truck
Time 5767.617: Vessel 10 - Truck transported container 6 to yard
Time 5767.617: Vessel 10 - Crane moved container 7
Time 5769.018: Vessel 9 - Truck transported container 7 to yard
Time 5769.018: Vessel 9 - Crane moved container 8
Time 5770.617: Vessel 10 - Container 7 loaded onto truck
Time 5772.018: Vessel 9 - Container 8 loaded onto truck
Time 5776.617: Vessel 10 - Truck transported container 7 to yard
Time 5776.617: Vessel 10 - Crane moved container 8
Time 5778.018: Vessel 9 - Truck transported container 8 to yard
Time 5778.018: Vessel 9 - Crane moved container 9
Time 5779.617: Vessel 10 - Container 8 loaded onto truck
Time 5781.018: Vessel 9 - Container 9 loaded onto truck
Time 5785.617: Vessel 10 - Truck transported container 8 to yard
Time 5785.617: Vessel 10 - Crane moved container 9
Time 5787.018: Vessel 9 - Truck transported container 9 to yard
Time 5787.018: Vessel 9 - Crane moved container 10
Time 5788.617: Vessel 10 - Container 9 loaded onto truck
Time 5790.018: Vessel 9 - Container 10 loaded onto truck
Time 5794.617: Vessel 10 - Truck transported container 9 to yard
Time 5794.617: Vessel 10 - Crane moved container 10
Time 5796.018: Vessel 9 - Truck transported container 10 to yard
Time 5796.018: Vessel 9 - Crane moved container 11
Time 5797.617: Vessel 10 - Container 10 loaded onto truck
Time 5799.018: Vessel 9 - Container 11 loaded onto truck
Time 5803.617: Vessel 10 - Truck transported container 10 to yard
Time 5803.617: Vessel 10 - Crane moved container 11
Time 5805.018: Vessel 9 - Truck transported container 11 to yard
Time 5805.018: Vessel 9 - Crane moved container 12
Time 5806.617: Vessel 10 - Container 11 loaded onto truck
Time 5808.018: Vessel 9 - Container 12 loaded onto truck
Time 5812.617: Vessel 10 - Truck transported container 11 to yard
Time 5812.617: Vessel 10 - Crane moved container 12
Time 5814.018: Vessel 9 - Truck transported container 12 to yard
Time 5814.018: Vessel 9 - Crane moved container 13
Time 5815.617: Vessel 10 - Container 12 loaded onto truck
Time 5817.018: Vessel 9 - Container 13 loaded onto truck
Time 5817.358: Vessel 25 Arrived
Time 5817.358: Vessel 25 Waiting for a berth
Time 5821.617: Vessel 10 - Truck transported container 12 to yard
Time 5821.617: Vessel 10 - Crane moved container 13
Time 5823.018: Vessel 9 - Truck transported container 13 to yard
Time 5823.018: Vessel 9 - Crane moved container 14
Time 5824.617: Vessel 10 - Container 13 loaded onto truck
Time 5826.018: Vessel 9 - Container 14 loaded onto truck
Time 5830.617: Vessel 10 - Truck transported container 13 to yard
Time 5830.617: Vessel 10 - Crane moved container 14
Time 5832.018: Vessel 9 - Truck transported container 14 to yard
Time 5832.018: Vessel 9 - Crane moved container 15
Time 5833.617: Vessel 10 - Container 14 loaded onto truck
Time 5835.018: Vessel 9 - Container 15 loaded onto truck
Time 5839.617: Vessel 10 - Truck transported container 14 to yard
Time 5839.617: Vessel 10 - Crane moved container 15
Time 5841.018: Vessel 9 - Truck transported container 15 to yard
Time 5841.018: Vessel 9 - Crane moved container 16
Time 5842.617: Vessel 10 - Container 15 loaded onto truck
Time 5844.018: Vessel 9 - Container 16 loaded onto truck
Time 5848.617: Vessel 10 - Truck transported container 15 to yard
Time 5848.617: Vessel 10 - Crane moved container 16
Time 5850.018: Vessel 9 - Truck transported container 16 to yard
Time 5850.018: Vessel 9 - Crane moved container 17
Time 5851.617: Vessel 10 - Container 16 loaded onto truck
Time 5853.018: Vessel 9 - Container 17 loaded onto truck
Time 5857.617: Vessel 10 - Truck transported container 16 to yard
Time 5857.617: Vessel 10 - Crane moved container 17
Time 5859.018: Vessel 9 - Truck transported container 17 to yard
Time 5859.018: Vessel 9 - Crane moved container 18
Time 5860.617: Vessel 10 - Container 17 loaded onto truck
Time 5862.018: Vessel 9 - Container 18 loaded onto truck
Time 5866.617: Vessel 10 - Truck transported container 17 to yard
Time 5866.617: Vessel 10 - Crane moved container 18
Time 5868.018: Vessel 9 - Truck transported container 18 to yard
Time 5868.018: Vessel 9 - Crane moved container 19
Time 5869.617: Vessel 10 - Container 18 loaded onto truck
Time 5871.018: Vessel 9 - Container 19 loaded onto truck
Time 5875.617: Vessel 10 - Truck transported container 18 to yard
Time 5875.617: Vessel 10 - Crane moved container 19
Time 5877.018: Vessel 9 - Truck transported container 19 to yard
Time 5877.018: Vessel 9 - Crane moved container 20
Time 5878.617: Vessel 10 - Container 19 loaded onto truck
Time 5880.018: Vessel 9 - Container 20 loaded onto truck
Time 5884.617: Vessel 10 - Truck transported container 19 to yard
Time 5884.617: Vessel 10 - Crane moved container 20
Time 5886.018: Vessel 9 - Truck transported container 20 to yard
Time 5886.018: Vessel 9 - Crane moved container 21
Time 5887.617: Vessel 10 - Container 20 loaded onto truck
Time 5889.018: Vessel 9 - Container 21 loaded onto truck
Time 5893.617: Vessel 10 - Truck transported container 20 to yard
Time 5893.617: Vessel 10 - Crane moved container 21
Time 5895.018: Vessel 9 - Truck transported container 21 to yard
Time 5895.018: Vessel 9 - Crane moved container 22
Time 5896.617: Vessel 10 - Container 21 loaded onto truck
Time 5898.018: Vessel 9 - Container 22 loaded onto truck
Time 5902.617: Vessel 10 - Truck transported container 21 to yard
Time 5902.617: Vessel 10 - Crane moved container 22
Time 5904.018: Vessel 9 - Truck transported container 22 to yard
Time 5904.018: Vessel 9 - Crane moved container 23
Time 5905.617: Vessel 10 - Container 22 loaded onto truck
Time 5907.018: Vessel 9 - Container 23 loaded onto truck
Time 5911.617: Vessel 10 - Truck transported container 22 to yard
Time 5911.617: Vessel 10 - Crane moved container 23
Time 5913.018: Vessel 9 - Truck transported container 23 to yard
Time 5913.018: Vessel 9 - Crane moved container 24
Time 5914.617: Vessel 10 - Container 23 loaded onto truck
Time 5916.018: Vessel 9 - Container 24 loaded onto truck
Time 5920.617: Vessel 10 - Truck transported container 23 to yard
Time 5920.617: Vessel 10 - Crane moved container 24
Time 5922.018: Vessel 9 - Truck transported container 24 to yard
Time 5922.018: Vessel 9 - Crane moved container 25
Time 5923.617: Vessel 10 - Container 24 loaded onto truck
Time 5925.018: Vessel 9 - Container 25 loaded onto truck
Time 5929.617: Vessel 10 - Truck transported container 24 to yard
Time 5929.617: Vessel 10 - Crane moved container 25
Time 5931.018: Vessel 9 - Truck transported container 25 to yard
Time 5931.018: Vessel 9 - Crane moved container 26
Time 5932.617: Vessel 10 - Container 25 loaded onto truck
Time 5934.018: Vessel 9 - Container 26 loaded onto truck
Time 5938.617: Vessel 10 - Truck transported container 25 to yard
Time 5938.617: Vessel 10 - Crane moved container 26
Time 5940.018: Vessel 9 - Truck transported container 26 to yard
Time 5940.018: Vessel 9 - Crane moved container 27
Time 5940.469: Vessel 26 Arrived
Time 5940.469: Vessel 26 Waiting for a berth
Time 5941.617: Vessel 10 - Container 26 loaded onto truck
Time 5943.018: Vessel 9 - Container 27 loaded onto truck
Time 5947.617: Vessel 10 - Truck transported container 26 to yard
Time 5947.617: Vessel 10 - Crane moved container 27
Time 5949.018: Vessel 9 - Truck transported container 27 to yard
Time 5949.018: Vessel 9 - Crane moved container 28
Time 5950.617: Vessel 10 - Container 27 loaded onto truck
Time 5952.018: Vessel 9 - Container 28 loaded onto truck
Time 5956.617: Vessel 10 - Truck transported container 27 to yard
Time 5956.617: Vessel 10 - Crane moved container 28
Time 5958.018: Vessel 9 - Truck transported container 28 to yard
Time 5958.018: Vessel 9 - Crane moved container 29
Time 5959.617: Vessel 10 - Container 28 loaded onto truck
Time 5961.018: Vessel 9 - Container 29 loaded onto truck
Time 5965.617: Vessel 10 - Truck transported container 28 to yard
Time 5965.617: Vessel 10 - Crane moved container 29
Time 5967.018: Vessel 9 - Truck transported container 29 to yard
Time 5967.018: Vessel 9 - Crane moved container 30
Time 5968.617: Vessel 10 - Container 29 loaded onto truck
Time 5969.669: Vessel 27 Arrived
Time 5969.669: Vessel 27 Waiting for a berth
Time 5970.018: Vessel 9 - Container 30 loaded onto truck
Time 5974.617: Vessel 10 - Truck transported container 29 to yard
Time 5974.617: Vessel 10 - Crane moved container 30
Time 5976.018: Vessel 9 - Truck transported container 30 to yard
Time 5976.018: Vessel 9 - Crane moved container 31
Time 5977.617: Vessel 10 - Container 30 loaded onto truck
Time 5979.018: Vessel 9 - Container 31 loaded onto truck
Time 5983.617: Vessel 10 - Truck transported container 30 to yard
Time 5983.617: Vessel 10 - Crane moved container 31
Time 5985.018: Vessel 9 - Truck transported container 31 to yard
Time 5985.018: Vessel 9 - Crane moved container 32
Time 5986.617: Vessel 10 - Container 31 loaded onto truck
Time 5988.018: Vessel 9 - Container 32 loaded onto truck
Time 5992.617: Vessel 10 - Truck transported container 31 to yard
Time 5992.617: Vessel 10 - Crane moved container 32
Time 5994.018: Vessel 9 - Truck transported container 32 to yard
Time 5994.018: Vessel 9 - Crane moved container 33
Time 5995.617: Vessel 10 - Container 32 loaded onto truck
Time 5997.018: Vessel 9 - Container 33 loaded onto truck
Time 6000.184: Vessel 28 Arrived
Time 6000.184: Vessel 28 Waiting for a berth
Time 6001.617: Vessel 10 - Truck transported container 32 to yard
Time 6001.617: Vessel 10 - Crane moved container 33
Time 6003.018: Vessel 9 - Truck transported container 33 to yard
Time 6003.018: Vessel 9 - Crane moved container 34
Time 6004.617: Vessel 10 - Container 33 loaded onto truck
Time 6006.018: Vessel 9 - Container 34 loaded onto truck
Time 6010.617: Vessel 10 - Truck transported container 33 to yard
Time 6010.617: Vessel 10 - Crane moved container 34
Time 6012.018: Vessel 9 - Truck transported container 34 to yard
Time 6012.018: Vessel 9 - Crane moved container 35
Time 6013.617: Vessel 10 - Container 34 loaded onto truck
Time 6015.018: Vessel 9 - Container 35 loaded onto truck
Time 6019.617: Vessel 10 - Truck transported container 34 to yard
Time 6019.617: Vessel 10 - Crane moved container 35
Time 6021.018: Vessel 9 - Truck transported container 35 to yard
Time 6021.018: Vessel 9 - Crane moved container 36
Time 6022.617: Vessel 10 - Container 35 loaded onto truck
Time 6024.018: Vessel 9 - Container 36 loaded onto truck
Time 6028.617: Vessel 10 - Truck transported container 35 to yard
Time 6028.617: Vessel 10 - Crane moved container 36
Time 6030.018: Vessel 9 - Truck transported container 36 to yard
Time 6030.018: Vessel 9 - Crane moved container 37
Time 6031.617: Vessel 10 - Container 36 loaded onto truck
Time 6033.018: Vessel 9 - Container 37 loaded onto truck
Time 6037.617: Vessel 10 - Truck transported container 36 to yard
Time 6037.617: Vessel 10 - Crane moved container 37
Time 6039.018: Vessel 9 - Truck transported container 37 to yard
Time 6039.018: Vessel 9 - Crane moved container 38
Time 6040.617: Vessel 10 - Container 37 loaded onto truck
Time 6042.018: Vessel 9 - Container 38 loaded onto truck
Time 6046.617: Vessel 10 - Truck transported container 37 to yard
Time 6046.617: Vessel 10 - Crane moved container 38
Time 6048.018: Vessel 9 - Truck transported container 38 to yard
Time 6048.018: Vessel 9 - Crane moved container 39
Time 6049.617: Vessel 10 - Container 38 loaded onto truck
Time 6051.018: Vessel 9 - Container 39 loaded onto truck
Time 6055.617: Vessel 10 - Truck transported container 38 to yard
Time 6055.617: Vessel 10 - Crane moved container 39
Time 6057.018: Vessel 9 - Truck transported container 39 to yard
Time 6057.018: Vessel 9 - Crane moved container 40
Time 6058.617: Vessel 10 - Container 39 loaded onto truck
Time 6060.018: Vessel 9 - Container 40 loaded onto truck
Time 6064.617: Vessel 10 - Truck transported container 39 to yard
Time 6064.617: Vessel 10 - Crane moved container 40
Time 6066.018: Vessel 9 - Truck transported container 40 to yard
Time 6066.018: Vessel 9 - Crane moved container 41
Time 6067.617: Vessel 10 - Container 40 loaded onto truck
Time 6069.018: Vessel 9 - Container 41 loaded onto truck
Time 6073.617: Vessel 10 - Truck transported container 40 to yard
Time 6073.617: Vessel 10 - Crane moved container 41
Time 6075.018: Vessel 9 - Truck transported container 41 to yard
Time 6075.018: Vessel 9 - Crane moved container 42
Time 6076.617: Vessel 10 - Container 41 loaded onto truck
Time 6078.018: Vessel 9 - Container 42 loaded onto truck
Time 6082.617: Vessel 10 - Truck transported container 41 to yard
Time 6082.617: Vessel 10 - Crane moved container 42
Time 6084.018: Vessel 9 - Truck transported container 42 to yard
Time 6084.018: Vessel 9 - Crane moved container 43
Time 6085.617: Vessel 10 - Container 42 loaded onto truck
Time 6087.018: Vessel 9 - Container 43 loaded onto truck
Time 6091.617: Vessel 10 - Truck transported container 42 to yard
Time 6091.617: Vessel 10 - Crane moved container 43
Time 6093.018: Vessel 9 - Truck transported container 43 to yard
Time 6093.018: Vessel 9 - Crane moved container 44
Time 6094.617: Vessel 10 - Container 43 loaded onto truck
Time 6096.018: Vessel 9 - Container 44 loaded onto truck
Time 6100.617: Vessel 10 - Truck transported container 43 to yard
Time 6100.617: Vessel 10 - Crane moved container 44
Time 6102.018: Vessel 9 - Truck transported container 44 to yard
Time 6102.018: Vessel 9 - Crane moved container 45
Time 6103.617: Vessel 10 - Container 44 loaded onto truck
Time 6105.018: Vessel 9 - Container 45 loaded onto truck
Time 6109.617: Vessel 10 - Truck transported container 44 to yard
Time 6109.617: Vessel 10 - Crane moved container 45
Time 6111.018: Vessel 9 - Truck transported container 45 to yard
Time 6111.018: Vessel 9 - Crane moved container 46
Time 6112.617: Vessel 10 - Container 45 loaded onto truck
Time 6114.018: Vessel 9 - Container 46 loaded onto truck
Time 6118.617: Vessel 10 - Truck transported container 45 to yard
Time 6118.617: Vessel 10 - Crane moved container 46
Time 6120.018: Vessel 9 - Truck transported container 46 to yard
Time 6120.018: Vessel 9 - Crane moved container 47
Time 6121.617: Vessel 10 - Container 46 loaded onto truck
Time 6123.018: Vessel 9 - Container 47 loaded onto truck
Time 6127.617: Vessel 10 - Truck transported container 46 to yard
Time 6127.617: Vessel 10 - Crane moved container 47
Time 6129.018: Vessel 9 - Truck transported container 47 to yard
Time 6129.018: Vessel 9 - Crane moved container 48
Time 6130.617: Vessel 10 - Container 47 loaded onto truck
Time 6132.018: Vessel 9 - Container 48 loaded onto truck
Time 6136.617: Vessel 10 - Truck transported container 47 to yard
Time 6136.617: Vessel 10 - Crane moved container 48
Time 6138.018: Vessel 9 - Truck transported container 48 to yard
Time 6138.018: Vessel 9 - Crane moved container 49
Time 6139.617: Vessel 10 - Container 48 loaded onto truck
Time 6141.018: Vessel 9 - Container 49 loaded onto truck
Time 6145.617: Vessel 10 - Truck transported container 48 to yard
Time 6145.617: Vessel 10 - Crane moved container 49
Time 6147.018: Vessel 9 - Truck transported container 49 to yard
Time 6147.018: Vessel 9 - Crane moved container 50
Time 6148.617: Vessel 10 - Container 49 loaded onto truck
Time 6150.018: Vessel 9 - Container 50 loaded onto truck
Time 6154.617: Vessel 10 - Truck transported container 49 to yard
Time 6154.617: Vessel 10 - Crane moved container 50
Time 6156.018: Vessel 9 - Truck transported container 50 to yard
Time 6156.018: Vessel 9 - Crane moved container 51
Time 6157.617: Vessel 10 - Container 50 loaded onto truck
Time 6159.018: Vessel 9 - Container 51 loaded onto truck
Time 6163.617: Vessel 10 - Truck transported container 50 to yard
Time 6163.617: Vessel 10 - Crane moved container 51
Time 6165.018: Vessel 9 - Truck transported container 51 to yard
Time 6165.018: Vessel 9 - Crane moved container 52
Time 6166.617: Vessel 10 - Container 51 loaded onto truck
Time 6168.018: Vessel 9 - Container 52 loaded onto truck
Time 6172.617: Vessel 10 - Truck transported container 51 to yard
Time 6172.617: Vessel 10 - Crane moved container 52
Time 6174.018: Vessel 9 - Truck transported container 52 to yard
Time 6174.018: Vessel 9 - Crane moved container 53
Time 6175.617: Vessel 10 - Container 52 loaded onto truck
Time 6177.018: Vessel 9 - Container 53 loaded onto truck
Time 6181.617: Vessel 10 - Truck transported container 52 to yard
Time 6181.617: Vessel 10 - Crane moved container 53
Time 6183.018: Vessel 9 - Truck transported container 53 to yard
Time 6183.018: Vessel 9 - Crane moved container 54
Time 6184.617: Vessel 10 - Container 53 loaded onto truck
Time 6186.018: Vessel 9 - Container 54 loaded onto truck
Time 6190.617: Vessel 10 - Truck transported container 53 to yard
Time 6190.617: Vessel 10 - Crane moved container 54
Time 6192.018: Vessel 9 - Truck transported container 54 to yard
Time 6192.018: Vessel 9 - Crane moved container 55
Time 6193.617: Vessel 10 - Container 54 loaded onto truck
Time 6195.018: Vessel 9 - Container 55 loaded onto truck
Time 6199.617: Vessel 10 - Truck transported container 54 to yard
Time 6199.617: Vessel 10 - Crane moved container 55
Time 6201.018: Vessel 9 - Truck transported container 55 to yard
Time 6201.018: Vessel 9 - Crane moved container 56
Time 6202.617: Vessel 10 - Container 55 loaded onto truck
Time 6204.018: Vessel 9 - Container 56 loaded onto truck
Time 6208.617: Vessel 10 - Truck transported container 55 to yard
Time 6208.617: Vessel 10 - Crane moved container 56
Time 6210.018: Vessel 9 - Truck transported container 56 to yard
Time 6210.018: Vessel 9 - Crane moved container 57
Time 6211.617: Vessel 10 - Container 56 loaded onto truck
Time 6213.018: Vessel 9 - Container 57 loaded onto truck
Time 6217.617: Vessel 10 - Truck transported container 56 to yard
Time 6217.617: Vessel 10 - Crane moved container 57
Time 6219.018: Vessel 9 - Truck transported container 57 to yard
Time 6219.018: Vessel 9 - Crane moved container 58
Time 6220.617: Vessel 10 - Container 57 loaded onto truck
Time 6222.018: Vessel 9 - Container 58 loaded onto truck
Time 6226.617: Vessel 10 - Truck transported container 57 to yard
Time 6226.617: Vessel 10 - Crane moved container 58
Time 6228.018: Vessel 9 - Truck transported container 58 to yard
Time 6228.018: Vessel 9 - Crane moved container 59
Time 6229.617: Vessel 10 - Container 58 loaded onto truck
Time 6231.018: Vessel 9 - Container 59 loaded onto truck
Time 6235.617: Vessel 10 - Truck transported container 58 to yard
Time 6235.617: Vessel 10 - Crane moved container 59
Time 6237.018: Vessel 9 - Truck transported container 59 to yard
Time 6237.018: Vessel 9 - Crane moved container 60
Time 6238.617: Vessel 10 - Container 59 loaded onto truck
Time 6240.018: Vessel 9 - Container 60 loaded onto truck
Time 6244.617: Vessel 10 - Truck transported container 59 to yard
Time 6244.617: Vessel 10 - Crane moved container 60
Time 6246.018: Vessel 9 - Truck transported container 60 to yard
Time 6246.018: Vessel 9 - Crane moved container 61
Time 6247.617: Vessel 10 - Container 60 loaded onto truck
Time 6249.018: Vessel 9 - Container 61 loaded onto truck
Time 6253.617: Vessel 10 - Truck transported container 60 to yard
Time 6253.617: Vessel 10 - Crane moved container 61
Time 6255.018: Vessel 9 - Truck transported container 61 to yard
Time 6255.018: Vessel 9 - Crane moved container 62
Time 6256.617: Vessel 10 - Container 61 loaded onto truck
Time 6258.018: Vessel 9 - Container 62 loaded onto truck
Time 6262.617: Vessel 10 - Truck transported container 61 to yard
Time 6262.617: Vessel 10 - Crane moved container 62
Time 6264.018: Vessel 9 - Truck transported container 62 to yard
Time 6264.018: Vessel 9 - Crane moved container 63
Time 6265.617: Vessel 10 - Container 62 loaded onto truck
Time 6267.018: Vessel 9 - Container 63 loaded onto truck
Time 6271.617: Vessel 10 - Truck transported container 62 to yard
Time 6271.617: Vessel 10 - Crane moved container 63
Time 6273.018: Vessel 9 - Truck transported container 63 to yard
Time 6273.018: Vessel 9 - Crane moved container 64
Time 6274.617: Vessel 10 - Container 63 loaded onto truck
Time 6276.018: Vessel 9 - Container 64 loaded onto truck
Time 6280.617: Vessel 10 - Truck transported container 63 to yard
Time 6280.617: Vessel 10 - Crane moved container 64
Time 6282.018: Vessel 9 - Truck transported container 64 to yard
Time 6282.018: Vessel 9 - Crane moved container 65
Time 6283.617: Vessel 10 - Container 64 loaded onto truck
Time 6285.018: Vessel 9 - Container 65 loaded onto truck
Time 6289.617: Vessel 10 - Truck transported container 64 to yard
Time 6289.617: Vessel 10 - Crane moved container 65
Time 6291.018: Vessel 9 - Truck transported container 65 to yard
Time 6291.018: Vessel 9 - Crane moved container 66
Time 6292.617: Vessel 10 - Container 65 loaded onto truck
Time 6294.018: Vessel 9 - Container 66 loaded onto truck
Time 6298.617: Vessel 10 - Truck transported container 65 to yard
Time 6298.617: Vessel 10 - Crane moved container 66
Time 6300.018: Vessel 9 - Truck transported container 66 to yard
Time 6300.018: Vessel 9 - Crane moved container 67
Time 6301.617: Vessel 10 - Container 66 loaded onto truck
Time 6303.018: Vessel 9 - Container 67 loaded onto truck
Time 6307.617: Vessel 10 - Truck transported container 66 to yard
Time 6307.617: Vessel 10 - Crane moved container 67
Time 6309.018: Vessel 9 - Truck transported container 67 to yard
Time 6309.018: Vessel 9 - Crane moved container 68
Time 6310.617: Vessel 10 - Container 67 loaded onto truck
Time 6312.018: Vessel 9 - Container 68 loaded onto truck
Time 6316.617: Vessel 10 - Truck transported container 67 to yard
Time 6316.617: Vessel 10 - Crane moved container 68
Time 6318.018: Vessel 9 - Truck transported container 68 to yard
Time 6318.018: Vessel 9 - Crane moved container 69
Time 6319.617: Vessel 10 - Container 68 loaded onto truck
Time 6321.018: Vessel 9 - Container 69 loaded onto truck
Time 6325.617: Vessel 10 - Truck transported container 68 to yard
Time 6325.617: Vessel 10 - Crane moved container 69
Time 6327.018: Vessel 9 - Truck transported container 69 to yard
Time 6327.018: Vessel 9 - Crane moved container 70
Time 6328.617: Vessel 10 - Container 69 loaded onto truck
Time 6330.018: Vessel 9 - Container 70 loaded onto truck
Time 6334.617: Vessel 10 - Truck transported container 69 to yard
Time 6334.617: Vessel 10 - Crane moved container 70
Time 6336.018: Vessel 9 - Truck transported container 70 to yard
Time 6336.018: Vessel 9 - Crane moved container 71
Time 6337.617: Vessel 10 - Container 70 loaded onto truck
Time 6339.018: Vessel 9 - Container 71 loaded onto truck
Time 6343.617: Vessel 10 - Truck transported container 70 to yard
Time 6343.617: Vessel 10 - Crane moved container 71
Time 6345.018: Vessel 9 - Truck transported container 71 to yard
Time 6345.018: Vessel 9 - Crane moved container 72
Time 6346.617: Vessel 10 - Container 71 loaded onto truck
Time 6348.018: Vessel 9 - Container 72 loaded onto truck
Time 6352.617: Vessel 10 - Truck transported container 71 to yard
Time 6352.617: Vessel 10 - Crane moved container 72
Time 6354.018: Vessel 9 - Truck transported container 72 to yard
Time 6354.018: Vessel 9 - Crane moved container 73
Time 6355.617: Vessel 10 - Container 72 loaded onto truck
Time 6357.018: Vessel 9 - Container 73 loaded onto truck
Time 6361.617: Vessel 10 - Truck transported container 72 to yard
Time 6361.617: Vessel 10 - Crane moved container 73
Time 6363.018: Vessel 9 - Truck transported container 73 to yard
Time 6363.018: Vessel 9 - Crane moved container 74
Time 6364.617: Vessel 10 - Container 73 loaded onto truck
Time 6366.018: Vessel 9 - Container 74 loaded onto truck
Time 6370.617: Vessel 10 - Truck transported container 73 to yard
Time 6370.617: Vessel 10 - Crane moved container 74
Time 6372.018: Vessel 9 - Truck transported container 74 to yard
Time 6372.018: Vessel 9 - Crane moved container 75
Time 6373.617: Vessel 10 - Container 74 loaded onto truck
Time 6375.018: Vessel 9 - Container 75 loaded onto truck
Time 6379.617: Vessel 10 - Truck transported container 74 to yard
Time 6379.617: Vessel 10 - Crane moved container 75
Time 6381.018: Vessel 9 - Truck transported container 75 to yard
Time 6381.018: Vessel 9 - Crane moved container 76
Time 6382.617: Vessel 10 - Container 75 loaded onto truck
Time 6384.018: Vessel 9 - Container 76 loaded onto truck
Time 6388.617: Vessel 10 - Truck transported container 75 to yard
Time 6388.617: Vessel 10 - Crane moved container 76
Time 6390.018: Vessel 9 - Truck transported container 76 to yard
Time 6390.018: Vessel 9 - Crane moved container 77
Time 6391.617: Vessel 10 - Container 76 loaded onto truck
Time 6393.018: Vessel 9 - Container 77 loaded onto truck
Time 6397.617: Vessel 10 - Truck transported container 76 to yard
Time 6397.617: Vessel 10 - Crane moved container 77
Time 6399.018: Vessel 9 - Truck transported container 77 to yard
Time 6399.018: Vessel 9 - Crane moved container 78
Time 6400.617: Vessel 10 - Container 77 loaded onto truck
Time 6402.018: Vessel 9 - Container 78 loaded onto truck
Time 6406.617: Vessel 10 - Truck transported container 77 to yard
Time 6406.617: Vessel 10 - Crane moved container 78
Time 6408.018: Vessel 9 - Truck transported container 78 to yard
Time 6408.018: Vessel 9 - Crane moved container 79
Time 6409.617: Vessel 10 - Container 78 loaded onto truck
Time 6411.018: Vessel 9 - Container 79 loaded onto truck
Time 6415.617: Vessel 10 - Truck transported container 78 to yard
Time 6415.617: Vessel 10 - Crane moved container 79
Time 6417.018: Vessel 9 - Truck transported container 79 to yard
Time 6417.018: Vessel 9 - Crane moved container 80
Time 6418.617: Vessel 10 - Container 79 loaded onto truck
Time 6420.018: Vessel 9 - Container 80 loaded onto truck
Time 6424.617: Vessel 10 - Truck transported container 79 to yard
Time 6424.617: Vessel 10 - Crane moved container 80
Time 6426.018: Vessel 9 - Truck transported container 80 to yard
Time 6426.018: Vessel 9 - Crane moved container 81
Time 6427.617: Vessel 10 - Container 80 loaded onto truck
Time 6429.018: Vessel 9 - Container 81 loaded onto truck
Time 6433.617: Vessel 10 - Truck transported container 80 to yard
Time 6433.617: Vessel 10 - Crane moved container 81
Time 6435.018: Vessel 9 - Truck transported container 81 to yard
Time 6435.018: Vessel 9 - Crane moved container 82
Time 6436.617: Vessel 10 - Container 81 loaded onto truck
Time 6438.018: Vessel 9 - Container 82 loaded onto truck
Time 6442.617: Vessel 10 - Truck transported container 81 to yard
Time 6442.617: Vessel 10 - Crane moved container 82
Time 6444.018: Vessel 9 - Truck transported container 82 to yard
Time 6444.018: Vessel 9 - Crane moved container 83
Time 6445.617: Vessel 10 - Container 82 loaded onto truck
Time 6447.018: Vessel 9 - Container 83 loaded onto truck
Time 6451.617: Vessel 10 - Truck transported container 82 to yard
Time 6451.617: Vessel 10 - Crane moved container 83
Time 6453.018: Vessel 9 - Truck transported container 83 to yard
Time 6453.018: Vessel 9 - Crane moved container 84
Time 6454.617: Vessel 10 - Container 83 loaded onto truck
Time 6456.018: Vessel 9 - Container 84 loaded onto truck
Time 6460.617: Vessel 10 - Truck transported container 83 to yard
Time 6460.617: Vessel 10 - Crane moved container 84
Time 6462.018: Vessel 9 - Truck transported container 84 to yard
Time 6462.018: Vessel 9 - Crane moved container 85
Time 6463.617: Vessel 10 - Container 84 loaded onto truck
Time 6465.018: Vessel 9 - Container 85 loaded onto truck
Time 6469.617: Vessel 10 - Truck transported container 84 to yard
Time 6469.617: Vessel 10 - Crane moved container 85
Time 6471.018: Vessel 9 - Truck transported container 85 to yard
Time 6471.018: Vessel 9 - Crane moved container 86
Time 6472.617: Vessel 10 - Container 85 loaded onto truck
Time 6474.018: Vessel 9 - Container 86 loaded onto truck
Time 6478.617: Vessel 10 - Truck transported container 85 to yard
Time 6478.617: Vessel 10 - Crane moved container 86
Time 6480.018: Vessel 9 - Truck transported container 86 to yard
Time 6480.018: Vessel 9 - Crane moved container 87
Time 6481.617: Vessel 10 - Container 86 loaded onto truck
Time 6483.018: Vessel 9 - Container 87 loaded onto truck
Time 6487.617: Vessel 10 - Truck transported container 86 to yard
Time 6487.617: Vessel 10 - Crane moved container 87
Time 6489.018: Vessel 9 - Truck transported container 87 to yard
Time 6489.018: Vessel 9 - Crane moved container 88
Time 6490.617: Vessel 10 - Container 87 loaded onto truck
Time 6492.018: Vessel 9 - Container 88 loaded onto truck
Time 6496.617: Vessel 10 - Truck transported container 87 to yard
Time 6496.617: Vessel 10 - Crane moved container 88
Time 6498.018: Vessel 9 - Truck transported container 88 to yard
Time 6498.018: Vessel 9 - Crane moved container 89
Time 6499.617: Vessel 10 - Container 88 loaded onto truck
Time 6501.018: Vessel 9 - Container 89 loaded onto truck
Time 6505.617: Vessel 10 - Truck transported container 88 to yard
Time 6505.617: Vessel 10 - Crane moved container 89
Time 6507.018: Vessel 9 - Truck transported container 89 to yard
Time 6507.018: Vessel 9 - Crane moved container 90
Time 6508.617: Vessel 10 - Container 89 loaded onto truck
Time 6510.018: Vessel 9 - Container 90 loaded onto truck
Time 6514.617: Vessel 10 - Truck transported container 89 to yard
Time 6514.617: Vessel 10 - Crane moved container 90
Time 6516.018: Vessel 9 - Truck transported container 90 to yard
Time 6516.018: Vessel 9 - Crane moved container 91
Time 6517.617: Vessel 10 - Container 90 loaded onto truck
Time 6519.018: Vessel 9 - Container 91 loaded onto truck
Time 6523.617: Vessel 10 - Truck transported container 90 to yard
Time 6523.617: Vessel 10 - Crane moved container 91
Time 6525.018: Vessel 9 - Truck transported container 91 to yard
Time 6525.018: Vessel 9 - Crane moved container 92
Time 6526.617: Vessel 10 - Container 91 loaded onto truck
Time 6528.018: Vessel 9 - Container 92 loaded onto truck
Time 6532.617: Vessel 10 - Truck transported container 91 to yard
Time 6532.617: Vessel 10 - Crane moved container 92
Time 6534.018: Vessel 9 - Truck transported container 92 to yard
Time 6534.018: Vessel 9 - Crane moved container 93
Time 6535.617: Vessel 10 - Container 92 loaded onto truck
Time 6537.018: Vessel 9 - Container 93 loaded onto truck
Time 6541.617: Vessel 10 - Truck transported container 92 to yard
Time 6541.617: Vessel 10 - Crane moved container 93
Time 6543.018: Vessel 9 - Truck transported container 93 to yard
Time 6543.018: Vessel 9 - Crane moved container 94
Time 6544.617: Vessel 10 - Container 93 loaded onto truck
Time 6546.018: Vessel 9 - Container 94 loaded onto truck
Time 6550.617: Vessel 10 - Truck transported container 93 to yard
Time 6550.617: Vessel 10 - Crane moved container 94
Time 6552.018: Vessel 9 - Truck transported container 94 to yard
Time 6552.018: Vessel 9 - Crane moved container 95
Time 6553.617: Vessel 10 - Container 94 loaded onto truck
Time 6555.018: Vessel 9 - Container 95 loaded onto truck
Time 6559.617: Vessel 10 - Truck transported container 94 to yard
Time 6559.617: Vessel 10 - Crane moved container 95
Time 6561.018: Vessel 9 - Truck transported container 95 to yard
Time 6561.018: Vessel 9 - Crane moved container 96
Time 6562.617: Vessel 10 - Container 95 loaded onto truck
Time 6564.018: Vessel 9 - Container 96 loaded onto truck
Time 6564.351: Vessel 29 Arrived
Time 6564.351: Vessel 29 Waiting for a berth
Time 6568.617: Vessel 10 - Truck transported container 95 to yard
Time 6568.617: Vessel 10 - Crane moved container 96
Time 6570.018: Vessel 9 - Truck transported container 96 to yard
Time 6570.018: Vessel 9 - Crane moved container 97
Time 6571.617: Vessel 10 - Container 96 loaded onto truck
Time 6573.018: Vessel 9 - Container 97 loaded onto truck
Time 6577.617: Vessel 10 - Truck transported container 96 to yard
Time 6577.617: Vessel 10 - Crane moved container 97
Time 6579.018: Vessel 9 - Truck transported container 97 to yard
Time 6579.018: Vessel 9 - Crane moved container 98
Time 6580.617: Vessel 10 - Container 97 loaded onto truck
Time 6582.018: Vessel 9 - Container 98 loaded onto truck
Time 6586.617: Vessel 10 - Truck transported container 97 to yard
Time 6586.617: Vessel 10 - Crane moved container 98
Time 6588.018: Vessel 9 - Truck transported container 98 to yard
Time 6588.018: Vessel 9 - Crane moved container 99
Time 6589.617: Vessel 10 - Container 98 loaded onto truck
Time 6591.018: Vessel 9 - Container 99 loaded onto truck
Time 6595.617: Vessel 10 - Truck transported container 98 to yard
Time 6595.617: Vessel 10 - Crane moved container 99
Time 6597.018: Vessel 9 - Truck transported container 99 to yard
Time 6597.018: Vessel 9 - Crane moved container 100
Time 6598.617: Vessel 10 - Container 99 loaded onto truck
Time 6600.018: Vessel 9 - Container 100 loaded onto truck
Time 6604.617: Vessel 10 - Truck transported container 99 to yard
Time 6604.617: Vessel 10 - Crane moved container 100
Time 6606.018: Vessel 9 - Truck transported container 100 to yard
Time 6606.018: Vessel 9 - Crane moved container 101
Time 6607.617: Vessel 10 - Container 100 loaded onto truck
Time 6609.018: Vessel 9 - Container 101 loaded onto truck
Time 6613.617: Vessel 10 - Truck transported container 100 to yard
Time 6613.617: Vessel 10 - Crane moved container 101
Time 6615.018: Vessel 9 - Truck transported container 101 to yard
Time 6615.018: Vessel 9 - Crane moved container 102
Time 6616.617: Vessel 10 - Container 101 loaded onto truck
Time 6618.018: Vessel 9 - Container 102 loaded onto truck
Time 6622.617: Vessel 10 - Truck transported container 101 to yard
Time 6622.617: Vessel 10 - Crane moved container 102
Time 6624.018: Vessel 9 - Truck transported container 102 to yard
Time 6624.018: Vessel 9 - Crane moved container 103
Time 6625.617: Vessel 10 - Container 102 loaded onto truck
Time 6627.018: Vessel 9 - Container 103 loaded onto truck
Time 6631.617: Vessel 10 - Truck transported container 102 to yard
Time 6631.617: Vessel 10 - Crane moved container 103
Time 6633.018: Vessel 9 - Truck transported container 103 to yard
Time 6633.018: Vessel 9 - Crane moved container 104
Time 6634.617: Vessel 10 - Container 103 loaded onto truck
Time 6636.018: Vessel 9 - Container 104 loaded onto truck
Time 6640.617: Vessel 10 - Truck transported container 103 to yard
Time 6640.617: Vessel 10 - Crane moved container 104
Time 6642.018: Vessel 9 - Truck transported container 104 to yard
Time 6642.018: Vessel 9 - Crane moved container 105
Time 6643.617: Vessel 10 - Container 104 loaded onto truck
Time 6645.018: Vessel 9 - Container 105 loaded onto truck
Time 6649.617: Vessel 10 - Truck transported container 104 to yard
Time 6649.617: Vessel 10 - Crane moved container 105
Time 6651.018: Vessel 9 - Truck transported container 105 to yard
Time 6651.018: Vessel 9 - Crane moved container 106
Time 6652.617: Vessel 10 - Container 105 loaded onto truck
Time 6654.018: Vessel 9 - Container 106 loaded onto truck
Time 6658.617: Vessel 10 - Truck transported container 105 to yard
Time 6658.617: Vessel 10 - Crane moved container 106
Time 6660.018: Vessel 9 - Truck transported container 106 to yard
Time 6660.018: Vessel 9 - Crane moved container 107
Time 6661.617: Vessel 10 - Container 106 loaded onto truck
Time 6663.018: Vessel 9 - Container 107 loaded onto truck
Time 6667.617: Vessel 10 - Truck transported container 106 to yard
Time 6667.617: Vessel 10 - Crane moved container 107
Time 6669.018: Vessel 9 - Truck transported container 107 to yard
Time 6669.018: Vessel 9 - Crane moved container 108
Time 6670.617: Vessel 10 - Container 107 loaded onto truck
Time 6672.018: Vessel 9 - Container 108 loaded onto truck
Time 6676.617: Vessel 10 - Truck transported container 107 to yard
Time 6676.617: Vessel 10 - Crane moved container 108
Time 6678.018: Vessel 9 - Truck transported container 108 to yard
Time 6678.018: Vessel 9 - Crane moved container 109
Time 6679.617: Vessel 10 - Container 108 loaded onto truck
Time 6681.018: Vessel 9 - Container 109 loaded onto truck
Time 6685.617: Vessel 10 - Truck transported container 108 to yard
Time 6685.617: Vessel 10 - Crane moved container 109
Time 6687.018: Vessel 9 - Truck transported container 109 to yard
Time 6687.018: Vessel 9 - Crane moved container 110
Time 6688.617: Vessel 10 - Container 109 loaded onto truck
Time 6690.018: Vessel 9 - Container 110 loaded onto truck
Time 6694.617: Vessel 10 - Truck transported container 109 to yard
Time 6694.617: Vessel 10 - Crane moved container 110
Time 6696.018: Vessel 9 - Truck transported container 110 to yard
Time 6696.018: Vessel 9 - Crane moved container 111
Time 6697.617: Vessel 10 - Container 110 loaded onto truck
Time 6699.018: Vessel 9 - Container 111 loaded onto truck
Time 6703.617: Vessel 10 - Truck transported container 110 to yard
Time 6703.617: Vessel 10 - Crane moved container 111
Time 6705.018: Vessel 9 - Truck transported container 111 to yard
Time 6705.018: Vessel 9 - Crane moved container 112
Time 6706.617: Vessel 10 - Container 111 loaded onto truck
Time 6708.018: Vessel 9 - Container 112 loaded onto truck
Time 6712.617: Vessel 10 - Truck transported container 111 to yard
Time 6712.617: Vessel 10 - Crane moved container 112
Time 6714.018: Vessel 9 - Truck transported container 112 to yard
Time 6714.018: Vessel 9 - Crane moved container 113
Time 6715.617: Vessel 10 - Container 112 loaded onto truck
Time 6717.018: Vessel 9 - Container 113 loaded onto truck
Time 6721.617: Vessel 10 - Truck transported container 112 to yard
Time 6721.617: Vessel 10 - Crane moved container 113
Time 6723.018: Vessel 9 - Truck transported container 113 to yard
Time 6723.018: Vessel 9 - Crane moved container 114
Time 6724.617: Vessel 10 - Container 113 loaded onto truck
Time 6726.018: Vessel 9 - Container 114 loaded onto truck
Time 6730.617: Vessel 10 - Truck transported container 113 to yard
Time 6730.617: Vessel 10 - Crane moved container 114
Time 6732.018: Vessel 9 - Truck transported container 114 to yard
Time 6732.018: Vessel 9 - Crane moved container 115
Time 6733.617: Vessel 10 - Container 114 loaded onto truck
Time 6735.018: Vessel 9 - Container 115 loaded onto truck
Time 6739.617: Vessel 10 - Truck transported container 114 to yard
Time 6739.617: Vessel 10 - Crane moved container 115
Time 6741.018: Vessel 9 - Truck transported container 115 to yard
Time 6741.018: Vessel 9 - Crane moved container 116
Time 6742.617: Vessel 10 - Container 115 loaded onto truck
Time 6744.018: Vessel 9 - Container 116 loaded onto truck
Time 6748.617: Vessel 10 - Truck transported container 115 to yard
Time 6748.617: Vessel 10 - Crane moved container 116
Time 6750.018: Vessel 9 - Truck transported container 116 to yard
Time 6750.018: Vessel 9 - Crane moved container 117
Time 6751.617: Vessel 10 - Container 116 loaded onto truck
Time 6753.018: Vessel 9 - Container 117 loaded onto truck
Time 6757.617: Vessel 10 - Truck transported container 116 to yard
Time 6757.617: Vessel 10 - Crane moved container 117
Time 6759.018: Vessel 9 - Truck transported container 117 to yard
Time 6759.018: Vessel 9 - Crane moved container 118
Time 6760.617: Vessel 10 - Container 117 loaded onto truck
Time 6762.018: Vessel 9 - Container 118 loaded onto truck
Time 6766.617: Vessel 10 - Truck transported container 117 to yard
Time 6766.617: Vessel 10 - Crane moved container 118
Time 6768.018: Vessel 9 - Truck transported container 118 to yard
Time 6768.018: Vessel 9 - Crane moved container 119
Time 6769.617: Vessel 10 - Container 118 loaded onto truck
Time 6771.018: Vessel 9 - Container 119 loaded onto truck
Time 6775.617: Vessel 10 - Truck transported container 118 to yard
Time 6775.617: Vessel 10 - Crane moved container 119
Time 6777.018: Vessel 9 - Truck transported container 119 to yard
Time 6777.018: Vessel 9 - Crane moved container 120
Time 6778.617: Vessel 10 - Container 119 loaded onto truck
Time 6780.018: Vessel 9 - Container 120 loaded onto truck
Time 6784.617: Vessel 10 - Truck transported container 119 to yard
Time 6784.617: Vessel 10 - Crane moved container 120
Time 6786.018: Vessel 9 - Truck transported container 120 to yard
Time 6786.018: Vessel 9 - Crane moved container 121
Time 6787.617: Vessel 10 - Container 120 loaded onto truck
Time 6789.018: Vessel 9 - Container 121 loaded onto truck
Time 6793.617: Vessel 10 - Truck transported container 120 to yard
Time 6793.617: Vessel 10 - Crane moved container 121
Time 6795.018: Vessel 9 - Truck transported container 121 to yard
Time 6795.018: Vessel 9 - Crane moved container 122
Time 6796.617: Vessel 10 - Container 121 loaded onto truck
Time 6798.018: Vessel 9 - Container 122 loaded onto truck
Time 6802.617: Vessel 10 - Truck transported container 121 to yard
Time 6802.617: Vessel 10 - Crane moved container 122
Time 6804.018: Vessel 9 - Truck transported container 122 to yard
Time 6804.018: Vessel 9 - Crane moved container 123
Time 6805.617: Vessel 10 - Container 122 loaded onto truck
Time 6807.018: Vessel 9 - Container 123 loaded onto truck
Time 6811.617: Vessel 10 - Truck transported container 122 to yard
Time 6811.617: Vessel 10 - Crane moved container 123
Time 6813.018: Vessel 9 - Truck transported container 123 to yard
Time 6813.018: Vessel 9 - Crane moved container 124
Time 6814.617: Vessel 10 - Container 123 loaded onto truck
Time 6816.018: Vessel 9 - Container 124 loaded onto truck
Time 6820.617: Vessel 10 - Truck transported container 123 to yard
Time 6820.617: Vessel 10 - Crane moved container 124
Time 6822.018: Vessel 9 - Truck transported container 124 to yard
Time 6822.018: Vessel 9 - Crane moved container 125
Time 6823.617: Vessel 10 - Container 124 loaded onto truck
Time 6825.018: Vessel 9 - Container 125 loaded onto truck
Time 6829.617: Vessel 10 - Truck transported container 124 to yard
Time 6829.617: Vessel 10 - Crane moved container 125
Time 6831.018: Vessel 9 - Truck transported container 125 to yard
Time 6831.018: Vessel 9 - Crane moved container 126
Time 6832.617: Vessel 10 - Container 125 loaded onto truck
Time 6834.018: Vessel 9 - Container 126 loaded onto truck
Time 6838.617: Vessel 10 - Truck transported container 125 to yard
Time 6838.617: Vessel 10 - Crane moved container 126
Time 6840.018: Vessel 9 - Truck transported container 126 to yard
Time 6840.018: Vessel 9 - Crane moved container 127
Time 6841.617: Vessel 10 - Container 126 loaded onto truck
Time 6842.045: Vessel 30 Arrived
Time 6842.045: Vessel 30 Waiting for a berth
Time 6843.018: Vessel 9 - Container 127 loaded onto truck
Time 6847.617: Vessel 10 - Truck transported container 126 to yard
Time 6847.617: Vessel 10 - Crane moved container 127
Time 6849.018: Vessel 9 - Truck transported container 127 to yard
Time 6849.018: Vessel 9 - Crane moved container 128
Time 6850.617: Vessel 10 - Container 127 loaded onto truck
Time 6852.018: Vessel 9 - Container 128 loaded onto truck
Time 6856.617: Vessel 10 - Truck transported container 127 to yard
Time 6856.617: Vessel 10 - Crane moved container 128
Time 6858.018: Vessel 9 - Truck transported container 128 to yard
Time 6858.018: Vessel 9 - Crane moved container 129
Time 6859.617: Vessel 10 - Container 128 loaded onto truck
Time 6861.018: Vessel 9 - Container 129 loaded onto truck
Time 6865.617: Vessel 10 - Truck transported container 128 to yard
Time 6865.617: Vessel 10 - Crane moved container 129
Time 6867.018: Vessel 9 - Truck transported container 129 to yard
Time 6867.018: Vessel 9 - Crane moved container 130
Time 6868.617: Vessel 10 - Container 129 loaded onto truck
Time 6870.018: Vessel 9 - Container 130 loaded onto truck
Time 6874.617: Vessel 10 - Truck transported container 129 to yard
Time 6874.617: Vessel 10 - Crane moved container 130
Time 6876.018: Vessel 9 - Truck transported container 130 to yard
Time 6876.018: Vessel 9 - Crane moved container 131
Time 6877.617: Vessel 10 - Container 130 loaded onto truck
Time 6879.018: Vessel 9 - Container 131 loaded onto truck
Time 6883.617: Vessel 10 - Truck transported container 130 to yard
Time 6883.617: Vessel 10 - Crane moved container 131
Time 6885.018: Vessel 9 - Truck transported container 131 to yard
Time 6885.018: Vessel 9 - Crane moved container 132
Time 6886.617: Vessel 10 - Container 131 loaded onto truck
Time 6888.018: Vessel 9 - Container 132 loaded onto truck
Time 6892.617: Vessel 10 - Truck transported container 131 to yard
Time 6892.617: Vessel 10 - Crane moved container 132
Time 6894.018: Vessel 9 - Truck transported container 132 to yard
Time 6894.018: Vessel 9 - Crane moved container 133
Time 6895.617: Vessel 10 - Container 132 loaded onto truck
Time 6897.018: Vessel 9 - Container 133 loaded onto truck
Time 6901.617: Vessel 10 - Truck transported container 132 to yard
Time 6901.617: Vessel 10 - Crane moved container 133
Time 6903.018: Vessel 9 - Truck transported container 133 to yard
Time 6903.018: Vessel 9 - Crane moved container 134
Time 6904.617: Vessel 10 - Container 133 loaded onto truck
Time 6906.018: Vessel 9 - Container 134 loaded onto truck
Time 6910.617: Vessel 10 - Truck transported container 133 to yard
Time 6910.617: Vessel 10 - Crane moved container 134
Time 6912.018: Vessel 9 - Truck transported container 134 to yard
Time 6912.018: Vessel 9 - Crane moved container 135
Time 6913.617: Vessel 10 - Container 134 loaded onto truck
Time 6915.018: Vessel 9 - Container 135 loaded onto truck
Time 6919.617: Vessel 10 - Truck transported container 134 to yard
Time 6919.617: Vessel 10 - Crane moved container 135
Time 6921.018: Vessel 9 - Truck transported container 135 to yard
Time 6921.018: Vessel 9 - Crane moved container 136
Time 6922.617: Vessel 10 - Container 135 loaded onto truck
Time 6924.018: Vessel 9 - Container 136 loaded onto truck
Time 6928.617: Vessel 10 - Truck transported container 135 to yard
Time 6928.617: Vessel 10 - Crane moved container 136
Time 6930.018: Vessel 9 - Truck transported container 136 to yard
Time 6930.018: Vessel 9 - Crane moved container 137
Time 6931.617: Vessel 10 - Container 136 loaded onto truck
Time 6933.018: Vessel 9 - Container 137 loaded onto truck
Time 6937.617: Vessel 10 - Truck transported container 136 to yard
Time 6937.617: Vessel 10 - Crane moved container 137
Time 6939.018: Vessel 9 - Truck transported container 137 to yard
Time 6939.018: Vessel 9 - Crane moved container 138
Time 6940.617: Vessel 10 - Container 137 loaded onto truck
Time 6942.018: Vessel 9 - Container 138 loaded onto truck
Time 6946.617: Vessel 10 - Truck transported container 137 to yard
Time 6946.617: Vessel 10 - Crane moved container 138
Time 6948.018: Vessel 9 - Truck transported container 138 to yard
Time 6948.018: Vessel 9 - Crane moved container 139
Time 6949.617: Vessel 10 - Container 138 loaded onto truck
Time 6951.018: Vessel 9 - Container 139 loaded onto truck
Time 6955.617: Vessel 10 - Truck transported container 138 to yard
Time 6955.617: Vessel 10 - Crane moved container 139
Time 6957.018: Vessel 9 - Truck transported container 139 to yard
Time 6957.018: Vessel 9 - Crane moved container 140
Time 6958.617: Vessel 10 - Container 139 loaded onto truck
Time 6960.018: Vessel 9 - Container 140 loaded onto truck
Time 6964.617: Vessel 10 - Truck transported container 139 to yard
Time 6964.617: Vessel 10 - Crane moved container 140
Time 6966.018: Vessel 9 - Truck transported container 140 to yard
Time 6966.018: Vessel 9 - Crane moved container 141
Time 6967.617: Vessel 10 - Container 140 loaded onto truck
Time 6969.018: Vessel 9 - Container 141 loaded onto truck
Time 6973.617: Vessel 10 - Truck transported container 140 to yard
Time 6973.617: Vessel 10 - Crane moved container 141
Time 6975.018: Vessel 9 - Truck transported container 141 to yard
Time 6975.018: Vessel 9 - Crane moved container 142
Time 6976.617: Vessel 10 - Container 141 loaded onto truck
Time 6978.018: Vessel 9 - Container 142 loaded onto truck
Time 6982.617: Vessel 10 - Truck transported container 141 to yard
Time 6982.617: Vessel 10 - Crane moved container 142
Time 6984.018: Vessel 9 - Truck transported container 142 to yard
Time 6984.018: Vessel 9 - Crane moved container 143
Time 6985.617: Vessel 10 - Container 142 loaded onto truck
Time 6987.018: Vessel 9 - Container 143 loaded onto truck
Time 6991.617: Vessel 10 - Truck transported container 142 to yard
Time 6991.617: Vessel 10 - Crane moved container 143
Time 6993.018: Vessel 9 - Truck transported container 143 to yard
Time 6993.018: Vessel 9 - Crane moved container 144
Time 6994.617: Vessel 10 - Container 143 loaded onto truck
Time 6996.018: Vessel 9 - Container 144 loaded onto truck
Time 7000.617: Vessel 10 - Truck transported container 143 to yard
Time 7000.617: Vessel 10 - Crane moved container 144
Time 7002.018: Vessel 9 - Truck transported container 144 to yard
Time 7002.018: Vessel 9 - Crane moved container 145
Time 7003.617: Vessel 10 - Container 144 loaded onto truck
Time 7005.018: Vessel 9 - Container 145 loaded onto truck
Time 7009.617: Vessel 10 - Truck transported container 144 to yard
Time 7009.617: Vessel 10 - Crane moved container 145
Time 7011.018: Vessel 9 - Truck transported container 145 to yard
Time 7011.018: Vessel 9 - Crane moved container 146
Time 7012.617: Vessel 10 - Container 145 loaded onto truck
Time 7014.018: Vessel 9 - Container 146 loaded onto truck
Time 7018.617: Vessel 10 - Truck transported container 145 to yard
Time 7018.617: Vessel 10 - Crane moved container 146
Time 7020.018: Vessel 9 - Truck transported container 146 to yard
Time 7020.018: Vessel 9 - Crane moved container 147
Time 7021.617: Vessel 10 - Container 146 loaded onto truck
Time 7023.018: Vessel 9 - Container 147 loaded onto truck
Time 7027.617: Vessel 10 - Truck transported container 146 to yard
Time 7027.617: Vessel 10 - Crane moved container 147
Time 7029.018: Vessel 9 - Truck transported container 147 to yard
Time 7029.018: Vessel 9 - Crane moved container 148
Time 7030.617: Vessel 10 - Container 147 loaded onto truck
Time 7032.018: Vessel 9 - Container 148 loaded onto truck
Time 7036.617: Vessel 10 - Truck transported container 147 to yard
Time 7036.617: Vessel 10 - Crane moved container 148
Time 7038.018: Vessel 9 - Truck transported container 148 to yard
Time 7038.018: Vessel 9 - Crane moved container 149
Time 7039.617: Vessel 10 - Container 148 loaded onto truck
Time 7041.018: Vessel 9 - Container 149 loaded onto truck
Time 7045.617: Vessel 10 - Truck transported container 148 to yard
Time 7045.617: Vessel 10 - Crane moved container 149
Time 7047.018: Vessel 9 - Truck transported container 149 to yard
Time 7047.018: Vessel 9 - Crane moved container 150
Time 7048.617: Vessel 10 - Container 149 loaded onto truck
Time 7050.018: Vessel 9 - Container 150 loaded onto truck
Time 7054.617: Vessel 10 - Truck transported container 149 to yard
Time 7054.617: Vessel 10 - Crane moved container 150
Time 7056.018: Vessel 9 - Truck transported container 150 to yard
Time 7056.018: Vessel 9 finished unloading and leaves
Time 7056.018: Vessel 11 berthed
Time 7056.018: Vessel 11 - Crane allocated
Time 7056.018: Vessel 11 - Crane moved container 1
Time 7057.617: Vessel 10 - Container 150 loaded onto truck
Time 7059.018: Vessel 11 - Container 1 loaded onto truck
Time 7063.617: Vessel 10 - Truck transported container 150 to yard
Time 7063.617: Vessel 10 finished unloading and leaves
Time 7063.617: Vessel 12 berthed
Time 7063.617: Vessel 12 - Crane allocated
Time 7063.617: Vessel 12 - Crane moved container 1
Time 7065.018: Vessel 11 - Truck transported container 1 to yard
Time 7065.018: Vessel 11 - Crane moved container 2
Time 7066.617: Vessel 12 - Container 1 loaded onto truck
Time 7068.018: Vessel 11 - Container 2 loaded onto truck
Time 7072.617: Vessel 12 - Truck transported container 1 to yard
Time 7072.617: Vessel 12 - Crane moved container 2
Time 7074.018: Vessel 11 - Truck transported container 2 to yard
Time 7074.018: Vessel 11 - Crane moved container 3
Time 7075.617: Vessel 12 - Container 2 loaded onto truck
Time 7077.018: Vessel 11 - Container 3 loaded onto truck
Time 7081.617: Vessel 12 - Truck transported container 2 to yard
Time 7081.617: Vessel 12 - Crane moved container 3
Time 7083.018: Vessel 11 - Truck transported container 3 to yard
Time 7083.018: Vessel 11 - Crane moved container 4
Time 7084.617: Vessel 12 - Container 3 loaded onto truck
Time 7086.018: Vessel 11 - Container 4 loaded onto truck
Time 7090.617: Vessel 12 - Truck transported container 3 to yard
Time 7090.617: Vessel 12 - Crane moved container 4
Time 7092.018: Vessel 11 - Truck transported container 4 to yard
Time 7092.018: Vessel 11 - Crane moved container 5
Time 7093.617: Vessel 12 - Container 4 loaded onto truck
Time 7095.018: Vessel 11 - Container 5 loaded onto truck
Time 7099.617: Vessel 12 - Truck transported container 4 to yard
Time 7099.617: Vessel 12 - Crane moved container 5
Time 7101.018: Vessel 11 - Truck transported container 5 to yard
Time 7101.018: Vessel 11 - Crane moved container 6
Time 7102.617: Vessel 12 - Container 5 loaded onto truck
Time 7104.018: Vessel 11 - Container 6 loaded onto truck
Time 7108.617: Vessel 12 - Truck transported container 5 to yard
Time 7108.617: Vessel 12 - Crane moved container 6
Time 7110.018: Vessel 11 - Truck transported container 6 to yard
Time 7110.018: Vessel 11 - Crane moved container 7
Time 7111.617: Vessel 12 - Container 6 loaded onto truck
Time 7113.018: Vessel 11 - Container 7 loaded onto truck
Time 7117.617: Vessel 12 - Truck transported container 6 to yard
Time 7117.617: Vessel 12 - Crane moved container 7
Time 7119.018: Vessel 11 - Truck transported container 7 to yard
Time 7119.018: Vessel 11 - Crane moved container 8
Time 7120.617: Vessel 12 - Container 7 loaded onto truck
Time 7122.018: Vessel 11 - Container 8 loaded onto truck
Time 7126.617: Vessel 12 - Truck transported container 7 to yard
Time 7126.617: Vessel 12 - Crane moved container 8
Time 7128.018: Vessel 11 - Truck transported container 8 to yard
Time 7128.018: Vessel 11 - Crane moved container 9
Time 7129.617: Vessel 12 - Container 8 loaded onto truck
Time 7131.018: Vessel 11 - Container 9 loaded onto truck
Time 7135.617: Vessel 12 - Truck transported container 8 to yard
Time 7135.617: Vessel 12 - Crane moved container 9
Time 7137.018: Vessel 11 - Truck transported container 9 to yard
Time 7137.018: Vessel 11 - Crane moved container 10
Time 7138.617: Vessel 12 - Container 9 loaded onto truck
Time 7140.018: Vessel 11 - Container 10 loaded onto truck
Time 7144.617: Vessel 12 - Truck transported container 9 to yard
Time 7144.617: Vessel 12 - Crane moved container 10
Time 7146.018: Vessel 11 - Truck transported container 10 to yard
Time 7146.018: Vessel 11 - Crane moved container 11
Time 7147.617: Vessel 12 - Container 10 loaded onto truck
Time 7149.018: Vessel 11 - Container 11 loaded onto truck
Time 7153.617: Vessel 12 - Truck transported container 10 to yard
Time 7153.617: Vessel 12 - Crane moved container 11
Time 7155.018: Vessel 11 - Truck transported container 11 to yard
Time 7155.018: Vessel 11 - Crane moved container 12
Time 7156.617: Vessel 12 - Container 11 loaded onto truck
Time 7158.018: Vessel 11 - Container 12 loaded onto truck
Time 7162.617: Vessel 12 - Truck transported container 11 to yard
Time 7162.617: Vessel 12 - Crane moved container 12
Time 7164.018: Vessel 11 - Truck transported container 12 to yard
Time 7164.018: Vessel 11 - Crane moved container 13
Time 7165.617: Vessel 12 - Container 12 loaded onto truck
Time 7167.018: Vessel 11 - Container 13 loaded onto truck
Time 7171.617: Vessel 12 - Truck transported container 12 to yard
Time 7171.617: Vessel 12 - Crane moved container 13
Time 7173.018: Vessel 11 - Truck transported container 13 to yard
Time 7173.018: Vessel 11 - Crane moved container 14
Time 7174.617: Vessel 12 - Container 13 loaded onto truck
Time 7176.018: Vessel 11 - Container 14 loaded onto truck
Time 7180.617: Vessel 12 - Truck transported container 13 to yard
Time 7180.617: Vessel 12 - Crane moved container 14
Time 7182.018: Vessel 11 - Truck transported container 14 to yard
Time 7182.018: Vessel 11 - Crane moved container 15
Time 7183.617: Vessel 12 - Container 14 loaded onto truck
Time 7185.018: Vessel 11 - Container 15 loaded onto truck
Time 7189.617: Vessel 12 - Truck transported container 14 to yard
Time 7189.617: Vessel 12 - Crane moved container 15
Time 7191.018: Vessel 11 - Truck transported container 15 to yard
Time 7191.018: Vessel 11 - Crane moved container 16
Time 7192.617: Vessel 12 - Container 15 loaded onto truck
Time 7194.018: Vessel 11 - Container 16 loaded onto truck
Time 7198.617: Vessel 12 - Truck transported container 15 to yard
Time 7198.617: Vessel 12 - Crane moved container 16
Time 7200.018: Vessel 11 - Truck transported container 16 to yard
Time 7200.018: Vessel 11 - Crane moved container 17
Time 7201.617: Vessel 12 - Container 16 loaded onto truck
Time 7203.018: Vessel 11 - Container 17 loaded onto truck
Time 7207.617: Vessel 12 - Truck transported container 16 to yard
Time 7207.617: Vessel 12 - Crane moved container 17
Time 7209.018: Vessel 11 - Truck transported container 17 to yard
Time 7209.018: Vessel 11 - Crane moved container 18
Time 7210.617: Vessel 12 - Container 17 loaded onto truck
Time 7212.018: Vessel 11 - Container 18 loaded onto truck
Time 7216.617: Vessel 12 - Truck transported container 17 to yard
Time 7216.617: Vessel 12 - Crane moved container 18
Time 7218.018: Vessel 11 - Truck transported container 18 to yard
Time 7218.018: Vessel 11 - Crane moved container 19
Time 7219.617: Vessel 12 - Container 18 loaded onto truck
Time 7221.018: Vessel 11 - Container 19 loaded onto truck
Time 7225.617: Vessel 12 - Truck transported container 18 to yard
Time 7225.617: Vessel 12 - Crane moved container 19
Time 7227.018: Vessel 11 - Truck transported container 19 to yard
Time 7227.018: Vessel 11 - Crane moved container 20
Time 7228.617: Vessel 12 - Container 19 loaded onto truck
Time 7230.018: Vessel 11 - Container 20 loaded onto truck
Time 7234.617: Vessel 12 - Truck transported container 19 to yard
Time 7234.617: Vessel 12 - Crane moved container 20
Time 7236.018: Vessel 11 - Truck transported container 20 to yard
Time 7236.018: Vessel 11 - Crane moved container 21
Time 7237.617: Vessel 12 - Container 20 loaded onto truck
Time 7239.018: Vessel 11 - Container 21 loaded onto truck
Time 7243.617: Vessel 12 - Truck transported container 20 to yard
Time 7243.617: Vessel 12 - Crane moved container 21
Time 7245.018: Vessel 11 - Truck transported container 21 to yard
Time 7245.018: Vessel 11 - Crane moved container 22
Time 7246.617: Vessel 12 - Container 21 loaded onto truck
Time 7248.018: Vessel 11 - Container 22 loaded onto truck
Time 7252.617: Vessel 12 - Truck transported container 21 to yard
Time 7252.617: Vessel 12 - Crane moved container 22
Time 7254.018: Vessel 11 - Truck transported container 22 to yard
Time 7254.018: Vessel 11 - Crane moved container 23
Time 7255.617: Vessel 12 - Container 22 loaded onto truck
Time 7257.018: Vessel 11 - Container 23 loaded onto truck
Time 7261.617: Vessel 12 - Truck transported container 22 to yard
Time 7261.617: Vessel 12 - Crane moved container 23
Time 7263.018: Vessel 11 - Truck transported container 23 to yard
Time 7263.018: Vessel 11 - Crane moved container 24
Time 7264.617: Vessel 12 - Container 23 loaded onto truck
Time 7266.018: Vessel 11 - Container 24 loaded onto truck
Time 7270.617: Vessel 12 - Truck transported container 23 to yard
Time 7270.617: Vessel 12 - Crane moved container 24
Time 7272.018: Vessel 11 - Truck transported container 24 to yard
Time 7272.018: Vessel 11 - Crane moved container 25
Time 7273.617: Vessel 12 - Container 24 loaded onto truck
Time 7275.018: Vessel 11 - Container 25 loaded onto truck
Time 7279.617: Vessel 12 - Truck transported container 24 to yard
Time 7279.617: Vessel 12 - Crane moved container 25
Time 7281.018: Vessel 11 - Truck transported container 25 to yard
Time 7281.018: Vessel 11 - Crane moved container 26
Time 7282.617: Vessel 12 - Container 25 loaded onto truck
Time 7284.018: Vessel 11 - Container 26 loaded onto truck
Time 7288.617: Vessel 12 - Truck transported container 25 to yard
Time 7288.617: Vessel 12 - Crane moved container 26
Time 7290.018: Vessel 11 - Truck transported container 26 to yard
Time 7290.018: Vessel 11 - Crane moved container 27
Time 7291.617: Vessel 12 - Container 26 loaded onto truck
Time 7293.018: Vessel 11 - Container 27 loaded onto truck
Time 7297.617: Vessel 12 - Truck transported container 26 to yard
Time 7297.617: Vessel 12 - Crane moved container 27
Time 7299.018: Vessel 11 - Truck transported container 27 to yard
Time 7299.018: Vessel 11 - Crane moved container 28
Time 7300.617: Vessel 12 - Container 27 loaded onto truck
Time 7302.018: Vessel 11 - Container 28 loaded onto truck
Time 7306.617: Vessel 12 - Truck transported container 27 to yard
Time 7306.617: Vessel 12 - Crane moved container 28
Time 7308.018: Vessel 11 - Truck transported container 28 to yard
Time 7308.018: Vessel 11 - Crane moved container 29
Time 7309.617: Vessel 12 - Container 28 loaded onto truck
Time 7311.018: Vessel 11 - Container 29 loaded onto truck
Time 7315.617: Vessel 12 - Truck transported container 28 to yard
Time 7315.617: Vessel 12 - Crane moved container 29
Time 7317.018: Vessel 11 - Truck transported container 29 to yard
Time 7317.018: Vessel 11 - Crane moved container 30
Time 7318.617: Vessel 12 - Container 29 loaded onto truck
Time 7320.018: Vessel 11 - Container 30 loaded onto truck
Time 7324.617: Vessel 12 - Truck transported container 29 to yard
Time 7324.617: Vessel 12 - Crane moved container 30
Time 7326.018: Vessel 11 - Truck transported container 30 to yard
Time 7326.018: Vessel 11 - Crane moved container 31
Time 7327.617: Vessel 12 - Container 30 loaded onto truck
Time 7329.018: Vessel 11 - Container 31 loaded onto truck
Time 7333.617: Vessel 12 - Truck transported container 30 to yard
Time 7333.617: Vessel 12 - Crane moved container 31
Time 7335.018: Vessel 11 - Truck transported container 31 to yard
Time 7335.018: Vessel 11 - Crane moved container 32
Time 7335.764: Vessel 31 Arrived
Time 7335.764: Vessel 31 Waiting for a berth
Time 7336.617: Vessel 12 - Container 31 loaded onto truck
Time 7338.018: Vessel 11 - Container 32 loaded onto truck
Time 7342.617: Vessel 12 - Truck transported container 31 to yard
Time 7342.617: Vessel 12 - Crane moved container 32
Time 7344.018: Vessel 11 - Truck transported container 32 to yard
Time 7344.018: Vessel 11 - Crane moved container 33
Time 7345.617: Vessel 12 - Container 32 loaded onto truck
Time 7347.018: Vessel 11 - Container 33 loaded onto truck
Time 7351.617: Vessel 12 - Truck transported container 32 to yard
Time 7351.617: Vessel 12 - Crane moved container 33
Time 7353.018: Vessel 11 - Truck transported container 33 to yard
Time 7353.018: Vessel 11 - Crane moved container 34
Time 7354.617: Vessel 12 - Container 33 loaded onto truck
Time 7356.018: Vessel 11 - Container 34 loaded onto truck
Time 7360.617: Vessel 12 - Truck transported container 33 to yard
Time 7360.617: Vessel 12 - Crane moved container 34
Time 7362.018: Vessel 11 - Truck transported container 34 to yard
Time 7362.018: Vessel 11 - Crane moved container 35
Time 7363.617: Vessel 12 - Container 34 loaded onto truck
Time 7365.018: Vessel 11 - Container 35 loaded onto truck
Time 7369.617: Vessel 12 - Truck transported container 34 to yard
Time 7369.617: Vessel 12 - Crane moved container 35
Time 7371.018: Vessel 11 - Truck transported container 35 to yard
Time 7371.018: Vessel 11 - Crane moved container 36
Time 7372.617: Vessel 12 - Container 35 loaded onto truck
Time 7374.018: Vessel 11 - Container 36 loaded onto truck
Time 7378.617: Vessel 12 - Truck transported container 35 to yard
Time 7378.617: Vessel 12 - Crane moved container 36
Time 7380.018: Vessel 11 - Truck transported container 36 to yard
Time 7380.018: Vessel 11 - Crane moved container 37
Time 7381.617: Vessel 12 - Container 36 loaded onto truck
Time 7383.018: Vessel 11 - Container 37 loaded onto truck
Time 7387.617: Vessel 12 - Truck transported container 36 to yard
Time 7387.617: Vessel 12 - Crane moved container 37
Time 7389.018: Vessel 11 - Truck transported container 37 to yard
Time 7389.018: Vessel 11 - Crane moved container 38
Time 7390.617: Vessel 12 - Container 37 loaded onto truck
Time 7392.018: Vessel 11 - Container 38 loaded onto truck
Time 7396.617: Vessel 12 - Truck transported container 37 to yard
Time 7396.617: Vessel 12 - Crane moved container 38
Time 7398.018: Vessel 11 - Truck transported container 38 to yard
Time 7398.018: Vessel 11 - Crane moved container 39
Time 7399.617: Vessel 12 - Container 38 loaded onto truck
Time 7401.018: Vessel 11 - Container 39 loaded onto truck
Time 7405.617: Vessel 12 - Truck transported container 38 to yard
Time 7405.617: Vessel 12 - Crane moved container 39
Time 7407.018: Vessel 11 - Truck transported container 39 to yard
Time 7407.018: Vessel 11 - Crane moved container 40
Time 7408.617: Vessel 12 - Container 39 loaded onto truck
Time 7410.018: Vessel 11 - Container 40 loaded onto truck
Time 7414.617: Vessel 12 - Truck transported container 39 to yard
Time 7414.617: Vessel 12 - Crane moved container 40
Time 7416.018: Vessel 11 - Truck transported container 40 to yard
Time 7416.018: Vessel 11 - Crane moved container 41
Time 7417.617: Vessel 12 - Container 40 loaded onto truck
Time 7419.018: Vessel 11 - Container 41 loaded onto truck
Time 7423.617: Vessel 12 - Truck transported container 40 to yard
Time 7423.617: Vessel 12 - Crane moved container 41
Time 7425.018: Vessel 11 - Truck transported container 41 to yard
Time 7425.018: Vessel 11 - Crane moved container 42
Time 7426.617: Vessel 12 - Container 41 loaded onto truck
Time 7428.018: Vessel 11 - Container 42 loaded onto truck
Time 7432.617: Vessel 12 - Truck transported container 41 to yard
Time 7432.617: Vessel 12 - Crane moved container 42
Time 7434.018: Vessel 11 - Truck transported container 42 to yard
Time 7434.018: Vessel 11 - Crane moved container 43
Time 7435.617: Vessel 12 - Container 42 loaded onto truck
Time 7437.018: Vessel 11 - Container 43 loaded onto truck
Time 7441.617: Vessel 12 - Truck transported container 42 to yard
Time 7441.617: Vessel 12 - Crane moved container 43
Time 7443.018: Vessel 11 - Truck transported container 43 to yard
Time 7443.018: Vessel 11 - Crane moved container 44
Time 7444.617: Vessel 12 - Container 43 loaded onto truck
Time 7446.018: Vessel 11 - Container 44 loaded onto truck
Time 7450.617: Vessel 12 - Truck transported container 43 to yard
Time 7450.617: Vessel 12 - Crane moved container 44
Time 7452.018: Vessel 11 - Truck transported container 44 to yard
Time 7452.018: Vessel 11 - Crane moved container 45
Time 7453.617: Vessel 12 - Container 44 loaded onto truck
Time 7455.018: Vessel 11 - Container 45 loaded onto truck
Time 7459.617: Vessel 12 - Truck transported container 44 to yard
Time 7459.617: Vessel 12 - Crane moved container 45
Time 7461.018: Vessel 11 - Truck transported container 45 to yard
Time 7461.018: Vessel 11 - Crane moved container 46
Time 7462.617: Vessel 12 - Container 45 loaded onto truck
Time 7464.018: Vessel 11 - Container 46 loaded onto truck
Time 7468.617: Vessel 12 - Truck transported container 45 to yard
Time 7468.617: Vessel 12 - Crane moved container 46
Time 7470.018: Vessel 11 - Truck transported container 46 to yard
Time 7470.018: Vessel 11 - Crane moved container 47
Time 7471.617: Vessel 12 - Container 46 loaded onto truck
Time 7473.018: Vessel 11 - Container 47 loaded onto truck
Time 7477.617: Vessel 12 - Truck transported container 46 to yard
Time 7477.617: Vessel 12 - Crane moved container 47
Time 7479.018: Vessel 11 - Truck transported container 47 to yard
Time 7479.018: Vessel 11 - Crane moved container 48
Time 7480.617: Vessel 12 - Container 47 loaded onto truck
Time 7482.018: Vessel 11 - Container 48 loaded onto truck
Time 7486.617: Vessel 12 - Truck transported container 47 to yard
Time 7486.617: Vessel 12 - Crane moved container 48
Time 7488.018: Vessel 11 - Truck transported container 48 to yard
Time 7488.018: Vessel 11 - Crane moved container 49
Time 7489.617: Vessel 12 - Container 48 loaded onto truck
Time 7491.018: Vessel 11 - Container 49 loaded onto truck
Time 7495.617: Vessel 12 - Truck transported container 48 to yard
Time 7495.617: Vessel 12 - Crane moved container 49
Time 7497.018: Vessel 11 - Truck transported container 49 to yard
Time 7497.018: Vessel 11 - Crane moved container 50
Time 7498.617: Vessel 12 - Container 49 loaded onto truck
Time 7500.018: Vessel 11 - Container 50 loaded onto truck
Time 7504.617: Vessel 12 - Truck transported container 49 to yard
Time 7504.617: Vessel 12 - Crane moved container 50
Time 7506.018: Vessel 11 - Truck transported container 50 to yard
Time 7506.018: Vessel 11 - Crane moved container 51
Time 7507.617: Vessel 12 - Container 50 loaded onto truck
Time 7509.018: Vessel 11 - Container 51 loaded onto truck
Time 7513.617: Vessel 12 - Truck transported container 50 to yard
Time 7513.617: Vessel 12 - Crane moved container 51
Time 7515.018: Vessel 11 - Truck transported container 51 to yard
Time 7515.018: Vessel 11 - Crane moved container 52
Time 7516.617: Vessel 12 - Container 51 loaded onto truck
Time 7518.018: Vessel 11 - Container 52 loaded onto truck
Time 7522.617: Vessel 12 - Truck transported container 51 to yard
Time 7522.617: Vessel 12 - Crane moved container 52
Time 7524.018: Vessel 11 - Truck transported container 52 to yard
Time 7524.018: Vessel 11 - Crane moved container 53
Time 7525.617: Vessel 12 - Container 52 loaded onto truck
Time 7527.018: Vessel 11 - Container 53 loaded onto truck
Time 7531.617: Vessel 12 - Truck transported container 52 to yard
Time 7531.617: Vessel 12 - Crane moved container 53
Time 7533.018: Vessel 11 - Truck transported container 53 to yard
Time 7533.018: Vessel 11 - Crane moved container 54
Time 7534.617: Vessel 12 - Container 53 loaded onto truck
Time 7536.018: Vessel 11 - Container 54 loaded onto truck
Time 7540.617: Vessel 12 - Truck transported container 53 to yard
Time 7540.617: Vessel 12 - Crane moved container 54
Time 7542.018: Vessel 11 - Truck transported container 54 to yard
Time 7542.018: Vessel 11 - Crane moved container 55
Time 7543.617: Vessel 12 - Container 54 loaded onto truck
Time 7545.018: Vessel 11 - Container 55 loaded onto truck
Time 7549.617: Vessel 12 - Truck transported container 54 to yard
Time 7549.617: Vessel 12 - Crane moved container 55
Time 7551.018: Vessel 11 - Truck transported container 55 to yard
Time 7551.018: Vessel 11 - Crane moved container 56
Time 7552.617: Vessel 12 - Container 55 loaded onto truck
Time 7554.018: Vessel 11 - Container 56 loaded onto truck
Time 7558.617: Vessel 12 - Truck transported container 55 to yard
Time 7558.617: Vessel 12 - Crane moved container 56
Time 7560.018: Vessel 11 - Truck transported container 56 to yard
Time 7560.018: Vessel 11 - Crane moved container 57
Time 7561.617: Vessel 12 - Container 56 loaded onto truck
Time 7563.018: Vessel 11 - Container 57 loaded onto truck
Time 7567.617: Vessel 12 - Truck transported container 56 to yard
Time 7567.617: Vessel 12 - Crane moved container 57
Time 7569.018: Vessel 11 - Truck transported container 57 to yard
Time 7569.018: Vessel 11 - Crane moved container 58
Time 7570.617: Vessel 12 - Container 57 loaded onto truck
Time 7572.018: Vessel 11 - Container 58 loaded onto truck
Time 7576.617: Vessel 12 - Truck transported container 57 to yard
Time 7576.617: Vessel 12 - Crane moved container 58
Time 7578.018: Vessel 11 - Truck transported container 58 to yard
Time 7578.018: Vessel 11 - Crane moved container 59
Time 7579.617: Vessel 12 - Container 58 loaded onto truck
Time 7581.018: Vessel 11 - Container 59 loaded onto truck
Time 7585.617: Vessel 12 - Truck transported container 58 to yard
Time 7585.617: Vessel 12 - Crane moved container 59
Time 7587.018: Vessel 11 - Truck transported container 59 to yard
Time 7587.018: Vessel 11 - Crane moved container 60
Time 7588.617: Vessel 12 - Container 59 loaded onto truck
Time 7590.018: Vessel 11 - Container 60 loaded onto truck
Time 7594.617: Vessel 12 - Truck transported container 59 to yard
Time 7594.617: Vessel 12 - Crane moved container 60
Time 7596.018: Vessel 11 - Truck transported container 60 to yard
Time 7596.018: Vessel 11 - Crane moved container 61
Time 7597.617: Vessel 12 - Container 60 loaded onto truck
Time 7599.018: Vessel 11 - Container 61 loaded onto truck
Time 7603.617: Vessel 12 - Truck transported container 60 to yard
Time 7603.617: Vessel 12 - Crane moved container 61
Time 7605.018: Vessel 11 - Truck transported container 61 to yard
Time 7605.018: Vessel 11 - Crane moved container 62
Time 7606.617: Vessel 12 - Container 61 loaded onto truck
Time 7608.018: Vessel 11 - Container 62 loaded onto truck
Time 7612.617: Vessel 12 - Truck transported container 61 to yard
Time 7612.617: Vessel 12 - Crane moved container 62
Time 7614.018: Vessel 11 - Truck transported container 62 to yard
Time 7614.018: Vessel 11 - Crane moved container 63
Time 7615.617: Vessel 12 - Container 62 loaded onto truck
Time 7617.018: Vessel 11 - Container 63 loaded onto truck
Time 7621.617: Vessel 12 - Truck transported container 62 to yard
Time 7621.617: Vessel 12 - Crane moved container 63
Time 7623.018: Vessel 11 - Truck transported container 63 to yard
Time 7623.018: Vessel 11 - Crane moved container 64
Time 7624.617: Vessel 12 - Container 63 loaded onto truck
Time 7626.018: Vessel 11 - Container 64 loaded onto truck
Time 7630.617: Vessel 12 - Truck transported container 63 to yard
Time 7630.617: Vessel 12 - Crane moved container 64
Time 7632.018: Vessel 11 - Truck transported container 64 to yard
Time 7632.018: Vessel 11 - Crane moved container 65
Time 7633.617: Vessel 12 - Container 64 loaded onto truck
Time 7635.018: Vessel 11 - Container 65 loaded onto truck
Time 7639.617: Vessel 12 - Truck transported container 64 to yard
Time 7639.617: Vessel 12 - Crane moved container 65
Time 7641.018: Vessel 11 - Truck transported container 65 to yard
Time 7641.018: Vessel 11 - Crane moved container 66
Time 7642.617: Vessel 12 - Container 65 loaded onto truck
Time 7644.018: Vessel 11 - Container 66 loaded onto truck
Time 7648.617: Vessel 12 - Truck transported container 65 to yard
Time 7648.617: Vessel 12 - Crane moved container 66
Time 7650.018: Vessel 11 - Truck transported container 66 to yard
Time 7650.018: Vessel 11 - Crane moved container 67
Time 7651.617: Vessel 12 - Container 66 loaded onto truck
Time 7653.018: Vessel 11 - Container 67 loaded onto truck
Time 7657.617: Vessel 12 - Truck transported container 66 to yard
Time 7657.617: Vessel 12 - Crane moved container 67
Time 7659.018: Vessel 11 - Truck transported container 67 to yard
Time 7659.018: Vessel 11 - Crane moved container 68
Time 7660.617: Vessel 12 - Container 67 loaded onto truck
Time 7662.018: Vessel 11 - Container 68 loaded onto truck
Time 7666.617: Vessel 12 - Truck transported container 67 to yard
Time 7666.617: Vessel 12 - Crane moved container 68
Time 7668.018: Vessel 11 - Truck transported container 68 to yard
Time 7668.018: Vessel 11 - Crane moved container 69
Time 7669.617: Vessel 12 - Container 68 loaded onto truck
Time 7671.018: Vessel 11 - Container 69 loaded onto truck
Time 7675.617: Vessel 12 - Truck transported container 68 to yard
Time 7675.617: Vessel 12 - Crane moved container 69
Time 7677.018: Vessel 11 - Truck transported container 69 to yard
Time 7677.018: Vessel 11 - Crane moved container 70
Time 7678.617: Vessel 12 - Container 69 loaded onto truck
Time 7680.018: Vessel 11 - Container 70 loaded onto truck
Time 7684.617: Vessel 12 - Truck transported container 69 to yard
Time 7684.617: Vessel 12 - Crane moved container 70
Time 7686.018: Vessel 11 - Truck transported container 70 to yard
Time 7686.018: Vessel 11 - Crane moved container 71
Time 7687.617: Vessel 12 - Container 70 loaded onto truck
Time 7689.018: Vessel 11 - Container 71 loaded onto truck
Time 7693.617: Vessel 12 - Truck transported container 70 to yard
Time 7693.617: Vessel 12 - Crane moved container 71
Time 7695.018: Vessel 11 - Truck transported container 71 to yard
Time 7695.018: Vessel 11 - Crane moved container 72
Time 7696.617: Vessel 12 - Container 71 loaded onto truck
Time 7698.018: Vessel 11 - Container 72 loaded onto truck
Time 7702.617: Vessel 12 - Truck transported container 71 to yard
Time 7702.617: Vessel 12 - Crane moved container 72
Time 7704.018: Vessel 11 - Truck transported container 72 to yard
Time 7704.018: Vessel 11 - Crane moved container 73
Time 7705.617: Vessel 12 - Container 72 loaded onto truck
Time 7707.018: Vessel 11 - Container 73 loaded onto truck
Time 7711.617: Vessel 12 - Truck transported container 72 to yard
Time 7711.617: Vessel 12 - Crane moved container 73
Time 7713.018: Vessel 11 - Truck transported container 73 to yard
Time 7713.018: Vessel 11 - Crane moved container 74
Time 7714.617: Vessel 12 - Container 73 loaded onto truck
Time 7716.018: Vessel 11 - Container 74 loaded onto truck
Time 7720.617: Vessel 12 - Truck transported container 73 to yard
Time 7720.617: Vessel 12 - Crane moved container 74
Time 7722.018: Vessel 11 - Truck transported container 74 to yard
Time 7722.018: Vessel 11 - Crane moved container 75
Time 7723.617: Vessel 12 - Container 74 loaded onto truck
Time 7725.018: Vessel 11 - Container 75 loaded onto truck
Time 7728.266: Vessel 32 Arrived
Time 7728.266: Vessel 32 Waiting for a berth
Time 7729.617: Vessel 12 - Truck transported container 74 to yard
Time 7729.617: Vessel 12 - Crane moved container 75
Time 7731.018: Vessel 11 - Truck transported container 75 to yard
Time 7731.018: Vessel 11 - Crane moved container 76
Time 7732.617: Vessel 12 - Container 75 loaded onto truck
Time 7734.018: Vessel 11 - Container 76 loaded onto truck
Time 7738.617: Vessel 12 - Truck transported container 75 to yard
Time 7738.617: Vessel 12 - Crane moved container 76
Time 7740.018: Vessel 11 - Truck transported container 76 to yard
Time 7740.018: Vessel 11 - Crane moved container 77
Time 7741.617: Vessel 12 - Container 76 loaded onto truck
Time 7743.018: Vessel 11 - Container 77 loaded onto truck
Time 7747.617: Vessel 12 - Truck transported container 76 to yard
Time 7747.617: Vessel 12 - Crane moved container 77
Time 7749.018: Vessel 11 - Truck transported container 77 to yard
Time 7749.018: Vessel 11 - Crane moved container 78
Time 7750.617: Vessel 12 - Container 77 loaded onto truck
Time 7752.018: Vessel 11 - Container 78 loaded onto truck
Time 7756.617: Vessel 12 - Truck transported container 77 to yard
Time 7756.617: Vessel 12 - Crane moved container 78
Time 7758.018: Vessel 11 - Truck transported container 78 to yard
Time 7758.018: Vessel 11 - Crane moved container 79
Time 7759.617: Vessel 12 - Container 78 loaded onto truck
Time 7761.018: Vessel 11 - Container 79 loaded onto truck
Time 7765.617: Vessel 12 - Truck transported container 78 to yard
Time 7765.617: Vessel 12 - Crane moved container 79
Time 7767.018: Vessel 11 - Truck transported container 79 to yard
Time 7767.018: Vessel 11 - Crane moved container 80
Time 7768.617: Vessel 12 - Container 79 loaded onto truck
Time 7770.018: Vessel 11 - Container 80 loaded onto truck
Time 7774.617: Vessel 12 - Truck transported container 79 to yard
Time 7774.617: Vessel 12 - Crane moved container 80
Time 7776.018: Vessel 11 - Truck transported container 80 to yard
Time 7776.018: Vessel 11 - Crane moved container 81
Time 7777.617: Vessel 12 - Container 80 loaded onto truck
Time 7779.018: Vessel 11 - Container 81 loaded onto truck
Time 7783.617: Vessel 12 - Truck transported container 80 to yard
Time 7783.617: Vessel 12 - Crane moved container 81
Time 7785.018: Vessel 11 - Truck transported container 81 to yard
Time 7785.018: Vessel 11 - Crane moved container 82
Time 7786.617: Vessel 12 - Container 81 loaded onto truck
Time 7788.018: Vessel 11 - Container 82 loaded onto truck
Time 7792.617: Vessel 12 - Truck transported container 81 to yard
Time 7792.617: Vessel 12 - Crane moved container 82
Time 7794.018: Vessel 11 - Truck transported container 82 to yard
Time 7794.018: Vessel 11 - Crane moved container 83
Time 7795.617: Vessel 12 - Container 82 loaded onto truck
Time 7797.018: Vessel 11 - Container 83 loaded onto truck
Time 7801.617: Vessel 12 - Truck transported container 82 to yard
Time 7801.617: Vessel 12 - Crane moved container 83
Time 7803.018: Vessel 11 - Truck transported container 83 to yard
Time 7803.018: Vessel 11 - Crane moved container 84
Time 7804.617: Vessel 12 - Container 83 loaded onto truck
Time 7806.018: Vessel 11 - Container 84 loaded onto truck
Time 7810.617: Vessel 12 - Truck transported container 83 to yard
Time 7810.617: Vessel 12 - Crane moved container 84
Time 7812.018: Vessel 11 - Truck transported container 84 to yard
Time 7812.018: Vessel 11 - Crane moved container 85
Time 7813.617: Vessel 12 - Container 84 loaded onto truck
Time 7815.018: Vessel 11 - Container 85 loaded onto truck
Time 7819.617: Vessel 12 - Truck transported container 84 to yard
Time 7819.617: Vessel 12 - Crane moved container 85
Time 7821.018: Vessel 11 - Truck transported container 85 to yard
Time 7821.018: Vessel 11 - Crane moved container 86
Time 7822.617: Vessel 12 - Container 85 loaded onto truck
Time 7824.018: Vessel 11 - Container 86 loaded onto truck
Time 7828.617: Vessel 12 - Truck transported container 85 to yard
Time 7828.617: Vessel 12 - Crane moved container 86
Time 7830.018: Vessel 11 - Truck transported container 86 to yard
Time 7830.018: Vessel 11 - Crane moved container 87
Time 7831.617: Vessel 12 - Container 86 loaded onto truck
Time 7833.018: Vessel 11 - Container 87 loaded onto truck
Time 7837.617: Vessel 12 - Truck transported container 86 to yard
Time 7837.617: Vessel 12 - Crane moved container 87
Time 7839.018: Vessel 11 - Truck transported container 87 to yard
Time 7839.018: Vessel 11 - Crane moved container 88
Time 7840.617: Vessel 12 - Container 87 loaded onto truck
Time 7842.018: Vessel 11 - Container 88 loaded onto truck
Time 7846.617: Vessel 12 - Truck transported container 87 to yard
Time 7846.617: Vessel 12 - Crane moved container 88
Time 7848.018: Vessel 11 - Truck transported container 88 to yard
Time 7848.018: Vessel 11 - Crane moved container 89
Time 7849.617: Vessel 12 - Container 88 loaded onto truck
Time 7851.018: Vessel 11 - Container 89 loaded onto truck
Time 7855.617: Vessel 12 - Truck transported container 88 to yard
Time 7855.617: Vessel 12 - Crane moved container 89
Time 7857.018: Vessel 11 - Truck transported container 89 to yard
Time 7857.018: Vessel 11 - Crane moved container 90
Time 7858.617: Vessel 12 - Container 89 loaded onto truck
Time 7860.018: Vessel 11 - Container 90 loaded onto truck
Time 7864.617: Vessel 12 - Truck transported container 89 to yard
Time 7864.617: Vessel 12 - Crane moved container 90
Time 7866.018: Vessel 11 - Truck transported container 90 to yard
Time 7866.018: Vessel 11 - Crane moved container 91
Time 7867.617: Vessel 12 - Container 90 loaded onto truck
Time 7869.018: Vessel 11 - Container 91 loaded onto truck
Time 7873.617: Vessel 12 - Truck transported container 90 to yard
Time 7873.617: Vessel 12 - Crane moved container 91
Time 7875.018: Vessel 11 - Truck transported container 91 to yard
Time 7875.018: Vessel 11 - Crane moved container 92
Time 7876.617: Vessel 12 - Container 91 loaded onto truck
Time 7878.018: Vessel 11 - Container 92 loaded onto truck
Time 7882.617: Vessel 12 - Truck transported container 91 to yard
Time 7882.617: Vessel 12 - Crane moved container 92
Time 7884.018: Vessel 11 - Truck transported container 92 to yard
Time 7884.018: Vessel 11 - Crane moved container 93
Time 7885.617: Vessel 12 - Container 92 loaded onto truck
Time 7887.018: Vessel 11 - Container 93 loaded onto truck
Time 7891.617: Vessel 12 - Truck transported container 92 to yard
Time 7891.617: Vessel 12 - Crane moved container 93
Time 7893.018: Vessel 11 - Truck transported container 93 to yard
Time 7893.018: Vessel 11 - Crane moved container 94
Time 7894.617: Vessel 12 - Container 93 loaded onto truck
Time 7896.018: Vessel 11 - Container 94 loaded onto truck
Time 7900.617: Vessel 12 - Truck transported container 93 to yard
Time 7900.617: Vessel 12 - Crane moved container 94
Time 7902.018: Vessel 11 - Truck transported container 94 to yard
Time 7902.018: Vessel 11 - Crane moved container 95
Time 7903.617: Vessel 12 - Container 94 loaded onto truck
Time 7905.018: Vessel 11 - Container 95 loaded onto truck
Time 7909.617: Vessel 12 - Truck transported container 94 to yard
Time 7909.617: Vessel 12 - Crane moved container 95
Time 7911.018: Vessel 11 - Truck transported container 95 to yard
Time 7911.018: Vessel 11 - Crane moved container 96
Time 7912.617: Vessel 12 - Container 95 loaded onto truck
Time 7914.018: Vessel 11 - Container 96 loaded onto truck
Time 7918.617: Vessel 12 - Truck transported container 95 to yard
Time 7918.617: Vessel 12 - Crane moved container 96
Time 7920.018: Vessel 11 - Truck transported container 96 to yard
Time 7920.018: Vessel 11 - Crane moved container 97
Time 7921.617: Vessel 12 - Container 96 loaded onto truck
Time 7923.018: Vessel 11 - Container 97 loaded onto truck
Time 7927.617: Vessel 12 - Truck transported container 96 to yard
Time 7927.617: Vessel 12 - Crane moved container 97
Time 7929.018: Vessel 11 - Truck transported container 97 to yard
Time 7929.018: Vessel 11 - Crane moved container 98
Time 7930.617: Vessel 12 - Container 97 loaded onto truck
Time 7932.018: Vessel 11 - Container 98 loaded onto truck
Time 7936.617: Vessel 12 - Truck transported container 97 to yard
Time 7936.617: Vessel 12 - Crane moved container 98
Time 7938.018: Vessel 11 - Truck transported container 98 to yard
Time 7938.018: Vessel 11 - Crane moved container 99
Time 7939.617: Vessel 12 - Container 98 loaded onto truck
Time 7941.018: Vessel 11 - Container 99 loaded onto truck
Time 7945.617: Vessel 12 - Truck transported container 98 to yard
Time 7945.617: Vessel 12 - Crane moved container 99
Time 7947.018: Vessel 11 - Truck transported container 99 to yard
Time 7947.018: Vessel 11 - Crane moved container 100
Time 7948.617: Vessel 12 - Container 99 loaded onto truck
Time 7950.018: Vessel 11 - Container 100 loaded onto truck
Time 7954.617: Vessel 12 - Truck transported container 99 to yard
Time 7954.617: Vessel 12 - Crane moved container 100
Time 7956.018: Vessel 11 - Truck transported container 100 to yard
Time 7956.018: Vessel 11 - Crane moved container 101
Time 7957.617: Vessel 12 - Container 100 loaded onto truck
Time 7958.775: Vessel 33 Arrived
Time 7958.775: Vessel 33 Waiting for a berth
Time 7959.018: Vessel 11 - Container 101 loaded onto truck
Time 7963.617: Vessel 12 - Truck transported container 100 to yard
Time 7963.617: Vessel 12 - Crane moved container 101
Time 7965.018: Vessel 11 - Truck transported container 101 to yard
Time 7965.018: Vessel 11 - Crane moved container 102
Time 7966.617: Vessel 12 - Container 101 loaded onto truck
Time 7968.018: Vessel 11 - Container 102 loaded onto truck
Time 7972.617: Vessel 12 - Truck transported container 101 to yard
Time 7972.617: Vessel 12 - Crane moved container 102
Time 7974.018: Vessel 11 - Truck transported container 102 to yard
Time 7974.018: Vessel 11 - Crane moved container 103
Time 7975.617: Vessel 12 - Container 102 loaded onto truck
Time 7977.018: Vessel 11 - Container 103 loaded onto truck
Time 7981.617: Vessel 12 - Truck transported container 102 to yard
Time 7981.617: Vessel 12 - Crane moved container 103
Time 7983.018: Vessel 11 - Truck transported container 103 to yard
Time 7983.018: Vessel 11 - Crane moved container 104
Time 7984.617: Vessel 12 - Container 103 loaded onto truck
Time 7986.018: Vessel 11 - Container 104 loaded onto truck
Time 7990.617: Vessel 12 - Truck transported container 103 to yard
Time 7990.617: Vessel 12 - Crane moved container 104
Time 7992.018: Vessel 11 - Truck transported container 104 to yard
Time 7992.018: Vessel 11 - Crane moved container 105
Time 7993.617: Vessel 12 - Container 104 loaded onto truck
Time 7995.018: Vessel 11 - Container 105 loaded onto truck
Time 7999.617: Vessel 12 - Truck transported container 104 to yard
Time 7999.617: Vessel 12 - Crane moved container 105
Time 8001.018: Vessel 11 - Truck transported container 105 to yard
Time 8001.018: Vessel 11 - Crane moved container 106
Time 8002.617: Vessel 12 - Container 105 loaded onto truck
Time 8004.018: Vessel 11 - Container 106 loaded onto truck
Time 8008.617: Vessel 12 - Truck transported container 105 to yard
Time 8008.617: Vessel 12 - Crane moved container 106
Time 8010.018: Vessel 11 - Truck transported container 106 to yard
Time 8010.018: Vessel 11 - Crane moved container 107
Time 8011.617: Vessel 12 - Container 106 loaded onto truck
Time 8013.018: Vessel 11 - Container 107 loaded onto truck
Time 8017.617: Vessel 12 - Truck transported container 106 to yard
Time 8017.617: Vessel 12 - Crane moved container 107
Time 8019.018: Vessel 11 - Truck transported container 107 to yard
Time 8019.018: Vessel 11 - Crane moved container 108
Time 8020.617: Vessel 12 - Container 107 loaded onto truck
Time 8022.018: Vessel 11 - Container 108 loaded onto truck
Time 8026.617: Vessel 12 - Truck transported container 107 to yard
Time 8026.617: Vessel 12 - Crane moved container 108
Time 8028.018: Vessel 11 - Truck transported container 108 to yard
Time 8028.018: Vessel 11 - Crane moved container 109
Time 8029.617: Vessel 12 - Container 108 loaded onto truck
Time 8031.018: Vessel 11 - Container 109 loaded onto truck
Time 8035.617: Vessel 12 - Truck transported container 108 to yard
Time 8035.617: Vessel 12 - Crane moved container 109
Time 8037.018: Vessel 11 - Truck transported container 109 to yard
Time 8037.018: Vessel 11 - Crane moved container 110
Time 8038.617: Vessel 12 - Container 109 loaded onto truck
Time 8040.018: Vessel 11 - Container 110 loaded onto truck
Time 8044.617: Vessel 12 - Truck transported container 109 to yard
Time 8044.617: Vessel 12 - Crane moved container 110
Time 8046.018: Vessel 11 - Truck transported container 110 to yard
Time 8046.018: Vessel 11 - Crane moved container 111
Time 8047.617: Vessel 12 - Container 110 loaded onto truck
Time 8049.018: Vessel 11 - Container 111 loaded onto truck
Time 8053.617: Vessel 12 - Truck transported container 110 to yard
Time 8053.617: Vessel 12 - Crane moved container 111
Time 8055.018: Vessel 11 - Truck transported container 111 to yard
Time 8055.018: Vessel 11 - Crane moved container 112
Time 8056.617: Vessel 12 - Container 111 loaded onto truck
Time 8058.018: Vessel 11 - Container 112 loaded onto truck
Time 8062.617: Vessel 12 - Truck transported container 111 to yard
Time 8062.617: Vessel 12 - Crane moved container 112
Time 8064.018: Vessel 11 - Truck transported container 112 to yard
Time 8064.018: Vessel 11 - Crane moved container 113
Time 8065.617: Vessel 12 - Container 112 loaded onto truck
Time 8067.018: Vessel 11 - Container 113 loaded onto truck
Time 8071.617: Vessel 12 - Truck transported container 112 to yard
Time 8071.617: Vessel 12 - Crane moved container 113
Time 8073.018: Vessel 11 - Truck transported container 113 to yard
Time 8073.018: Vessel 11 - Crane moved container 114
Time 8074.617: Vessel 12 - Container 113 loaded onto truck
Time 8076.018: Vessel 11 - Container 114 loaded onto truck
Time 8080.617: Vessel 12 - Truck transported container 113 to yard
Time 8080.617: Vessel 12 - Crane moved container 114
Time 8082.018: Vessel 11 - Truck transported container 114 to yard
Time 8082.018: Vessel 11 - Crane moved container 115
Time 8083.617: Vessel 12 - Container 114 loaded onto truck
Time 8085.018: Vessel 11 - Container 115 loaded onto truck
Time 8089.617: Vessel 12 - Truck transported container 114 to yard
Time 8089.617: Vessel 12 - Crane moved container 115
Time 8091.018: Vessel 11 - Truck transported container 115 to yard
Time 8091.018: Vessel 11 - Crane moved container 116
Time 8092.617: Vessel 12 - Container 115 loaded onto truck
Time 8094.018: Vessel 11 - Container 116 loaded onto truck
Time 8098.617: Vessel 12 - Truck transported container 115 to yard
Time 8098.617: Vessel 12 - Crane moved container 116
Time 8100.018: Vessel 11 - Truck transported container 116 to yard
Time 8100.018: Vessel 11 - Crane moved container 117
Time 8101.617: Vessel 12 - Container 116 loaded onto truck
Time 8103.018: Vessel 11 - Container 117 loaded onto truck
Time 8107.617: Vessel 12 - Truck transported container 116 to yard
Time 8107.617: Vessel 12 - Crane moved container 117
Time 8109.018: Vessel 11 - Truck transported container 117 to yard
Time 8109.018: Vessel 11 - Crane moved container 118
Time 8110.617: Vessel 12 - Container 117 loaded onto truck
Time 8112.018: Vessel 11 - Container 118 loaded onto truck
Time 8116.617: Vessel 12 - Truck transported container 117 to yard
Time 8116.617: Vessel 12 - Crane moved container 118
Time 8118.018: Vessel 11 - Truck transported container 118 to yard
Time 8118.018: Vessel 11 - Crane moved container 119
Time 8119.617: Vessel 12 - Container 118 loaded onto truck
Time 8121.018: Vessel 11 - Container 119 loaded onto truck
Time 8125.617: Vessel 12 - Truck transported container 118 to yard
Time 8125.617: Vessel 12 - Crane moved container 119
Time 8127.018: Vessel 11 - Truck transported container 119 to yard
Time 8127.018: Vessel 11 - Crane moved container 120
Time 8128.617: Vessel 12 - Container 119 loaded onto truck
Time 8130.018: Vessel 11 - Container 120 loaded onto truck
Time 8134.617: Vessel 12 - Truck transported container 119 to yard
Time 8134.617: Vessel 12 - Crane moved container 120
Time 8136.018: Vessel 11 - Truck transported container 120 to yard
Time 8136.018: Vessel 11 - Crane moved container 121
Time 8137.617: Vessel 12 - Container 120 loaded onto truck
Time 8139.018: Vessel 11 - Container 121 loaded onto truck
Time 8143.617: Vessel 12 - Truck transported container 120 to yard
Time 8143.617: Vessel 12 - Crane moved container 121
Time 8145.018: Vessel 11 - Truck transported container 121 to yard
Time 8145.018: Vessel 11 - Crane moved container 122
Time 8146.617: Vessel 12 - Container 121 loaded onto truck
Time 8148.018: Vessel 11 - Container 122 loaded onto truck
Time 8152.617: Vessel 12 - Truck transported container 121 to yard
Time 8152.617: Vessel 12 - Crane moved container 122
Time 8154.018: Vessel 11 - Truck transported container 122 to yard
Time 8154.018: Vessel 11 - Crane moved container 123
Time 8155.617: Vessel 12 - Container 122 loaded onto truck
Time 8157.018: Vessel 11 - Container 123 loaded onto truck
Time 8161.617: Vessel 12 - Truck transported container 122 to yard
Time 8161.617: Vessel 12 - Crane moved container 123
Time 8163.018: Vessel 11 - Truck transported container 123 to yard
Time 8163.018: Vessel 11 - Crane moved container 124
Time 8164.617: Vessel 12 - Container 123 loaded onto truck
Time 8166.018: Vessel 11 - Container 124 loaded onto truck
Time 8170.617: Vessel 12 - Truck transported container 123 to yard
Time 8170.617: Vessel 12 - Crane moved container 124
Time 8172.018: Vessel 11 - Truck transported container 124 to yard
Time 8172.018: Vessel 11 - Crane moved container 125
Time 8173.617: Vessel 12 - Container 124 loaded onto truck
Time 8175.018: Vessel 11 - Container 125 loaded onto truck
Time 8179.617: Vessel 12 - Truck transported container 124 to yard
Time 8179.617: Vessel 12 - Crane moved container 125
Time 8181.018: Vessel 11 - Truck transported container 125 to yard
Time 8181.018: Vessel 11 - Crane moved container 126
Time 8182.617: Vessel 12 - Container 125 loaded onto truck
Time 8184.018: Vessel 11 - Container 126 loaded onto truck
Time 8188.617: Vessel 12 - Truck transported container 125 to yard
Time 8188.617: Vessel 12 - Crane moved container 126
Time 8190.018: Vessel 11 - Truck transported container 126 to yard
Time 8190.018: Vessel 11 - Crane moved container 127
Time 8191.617: Vessel 12 - Container 126 loaded onto truck
Time 8193.018: Vessel 11 - Container 127 loaded onto truck
Time 8197.617: Vessel 12 - Truck transported container 126 to yard
Time 8197.617: Vessel 12 - Crane moved container 127
Time 8199.018: Vessel 11 - Truck transported container 127 to yard
Time 8199.018: Vessel 11 - Crane moved container 128
Time 8200.617: Vessel 12 - Container 127 loaded onto truck
Time 8202.018: Vessel 11 - Container 128 loaded onto truck
Time 8206.617: Vessel 12 - Truck transported container 127 to yard
Time 8206.617: Vessel 12 - Crane moved container 128
Time 8208.018: Vessel 11 - Truck transported container 128 to yard
Time 8208.018: Vessel 11 - Crane moved container 129
Time 8209.617: Vessel 12 - Container 128 loaded onto truck
Time 8211.018: Vessel 11 - Container 129 loaded onto truck
Time 8215.617: Vessel 12 - Truck transported container 128 to yard
Time 8215.617: Vessel 12 - Crane moved container 129
Time 8217.018: Vessel 11 - Truck transported container 129 to yard
Time 8217.018: Vessel 11 - Crane moved container 130
Time 8218.617: Vessel 12 - Container 129 loaded onto truck
Time 8220.018: Vessel 11 - Container 130 loaded onto truck
Time 8224.617: Vessel 12 - Truck transported container 129 to yard
Time 8224.617: Vessel 12 - Crane moved container 130
Time 8226.018: Vessel 11 - Truck transported container 130 to yard
Time 8226.018: Vessel 11 - Crane moved container 131
Time 8227.617: Vessel 12 - Container 130 loaded onto truck
Time 8229.018: Vessel 11 - Container 131 loaded onto truck
Time 8233.617: Vessel 12 - Truck transported container 130 to yard
Time 8233.617: Vessel 12 - Crane moved container 131
Time 8235.018: Vessel 11 - Truck transported container 131 to yard
Time 8235.018: Vessel 11 - Crane moved container 132
Time 8236.617: Vessel 12 - Container 131 loaded onto truck
Time 8238.018: Vessel 11 - Container 132 loaded onto truck
Time 8242.617: Vessel 12 - Truck transported container 131 to yard
Time 8242.617: Vessel 12 - Crane moved container 132
Time 8244.018: Vessel 11 - Truck transported container 132 to yard
Time 8244.018: Vessel 11 - Crane moved container 133
Time 8245.617: Vessel 12 - Container 132 loaded onto truck
Time 8247.018: Vessel 11 - Container 133 loaded onto truck
Time 8251.617: Vessel 12 - Truck transported container 132 to yard
Time 8251.617: Vessel 12 - Crane moved container 133
Time 8253.018: Vessel 11 - Truck transported container 133 to yard
Time 8253.018: Vessel 11 - Crane moved container 134
Time 8254.617: Vessel 12 - Container 133 loaded onto truck
Time 8256.018: Vessel 11 - Container 134 loaded onto truck
Time 8260.617: Vessel 12 - Truck transported container 133 to yard
Time 8260.617: Vessel 12 - Crane moved container 134
Time 8262.018: Vessel 11 - Truck transported container 134 to yard
Time 8262.018: Vessel 11 - Crane moved container 135
Time 8263.617: Vessel 12 - Container 134 loaded onto truck
Time 8265.018: Vessel 11 - Container 135 loaded onto truck
Time 8269.617: Vessel 12 - Truck transported container 134 to yard
Time 8269.617: Vessel 12 - Crane moved container 135
Time 8271.018: Vessel 11 - Truck transported container 135 to yard
Time 8271.018: Vessel 11 - Crane moved container 136
Time 8272.617: Vessel 12 - Container 135 loaded onto truck
Time 8274.018: Vessel 11 - Container 136 loaded onto truck
Time 8278.617: Vessel 12 - Truck transported container 135 to yard
Time 8278.617: Vessel 12 - Crane moved container 136
Time 8280.018: Vessel 11 - Truck transported container 136 to yard
Time 8280.018: Vessel 11 - Crane moved container 137
Time 8281.617: Vessel 12 - Container 136 loaded onto truck
Time 8283.018: Vessel 11 - Container 137 loaded onto truck
Time 8287.617: Vessel 12 - Truck transported container 136 to yard
Time 8287.617: Vessel 12 - Crane moved container 137
Time 8289.018: Vessel 11 - Truck transported container 137 to yard
Time 8289.018: Vessel 11 - Crane moved container 138
Time 8290.617: Vessel 12 - Container 137 loaded onto truck
Time 8292.018: Vessel 11 - Container 138 loaded onto truck
Time 8296.617: Vessel 12 - Truck transported container 137 to yard
Time 8296.617: Vessel 12 - Crane moved container 138
Time 8298.018: Vessel 11 - Truck transported container 138 to yard
Time 8298.018: Vessel 11 - Crane moved container 139
Time 8299.617: Vessel 12 - Container 138 loaded onto truck
Time 8301.018: Vessel 11 - Container 139 loaded onto truck
Time 8305.617: Vessel 12 - Truck transported container 138 to yard
Time 8305.617: Vessel 12 - Crane moved container 139
Time 8307.018: Vessel 11 - Truck transported container 139 to yard
Time 8307.018: Vessel 11 - Crane moved container 140
Time 8308.617: Vessel 12 - Container 139 loaded onto truck
Time 8310.018: Vessel 11 - Container 140 loaded onto truck
Time 8314.617: Vessel 12 - Truck transported container 139 to yard
Time 8314.617: Vessel 12 - Crane moved container 140
Time 8316.018: Vessel 11 - Truck transported container 140 to yard
Time 8316.018: Vessel 11 - Crane moved container 141
Time 8317.617: Vessel 12 - Container 140 loaded onto truck
Time 8319.018: Vessel 11 - Container 141 loaded onto truck
Time 8323.617: Vessel 12 - Truck transported container 140 to yard
Time 8323.617: Vessel 12 - Crane moved container 141
Time 8325.018: Vessel 11 - Truck transported container 141 to yard
Time 8325.018: Vessel 11 - Crane moved container 142
Time 8326.617: Vessel 12 - Container 141 loaded onto truck
Time 8328.018: Vessel 11 - Container 142 loaded onto truck
Time 8332.617: Vessel 12 - Truck transported container 141 to yard
Time 8332.617: Vessel 12 - Crane moved container 142
Time 8334.018: Vessel 11 - Truck transported container 142 to yard
Time 8334.018: Vessel 11 - Crane moved container 143
Time 8335.617: Vessel 12 - Container 142 loaded onto truck
Time 8337.018: Vessel 11 - Container 143 loaded onto truck
Time 8341.617: Vessel 12 - Truck transported container 142 to yard
Time 8341.617: Vessel 12 - Crane moved container 143
Time 8343.018: Vessel 11 - Truck transported container 143 to yard
Time 8343.018: Vessel 11 - Crane moved container 144
Time 8344.617: Vessel 12 - Container 143 loaded onto truck
Time 8346.018: Vessel 11 - Container 144 loaded onto truck
Time 8350.617: Vessel 12 - Truck transported container 143 to yard
Time 8350.617: Vessel 12 - Crane moved container 144
Time 8352.018: Vessel 11 - Truck transported container 144 to yard
Time 8352.018: Vessel 11 - Crane moved container 145
Time 8353.617: Vessel 12 - Container 144 loaded onto truck
Time 8355.018: Vessel 11 - Container 145 loaded onto truck
Time 8359.617: Vessel 12 - Truck transported container 144 to yard
Time 8359.617: Vessel 12 - Crane moved container 145
Time 8361.018: Vessel 11 - Truck transported container 145 to yard
Time 8361.018: Vessel 11 - Crane moved container 146
Time 8362.617: Vessel 12 - Container 145 loaded onto truck
Time 8364.018: Vessel 11 - Container 146 loaded onto truck
Time 8368.617: Vessel 12 - Truck transported container 145 to yard
Time 8368.617: Vessel 12 - Crane moved container 146
Time 8370.018: Vessel 11 - Truck transported container 146 to yard
Time 8370.018: Vessel 11 - Crane moved container 147
Time 8371.617: Vessel 12 - Container 146 loaded onto truck
Time 8373.018: Vessel 11 - Container 147 loaded onto truck
Time 8377.617: Vessel 12 - Truck transported container 146 to yard
Time 8377.617: Vessel 12 - Crane moved container 147
Time 8379.018: Vessel 11 - Truck transported container 147 to yard
Time 8379.018: Vessel 11 - Crane moved container 148
Time 8380.617: Vessel 12 - Container 147 loaded onto truck
Time 8382.018: Vessel 11 - Container 148 loaded onto truck
Time 8386.617: Vessel 12 - Truck transported container 147 to yard
Time 8386.617: Vessel 12 - Crane moved container 148
Time 8388.018: Vessel 11 - Truck transported container 148 to yard
Time 8388.018: Vessel 11 - Crane moved container 149
Time 8389.617: Vessel 12 - Container 148 loaded onto truck
Time 8391.018: Vessel 11 - Container 149 loaded onto truck
Time 8395.617: Vessel 12 - Truck transported container 148 to yard
Time 8395.617: Vessel 12 - Crane moved container 149
Time 8397.018: Vessel 11 - Truck transported container 149 to yard
Time 8397.018: Vessel 11 - Crane moved container 150
Time 8398.617: Vessel 12 - Container 149 loaded onto truck
Time 8400.018: Vessel 11 - Container 150 loaded onto truck
Time 8404.617: Vessel 12 - Truck transported container 149 to yard
Time 8404.617: Vessel 12 - Crane moved container 150
Time 8406.018: Vessel 11 - Truck transported container 150 to yard
Time 8406.018: Vessel 11 finished unloading and leaves
Time 8406.018: Vessel 13 berthed
Time 8406.018: Vessel 13 - Crane allocated
Time 8406.018: Vessel 13 - Crane moved container 1
Time 8407.617: Vessel 12 - Container 150 loaded onto truck
Time 8409.018: Vessel 13 - Container 1 loaded onto truck
Time 8413.617: Vessel 12 - Truck transported container 150 to yard
Time 8413.617: Vessel 12 finished unloading and leaves
Time 8413.617: Vessel 14 berthed
Time 8413.617: Vessel 14 - Crane allocated
Time 8413.617: Vessel 14 - Crane moved container 1
Time 8415.018: Vessel 13 - Truck transported container 1 to yard
Time 8415.018: Vessel 13 - Crane moved container 2
Time 8416.617: Vessel 14 - Container 1 loaded onto truck
Time 8418.018: Vessel 13 - Container 2 loaded onto truck
Time 8422.617: Vessel 14 - Truck transported container 1 to yard
Time 8422.617: Vessel 14 - Crane moved container 2
Time 8424.018: Vessel 13 - Truck transported container 2 to yard
Time 8424.018: Vessel 13 - Crane moved container 3
Time 8425.617: Vessel 14 - Container 2 loaded onto truck
Time 8427.018: Vessel 13 - Container 3 loaded onto truck
Time 8431.617: Vessel 14 - Truck transported container 2 to yard
Time 8431.617: Vessel 14 - Crane moved container 3
Time 8433.018: Vessel 13 - Truck transported container 3 to yard
Time 8433.018: Vessel 13 - Crane moved container 4
Time 8434.617: Vessel 14 - Container 3 loaded onto truck
Time 8436.018: Vessel 13 - Container 4 loaded onto truck
Time 8440.617: Vessel 14 - Truck transported container 3 to yard
Time 8440.617: Vessel 14 - Crane moved container 4
Time 8442.018: Vessel 13 - Truck transported container 4 to yard
Time 8442.018: Vessel 13 - Crane moved container 5
Time 8443.617: Vessel 14 - Container 4 loaded onto truck
Time 8445.018: Vessel 13 - Container 5 loaded onto truck
Time 8449.617: Vessel 14 - Truck transported container 4 to yard
Time 8449.617: Vessel 14 - Crane moved container 5
Time 8451.018: Vessel 13 - Truck transported container 5 to yard
Time 8451.018: Vessel 13 - Crane moved container 6
Time 8452.617: Vessel 14 - Container 5 loaded onto truck
Time 8454.018: Vessel 13 - Container 6 loaded onto truck
Time 8458.617: Vessel 14 - Truck transported container 5 to yard
Time 8458.617: Vessel 14 - Crane moved container 6
Time 8460.018: Vessel 13 - Truck transported container 6 to yard
Time 8460.018: Vessel 13 - Crane moved container 7
Time 8461.617: Vessel 14 - Container 6 loaded onto truck
Time 8463.018: Vessel 13 - Container 7 loaded onto truck
Time 8467.617: Vessel 14 - Truck transported container 6 to yard
Time 8467.617: Vessel 14 - Crane moved container 7
Time 8469.018: Vessel 13 - Truck transported container 7 to yard
Time 8469.018: Vessel 13 - Crane moved container 8
Time 8470.617: Vessel 14 - Container 7 loaded onto truck
Time 8472.018: Vessel 13 - Container 8 loaded onto truck
Time 8476.617: Vessel 14 - Truck transported container 7 to yard
Time 8476.617: Vessel 14 - Crane moved container 8
Time 8478.018: Vessel 13 - Truck transported container 8 to yard
Time 8478.018: Vessel 13 - Crane moved container 9
Time 8479.617: Vessel 14 - Container 8 loaded onto truck
Time 8481.018: Vessel 13 - Container 9 loaded onto truck
Time 8485.617: Vessel 14 - Truck transported container 8 to yard
Time 8485.617: Vessel 14 - Crane moved container 9
Time 8487.018: Vessel 13 - Truck transported container 9 to yard
Time 8487.018: Vessel 13 - Crane moved container 10
Time 8488.617: Vessel 14 - Container 9 loaded onto truck
Time 8490.018: Vessel 13 - Container 10 loaded onto truck
Time 8494.617: Vessel 14 - Truck transported container 9 to yard
Time 8494.617: Vessel 14 - Crane moved container 10
Time 8496.018: Vessel 13 - Truck transported container 10 to yard
Time 8496.018: Vessel 13 - Crane moved container 11
Time 8497.617: Vessel 14 - Container 10 loaded onto truck
Time 8499.018: Vessel 13 - Container 11 loaded onto truck
Time 8503.617: Vessel 14 - Truck transported container 10 to yard
Time 8503.617: Vessel 14 - Crane moved container 11
Time 8505.018: Vessel 13 - Truck transported container 11 to yard
Time 8505.018: Vessel 13 - Crane moved container 12
Time 8506.617: Vessel 14 - Container 11 loaded onto truck
Time 8508.018: Vessel 13 - Container 12 loaded onto truck
Time 8512.617: Vessel 14 - Truck transported container 11 to yard
Time 8512.617: Vessel 14 - Crane moved container 12
Time 8514.018: Vessel 13 - Truck transported container 12 to yard
Time 8514.018: Vessel 13 - Crane moved container 13
Time 8515.617: Vessel 14 - Container 12 loaded onto truck
Time 8517.018: Vessel 13 - Container 13 loaded onto truck
Time 8521.617: Vessel 14 - Truck transported container 12 to yard
Time 8521.617: Vessel 14 - Crane moved container 13
Time 8523.018: Vessel 13 - Truck transported container 13 to yard
Time 8523.018: Vessel 13 - Crane moved container 14
Time 8524.617: Vessel 14 - Container 13 loaded onto truck
Time 8526.018: Vessel 13 - Container 14 loaded onto truck
Time 8530.617: Vessel 14 - Truck transported container 13 to yard
Time 8530.617: Vessel 14 - Crane moved container 14
Time 8532.018: Vessel 13 - Truck transported container 14 to yard
Time 8532.018: Vessel 13 - Crane moved container 15
Time 8533.617: Vessel 14 - Container 14 loaded onto truck
Time 8535.018: Vessel 13 - Container 15 loaded onto truck
Time 8539.617: Vessel 14 - Truck transported container 14 to yard
Time 8539.617: Vessel 14 - Crane moved container 15
Time 8541.018: Vessel 13 - Truck transported container 15 to yard
Time 8541.018: Vessel 13 - Crane moved container 16
Time 8542.617: Vessel 14 - Container 15 loaded onto truck
Time 8544.018: Vessel 13 - Container 16 loaded onto truck
Time 8548.617: Vessel 14 - Truck transported container 15 to yard
Time 8548.617: Vessel 14 - Crane moved container 16
Time 8550.018: Vessel 13 - Truck transported container 16 to yard
Time 8550.018: Vessel 13 - Crane moved container 17
Time 8551.617: Vessel 14 - Container 16 loaded onto truck
Time 8553.018: Vessel 13 - Container 17 loaded onto truck
Time 8557.617: Vessel 14 - Truck transported container 16 to yard
Time 8557.617: Vessel 14 - Crane moved container 17
Time 8559.018: Vessel 13 - Truck transported container 17 to yard
Time 8559.018: Vessel 13 - Crane moved container 18
Time 8560.617: Vessel 14 - Container 17 loaded onto truck
Time 8562.018: Vessel 13 - Container 18 loaded onto truck
Time 8566.617: Vessel 14 - Truck transported container 17 to yard
Time 8566.617: Vessel 14 - Crane moved container 18
Time 8568.018: Vessel 13 - Truck transported container 18 to yard
Time 8568.018: Vessel 13 - Crane moved container 19
Time 8569.617: Vessel 14 - Container 18 loaded onto truck
Time 8571.018: Vessel 13 - Container 19 loaded onto truck
Time 8575.617: Vessel 14 - Truck transported container 18 to yard
Time 8575.617: Vessel 14 - Crane moved container 19
Time 8577.018: Vessel 13 - Truck transported container 19 to yard
Time 8577.018: Vessel 13 - Crane moved container 20
Time 8578.617: Vessel 14 - Container 19 loaded onto truck
Time 8580.018: Vessel 13 - Container 20 loaded onto truck
Time 8584.617: Vessel 14 - Truck transported container 19 to yard
Time 8584.617: Vessel 14 - Crane moved container 20
Time 8586.018: Vessel 13 - Truck transported container 20 to yard
Time 8586.018: Vessel 13 - Crane moved container 21
Time 8587.617: Vessel 14 - Container 20 loaded onto truck
Time 8589.018: Vessel 13 - Container 21 loaded onto truck
Time 8593.617: Vessel 14 - Truck transported container 20 to yard
Time 8593.617: Vessel 14 - Crane moved container 21
Time 8595.018: Vessel 13 - Truck transported container 21 to yard
Time 8595.018: Vessel 13 - Crane moved container 22
Time 8596.617: Vessel 14 - Container 21 loaded onto truck
Time 8598.018: Vessel 13 - Container 22 loaded onto truck
Time 8602.617: Vessel 14 - Truck transported container 21 to yard
Time 8602.617: Vessel 14 - Crane moved container 22
Time 8604.018: Vessel 13 - Truck transported container 22 to yard
Time 8604.018: Vessel 13 - Crane moved container 23
Time 8605.617: Vessel 14 - Container 22 loaded onto truck
Time 8607.018: Vessel 13 - Container 23 loaded onto truck
Time 8611.617: Vessel 14 - Truck transported container 22 to yard
Time 8611.617: Vessel 14 - Crane moved container 23
Time 8613.018: Vessel 13 - Truck transported container 23 to yard
Time 8613.018: Vessel 13 - Crane moved container 24
Time 8614.617: Vessel 14 - Container 23 loaded onto truck
Time 8616.018: Vessel 13 - Container 24 loaded onto truck
Time 8620.617: Vessel 14 - Truck transported container 23 to yard
Time 8620.617: Vessel 14 - Crane moved container 24
Time 8622.018: Vessel 13 - Truck transported container 24 to yard
Time 8622.018: Vessel 13 - Crane moved container 25
Time 8623.617: Vessel 14 - Container 24 loaded onto truck
Time 8625.018: Vessel 13 - Container 25 loaded onto truck
Time 8629.617: Vessel 14 - Truck transported container 24 to yard
Time 8629.617: Vessel 14 - Crane moved container 25
Time 8631.018: Vessel 13 - Truck transported container 25 to yard
Time 8631.018: Vessel 13 - Crane moved container 26
Time 8632.617: Vessel 14 - Container 25 loaded onto truck
Time 8634.018: Vessel 13 - Container 26 loaded onto truck
Time 8638.617: Vessel 14 - Truck transported container 25 to yard
Time 8638.617: Vessel 14 - Crane moved container 26
Time 8640.018: Vessel 13 - Truck transported container 26 to yard
Time 8640.018: Vessel 13 - Crane moved container 27
Time 8641.617: Vessel 14 - Container 26 loaded onto truck
Time 8643.018: Vessel 13 - Container 27 loaded onto truck
Time 8647.617: Vessel 14 - Truck transported container 26 to yard
Time 8647.617: Vessel 14 - Crane moved container 27
Time 8649.018: Vessel 13 - Truck transported container 27 to yard
Time 8649.018: Vessel 13 - Crane moved container 28
Time 8650.617: Vessel 14 - Container 27 loaded onto truck
Time 8652.018: Vessel 13 - Container 28 loaded onto truck
Time 8656.617: Vessel 14 - Truck transported container 27 to yard
Time 8656.617: Vessel 14 - Crane moved container 28
Time 8658.018: Vessel 13 - Truck transported container 28 to yard
Time 8658.018: Vessel 13 - Crane moved container 29
Time 8659.617: Vessel 14 - Container 28 loaded onto truck
Time 8661.018: Vessel 13 - Container 29 loaded onto truck
Time 8665.617: Vessel 14 - Truck transported container 28 to yard
Time 8665.617: Vessel 14 - Crane moved container 29
Time 8667.018: Vessel 13 - Truck transported container 29 to yard
Time 8667.018: Vessel 13 - Crane moved container 30
Time 8668.617: Vessel 14 - Container 29 loaded onto truck
Time 8670.018: Vessel 13 - Container 30 loaded onto truck
Time 8674.617: Vessel 14 - Truck transported container 29 to yard
Time 8674.617: Vessel 14 - Crane moved container 30
Time 8676.018: Vessel 13 - Truck transported container 30 to yard
Time 8676.018: Vessel 13 - Crane moved container 31
Time 8677.617: Vessel 14 - Container 30 loaded onto truck
Time 8679.018: Vessel 13 - Container 31 loaded onto truck
Time 8683.617: Vessel 14 - Truck transported container 30 to yard
Time 8683.617: Vessel 14 - Crane moved container 31
Time 8685.018: Vessel 13 - Truck transported container 31 to yard
Time 8685.018: Vessel 13 - Crane moved container 32
Time 8686.617: Vessel 14 - Container 31 loaded onto truck
Time 8688.018: Vessel 13 - Container 32 loaded onto truck
Time 8692.617: Vessel 14 - Truck transported container 31 to yard
Time 8692.617: Vessel 14 - Crane moved container 32
Time 8694.018: Vessel 13 - Truck transported container 32 to yard
Time 8694.018: Vessel 13 - Crane moved container 33
Time 8695.617: Vessel 14 - Container 32 loaded onto truck
Time 8697.018: Vessel 13 - Container 33 loaded onto truck
Time 8701.617: Vessel 14 - Truck transported container 32 to yard
Time 8701.617: Vessel 14 - Crane moved container 33
Time 8703.018: Vessel 13 - Truck transported container 33 to yard
Time 8703.018: Vessel 13 - Crane moved container 34
Time 8704.617: Vessel 14 - Container 33 loaded onto truck
Time 8706.018: Vessel 13 - Container 34 loaded onto truck
Time 8710.617: Vessel 14 - Truck transported container 33 to yard
Time 8710.617: Vessel 14 - Crane moved container 34
Time 8712.018: Vessel 13 - Truck transported container 34 to yard
Time 8712.018: Vessel 13 - Crane moved container 35
Time 8713.617: Vessel 14 - Container 34 loaded onto truck
Time 8715.018: Vessel 13 - Container 35 loaded onto truck
Time 8719.617: Vessel 14 - Truck transported container 34 to yard
Time 8719.617: Vessel 14 - Crane moved container 35
Time 8721.018: Vessel 13 - Truck transported container 35 to yard
Time 8721.018: Vessel 13 - Crane moved container 36
Time 8722.617: Vessel 14 - Container 35 loaded onto truck
Time 8724.018: Vessel 13 - Container 36 loaded onto truck
Time 8728.617: Vessel 14 - Truck transported container 35 to yard
Time 8728.617: Vessel 14 - Crane moved container 36
Time 8730.018: Vessel 13 - Truck transported container 36 to yard
Time 8730.018: Vessel 13 - Crane moved container 37
Time 8731.617: Vessel 14 - Container 36 loaded onto truck
Time 8733.018: Vessel 13 - Container 37 loaded onto truck
Time 8737.617: Vessel 14 - Truck transported container 36 to yard
Time 8737.617: Vessel 14 - Crane moved container 37
Time 8739.018: Vessel 13 - Truck transported container 37 to yard
Time 8739.018: Vessel 13 - Crane moved container 38
Time 8740.617: Vessel 14 - Container 37 loaded onto truck
Time 8742.018: Vessel 13 - Container 38 loaded onto truck
Time 8746.617: Vessel 14 - Truck transported container 37 to yard
Time 8746.617: Vessel 14 - Crane moved container 38
Time 8748.018: Vessel 13 - Truck transported container 38 to yard
Time 8748.018: Vessel 13 - Crane moved container 39
Time 8749.617: Vessel 14 - Container 38 loaded onto truck
Time 8751.018: Vessel 13 - Container 39 loaded onto truck
Time 8755.617: Vessel 14 - Truck transported container 38 to yard
Time 8755.617: Vessel 14 - Crane moved container 39
Time 8757.018: Vessel 13 - Truck transported container 39 to yard
Time 8757.018: Vessel 13 - Crane moved container 40
Time 8758.617: Vessel 14 - Container 39 loaded onto truck
Time 8760.018: Vessel 13 - Container 40 loaded onto truck
Time 8764.617: Vessel 14 - Truck transported container 39 to yard
Time 8764.617: Vessel 14 - Crane moved container 40
Time 8766.018: Vessel 13 - Truck transported container 40 to yard
Time 8766.018: Vessel 13 - Crane moved container 41
Time 8767.617: Vessel 14 - Container 40 loaded onto truck
Time 8769.018: Vessel 13 - Container 41 loaded onto truck
Time 8773.617: Vessel 14 - Truck transported container 40 to yard
Time 8773.617: Vessel 14 - Crane moved container 41
Time 8775.018: Vessel 13 - Truck transported container 41 to yard
Time 8775.018: Vessel 13 - Crane moved container 42
Time 8776.617: Vessel 14 - Container 41 loaded onto truck
Time 8778.018: Vessel 13 - Container 42 loaded onto truck
Time 8782.617: Vessel 14 - Truck transported container 41 to yard
Time 8782.617: Vessel 14 - Crane moved container 42
Time 8784.018: Vessel 13 - Truck transported container 42 to yard
Time 8784.018: Vessel 13 - Crane moved container 43
Time 8785.617: Vessel 14 - Container 42 loaded onto truck
Time 8787.018: Vessel 13 - Container 43 loaded onto truck
Time 8791.617: Vessel 14 - Truck transported container 42 to yard
Time 8791.617: Vessel 14 - Crane moved container 43
Time 8793.018: Vessel 13 - Truck transported container 43 to yard
Time 8793.018: Vessel 13 - Crane moved container 44
Time 8794.617: Vessel 14 - Container 43 loaded onto truck
Time 8796.018: Vessel 13 - Container 44 loaded onto truck
Time 8800.617: Vessel 14 - Truck transported container 43 to yard
Time 8800.617: Vessel 14 - Crane moved container 44
Time 8802.018: Vessel 13 - Truck transported container 44 to yard
Time 8802.018: Vessel 13 - Crane moved container 45
Time 8803.617: Vessel 14 - Container 44 loaded onto truck
Time 8805.018: Vessel 13 - Container 45 loaded onto truck
Time 8809.617: Vessel 14 - Truck transported container 44 to yard
Time 8809.617: Vessel 14 - Crane moved container 45
Time 8811.018: Vessel 13 - Truck transported container 45 to yard
Time 8811.018: Vessel 13 - Crane moved container 46
Time 8812.617: Vessel 14 - Container 45 loaded onto truck
Time 8814.018: Vessel 13 - Container 46 loaded onto truck
Time 8818.617: Vessel 14 - Truck transported container 45 to yard
Time 8818.617: Vessel 14 - Crane moved container 46
Time 8820.018: Vessel 13 - Truck transported container 46 to yard
Time 8820.018: Vessel 13 - Crane moved container 47
Time 8821.617: Vessel 14 - Container 46 loaded onto truck
Time 8823.018: Vessel 13 - Container 47 loaded onto truck
Time 8827.617: Vessel 14 - Truck transported container 46 to yard
Time 8827.617: Vessel 14 - Crane moved container 47
Time 8829.018: Vessel 13 - Truck transported container 47 to yard
Time 8829.018: Vessel 13 - Crane moved container 48
Time 8830.617: Vessel 14 - Container 47 loaded onto truck
Time 8832.018: Vessel 13 - Container 48 loaded onto truck
Time 8836.617: Vessel 14 - Truck transported container 47 to yard
Time 8836.617: Vessel 14 - Crane moved container 48
Time 8838.018: Vessel 13 - Truck transported container 48 to yard
Time 8838.018: Vessel 13 - Crane moved container 49
Time 8839.617: Vessel 14 - Container 48 loaded onto truck
Time 8841.018: Vessel 13 - Container 49 loaded onto truck
Time 8845.617: Vessel 14 - Truck transported container 48 to yard
Time 8845.617: Vessel 14 - Crane moved container 49
Time 8847.018: Vessel 13 - Truck transported container 49 to yard
Time 8847.018: Vessel 13 - Crane moved container 50
Time 8848.617: Vessel 14 - Container 49 loaded onto truck
Time 8850.018: Vessel 13 - Container 50 loaded onto truck
Time 8854.617: Vessel 14 - Truck transported container 49 to yard
Time 8854.617: Vessel 14 - Crane moved container 50
Time 8856.018: Vessel 13 - Truck transported container 50 to yard
Time 8856.018: Vessel 13 - Crane moved container 51
Time 8857.617: Vessel 14 - Container 50 loaded onto truck
Time 8859.018: Vessel 13 - Container 51 loaded onto truck
Time 8863.617: Vessel 14 - Truck transported container 50 to yard
Time 8863.617: Vessel 14 - Crane moved container 51
Time 8865.018: Vessel 13 - Truck transported container 51 to yard
Time 8865.018: Vessel 13 - Crane moved container 52
Time 8866.617: Vessel 14 - Container 51 loaded onto truck
Time 8868.018: Vessel 13 - Container 52 loaded onto truck
Time 8872.617: Vessel 14 - Truck transported container 51 to yard
Time 8872.617: Vessel 14 - Crane moved container 52
Time 8874.018: Vessel 13 - Truck transported container 52 to yard
Time 8874.018: Vessel 13 - Crane moved container 53
Time 8875.617: Vessel 14 - Container 52 loaded onto truck
Time 8877.018: Vessel 13 - Container 53 loaded onto truck
Time 8881.617: Vessel 14 - Truck transported container 52 to yard
Time 8881.617: Vessel 14 - Crane moved container 53
Time 8883.018: Vessel 13 - Truck transported container 53 to yard
Time 8883.018: Vessel 13 - Crane moved container 54
Time 8884.617: Vessel 14 - Container 53 loaded onto truck
Time 8886.018: Vessel 13 - Container 54 loaded onto truck
Time 8890.617: Vessel 14 - Truck transported container 53 to yard
Time 8890.617: Vessel 14 - Crane moved container 54
Time 8892.018: Vessel 13 - Truck transported container 54 to yard
Time 8892.018: Vessel 13 - Crane moved container 55
Time 8893.617: Vessel 14 - Container 54 loaded onto truck
Time 8895.018: Vessel 13 - Container 55 loaded onto truck
Time 8899.617: Vessel 14 - Truck transported container 54 to yard
Time 8899.617: Vessel 14 - Crane moved container 55
Time 8901.018: Vessel 13 - Truck transported container 55 to yard
Time 8901.018: Vessel 13 - Crane moved container 56
Time 8902.617: Vessel 14 - Container 55 loaded onto truck
Time 8904.018: Vessel 13 - Container 56 loaded onto truck
Time 8908.617: Vessel 14 - Truck transported container 55 to yard
Time 8908.617: Vessel 14 - Crane moved container 56
Time 8910.018: Vessel 13 - Truck transported container 56 to yard
Time 8910.018: Vessel 13 - Crane moved container 57
Time 8911.617: Vessel 14 - Container 56 loaded onto truck
Time 8913.018: Vessel 13 - Container 57 loaded onto truck
Time 8917.617: Vessel 14 - Truck transported container 56 to yard
Time 8917.617: Vessel 14 - Crane moved container 57
Time 8919.018: Vessel 13 - Truck transported container 57 to yard
Time 8919.018: Vessel 13 - Crane moved container 58
Time 8920.617: Vessel 14 - Container 57 loaded onto truck
Time 8922.018: Vessel 13 - Container 58 loaded onto truck
Time 8926.617: Vessel 14 - Truck transported container 57 to yard
Time 8926.617: Vessel 14 - Crane moved container 58
Time 8928.018: Vessel 13 - Truck transported container 58 to yard
Time 8928.018: Vessel 13 - Crane moved container 59
Time 8929.617: Vessel 14 - Container 58 loaded onto truck
Time 8931.018: Vessel 13 - Container 59 loaded onto truck
Time 8935.617: Vessel 14 - Truck transported container 58 to yard
Time 8935.617: Vessel 14 - Crane moved container 59
Time 8937.018: Vessel 13 - Truck transported container 59 to yard
Time 8937.018: Vessel 13 - Crane moved container 60
Time 8938.617: Vessel 14 - Container 59 loaded onto truck
Time 8940.018: Vessel 13 - Container 60 loaded onto truck
Time 8944.617: Vessel 14 - Truck transported container 59 to yard
Time 8944.617: Vessel 14 - Crane moved container 60
Time 8946.018: Vessel 13 - Truck transported container 60 to yard
Time 8946.018: Vessel 13 - Crane moved container 61
Time 8947.617: Vessel 14 - Container 60 loaded onto truck
Time 8949.018: Vessel 13 - Container 61 loaded onto truck
Time 8953.617: Vessel 14 - Truck transported container 60 to yard
Time 8953.617: Vessel 14 - Crane moved container 61
Time 8955.018: Vessel 13 - Truck transported container 61 to yard
Time 8955.018: Vessel 13 - Crane moved container 62
Time 8956.617: Vessel 14 - Container 61 loaded onto truck
Time 8958.018: Vessel 13 - Container 62 loaded onto truck
Time 8962.617: Vessel 14 - Truck transported container 61 to yard
Time 8962.617: Vessel 14 - Crane moved container 62
Time 8964.018: Vessel 13 - Truck transported container 62 to yard
Time 8964.018: Vessel 13 - Crane moved container 63
Time 8965.617: Vessel 14 - Container 62 loaded onto truck
Time 8967.018: Vessel 13 - Container 63 loaded onto truck
Time 8971.617: Vessel 14 - Truck transported container 62 to yard
Time 8971.617: Vessel 14 - Crane moved container 63
Time 8973.018: Vessel 13 - Truck transported container 63 to yard
Time 8973.018: Vessel 13 - Crane moved container 64
Time 8974.617: Vessel 14 - Container 63 loaded onto truck
Time 8976.018: Vessel 13 - Container 64 loaded onto truck
Time 8980.617: Vessel 14 - Truck transported container 63 to yard
Time 8980.617: Vessel 14 - Crane moved container 64
Time 8982.018: Vessel 13 - Truck transported container 64 to yard
Time 8982.018: Vessel 13 - Crane moved container 65
Time 8983.617: Vessel 14 - Container 64 loaded onto truck
Time 8985.018: Vessel 13 - Container 65 loaded onto truck
Time 8989.617: Vessel 14 - Truck transported container 64 to yard
Time 8989.617: Vessel 14 - Crane moved container 65
Time 8991.018: Vessel 13 - Truck transported container 65 to yard
Time 8991.018: Vessel 13 - Crane moved container 66
Time 8992.617: Vessel 14 - Container 65 loaded onto truck
Time 8994.018: Vessel 13 - Container 66 loaded onto truck
Time 8998.617: Vessel 14 - Truck transported container 65 to yard
Time 8998.617: Vessel 14 - Crane moved container 66
Time 9000.018: Vessel 13 - Truck transported container 66 to yard
Time 9000.018: Vessel 13 - Crane moved container 67
Time 9001.617: Vessel 14 - Container 66 loaded onto truck
Time 9003.018: Vessel 13 - Container 67 loaded onto truck
Time 9007.617: Vessel 14 - Truck transported container 66 to yard
Time 9007.617: Vessel 14 - Crane moved container 67
Time 9009.018: Vessel 13 - Truck transported container 67 to yard
Time 9009.018: Vessel 13 - Crane moved container 68
Time 9010.617: Vessel 14 - Container 67 loaded onto truck
Time 9012.018: Vessel 13 - Container 68 loaded onto truck
Time 9016.617: Vessel 14 - Truck transported container 67 to yard
Time 9016.617: Vessel 14 - Crane moved container 68
Time 9018.018: Vessel 13 - Truck transported container 68 to yard
Time 9018.018: Vessel 13 - Crane moved container 69
Time 9019.617: Vessel 14 - Container 68 loaded onto truck
Time 9021.018: Vessel 13 - Container 69 loaded onto truck
Time 9025.617: Vessel 14 - Truck transported container 68 to yard
Time 9025.617: Vessel 14 - Crane moved container 69
Time 9027.018: Vessel 13 - Truck transported container 69 to yard
Time 9027.018: Vessel 13 - Crane moved container 70
Time 9028.617: Vessel 14 - Container 69 loaded onto truck
Time 9030.018: Vessel 13 - Container 70 loaded onto truck
Time 9034.617: Vessel 14 - Truck transported container 69 to yard
Time 9034.617: Vessel 14 - Crane moved container 70
Time 9036.018: Vessel 13 - Truck transported container 70 to yard
Time 9036.018: Vessel 13 - Crane moved container 71
Time 9037.617: Vessel 14 - Container 70 loaded onto truck
Time 9039.018: Vessel 13 - Container 71 loaded onto truck
Time 9043.617: Vessel 14 - Truck transported container 70 to yard
Time 9043.617: Vessel 14 - Crane moved container 71
Time 9043.640: Vessel 34 Arrived
Time 9043.640: Vessel 34 Waiting for a berth
Time 9045.018: Vessel 13 - Truck transported container 71 to yard
Time 9045.018: Vessel 13 - Crane moved container 72
Time 9046.617: Vessel 14 - Container 71 loaded onto truck
Time 9048.018: Vessel 13 - Container 72 loaded onto truck
Time 9052.617: Vessel 14 - Truck transported container 71 to yard
Time 9052.617: Vessel 14 - Crane moved container 72
Time 9054.018: Vessel 13 - Truck transported container 72 to yard
Time 9054.018: Vessel 13 - Crane moved container 73
Time 9055.617: Vessel 14 - Container 72 loaded onto truck
Time 9057.018: Vessel 13 - Container 73 loaded onto truck
Time 9061.617: Vessel 14 - Truck transported container 72 to yard
Time 9061.617: Vessel 14 - Crane moved container 73
Time 9063.018: Vessel 13 - Truck transported container 73 to yard
Time 9063.018: Vessel 13 - Crane moved container 74
Time 9064.617: Vessel 14 - Container 73 loaded onto truck
Time 9066.018: Vessel 13 - Container 74 loaded onto truck
Time 9070.617: Vessel 14 - Truck transported container 73 to yard
Time 9070.617: Vessel 14 - Crane moved container 74
Time 9072.018: Vessel 13 - Truck transported container 74 to yard
Time 9072.018: Vessel 13 - Crane moved container 75
Time 9073.617: Vessel 14 - Container 74 loaded onto truck
Time 9075.018: Vessel 13 - Container 75 loaded onto truck
Time 9079.617: Vessel 14 - Truck transported container 74 to yard
Time 9079.617: Vessel 14 - Crane moved container 75
Time 9081.018: Vessel 13 - Truck transported container 75 to yard
Time 9081.018: Vessel 13 - Crane moved container 76
Time 9082.617: Vessel 14 - Container 75 loaded onto truck
Time 9084.018: Vessel 13 - Container 76 loaded onto truck
Time 9088.617: Vessel 14 - Truck transported container 75 to yard
Time 9088.617: Vessel 14 - Crane moved container 76
Time 9090.018: Vessel 13 - Truck transported container 76 to yard
Time 9090.018: Vessel 13 - Crane moved container 77
Time 9091.617: Vessel 14 - Container 76 loaded onto truck
Time 9093.018: Vessel 13 - Container 77 loaded onto truck
Time 9097.617: Vessel 14 - Truck transported container 76 to yard
Time 9097.617: Vessel 14 - Crane moved container 77
Time 9099.018: Vessel 13 - Truck transported container 77 to yard
Time 9099.018: Vessel 13 - Crane moved container 78
Time 9100.617: Vessel 14 - Container 77 loaded onto truck
Time 9102.018: Vessel 13 - Container 78 loaded onto truck
Time 9106.617: Vessel 14 - Truck transported container 77 to yard
Time 9106.617: Vessel 14 - Crane moved container 78
Time 9108.018: Vessel 13 - Truck transported container 78 to yard
Time 9108.018: Vessel 13 - Crane moved container 79
Time 9109.617: Vessel 14 - Container 78 loaded onto truck
Time 9111.018: Vessel 13 - Container 79 loaded onto truck
Time 9115.617: Vessel 14 - Truck transported container 78 to yard
Time 9115.617: Vessel 14 - Crane moved container 79
Time 9117.018: Vessel 13 - Truck transported container 79 to yard
Time 9117.018: Vessel 13 - Crane moved container 80
Time 9118.617: Vessel 14 - Container 79 loaded onto truck
Time 9120.018: Vessel 13 - Container 80 loaded onto truck
Time 9124.617: Vessel 14 - Truck transported container 79 to yard
Time 9124.617: Vessel 14 - Crane moved container 80
Time 9126.018: Vessel 13 - Truck transported container 80 to yard
Time 9126.018: Vessel 13 - Crane moved container 81
Time 9127.617: Vessel 14 - Container 80 loaded onto truck
Time 9129.018: Vessel 13 - Container 81 loaded onto truck
Time 9133.617: Vessel 14 - Truck transported container 80 to yard
Time 9133.617: Vessel 14 - Crane moved container 81
Time 9135.018: Vessel 13 - Truck transported container 81 to yard
Time 9135.018: Vessel 13 - Crane moved container 82
Time 9136.617: Vessel 14 - Container 81 loaded onto truck
Time 9138.018: Vessel 13 - Container 82 loaded onto truck
Time 9142.617: Vessel 14 - Truck transported container 81 to yard
Time 9142.617: Vessel 14 - Crane moved container 82
Time 9144.018: Vessel 13 - Truck transported container 82 to yard
Time 9144.018: Vessel 13 - Crane moved container 83
Time 9145.617: Vessel 14 - Container 82 loaded onto truck
Time 9147.018: Vessel 13 - Container 83 loaded onto truck
Time 9151.617: Vessel 14 - Truck transported container 82 to yard
Time 9151.617: Vessel 14 - Crane moved container 83
Time 9153.018: Vessel 13 - Truck transported container 83 to yard
Time 9153.018: Vessel 13 - Crane moved container 84
Time 9154.617: Vessel 14 - Container 83 loaded onto truck
Time 9156.018: Vessel 13 - Container 84 loaded onto truck
Time 9160.617: Vessel 14 - Truck transported container 83 to yard
Time 9160.617: Vessel 14 - Crane moved container 84
Time 9162.018: Vessel 13 - Truck transported container 84 to yard
Time 9162.018: Vessel 13 - Crane moved container 85
Time 9163.617: Vessel 14 - Container 84 loaded onto truck
Time 9165.018: Vessel 13 - Container 85 loaded onto truck
Time 9169.617: Vessel 14 - Truck transported container 84 to yard
Time 9169.617: Vessel 14 - Crane moved container 85
Time 9171.018: Vessel 13 - Truck transported container 85 to yard
Time 9171.018: Vessel 13 - Crane moved container 86
Time 9172.617: Vessel 14 - Container 85 loaded onto truck
Time 9174.018: Vessel 13 - Container 86 loaded onto truck
Time 9178.617: Vessel 14 - Truck transported container 85 to yard
Time 9178.617: Vessel 14 - Crane moved container 86
Time 9180.018: Vessel 13 - Truck transported container 86 to yard
Time 9180.018: Vessel 13 - Crane moved container 87
Time 9181.617: Vessel 14 - Container 86 loaded onto truck
Time 9183.018: Vessel 13 - Container 87 loaded onto truck
Time 9186.342: Vessel 35 Arrived
Time 9186.342: Vessel 35 Waiting for a berth
Time 9187.617: Vessel 14 - Truck transported container 86 to yard
Time 9187.617: Vessel 14 - Crane moved container 87
Time 9189.018: Vessel 13 - Truck transported container 87 to yard
Time 9189.018: Vessel 13 - Crane moved container 88
Time 9190.617: Vessel 14 - Container 87 loaded onto truck
Time 9192.018: Vessel 13 - Container 88 loaded onto truck
Time 9196.617: Vessel 14 - Truck transported container 87 to yard
Time 9196.617: Vessel 14 - Crane moved container 88
Time 9198.018: Vessel 13 - Truck transported container 88 to yard
Time 9198.018: Vessel 13 - Crane moved container 89
Time 9199.617: Vessel 14 - Container 88 loaded onto truck
Time 9201.018: Vessel 13 - Container 89 loaded onto truck
Time 9205.617: Vessel 14 - Truck transported container 88 to yard
Time 9205.617: Vessel 14 - Crane moved container 89
Time 9207.018: Vessel 13 - Truck transported container 89 to yard
Time 9207.018: Vessel 13 - Crane moved container 90
Time 9208.617: Vessel 14 - Container 89 loaded onto truck
Time 9210.018: Vessel 13 - Container 90 loaded onto truck
Time 9214.617: Vessel 14 - Truck transported container 89 to yard
Time 9214.617: Vessel 14 - Crane moved container 90
Time 9216.018: Vessel 13 - Truck transported container 90 to yard
Time 9216.018: Vessel 13 - Crane moved container 91
Time 9217.617: Vessel 14 - Container 90 loaded onto truck
Time 9219.018: Vessel 13 - Container 91 loaded onto truck
Time 9223.617: Vessel 14 - Truck transported container 90 to yard
Time 9223.617: Vessel 14 - Crane moved container 91
Time 9225.018: Vessel 13 - Truck transported container 91 to yard
Time 9225.018: Vessel 13 - Crane moved container 92
Time 9226.617: Vessel 14 - Container 91 loaded onto truck
Time 9228.018: Vessel 13 - Container 92 loaded onto truck
Time 9232.617: Vessel 14 - Truck transported container 91 to yard
Time 9232.617: Vessel 14 - Crane moved container 92
Time 9234.018: Vessel 13 - Truck transported container 92 to yard
Time 9234.018: Vessel 13 - Crane moved container 93
Time 9235.617: Vessel 14 - Container 92 loaded onto truck
Time 9237.018: Vessel 13 - Container 93 loaded onto truck
Time 9241.617: Vessel 14 - Truck transported container 92 to yard
Time 9241.617: Vessel 14 - Crane moved container 93
Time 9243.018: Vessel 13 - Truck transported container 93 to yard
Time 9243.018: Vessel 13 - Crane moved container 94
Time 9244.617: Vessel 14 - Container 93 loaded onto truck
Time 9246.018: Vessel 13 - Container 94 loaded onto truck
Time 9250.617: Vessel 14 - Truck transported container 93 to yard
Time 9250.617: Vessel 14 - Crane moved container 94
Time 9252.018: Vessel 13 - Truck transported container 94 to yard
Time 9252.018: Vessel 13 - Crane moved container 95
Time 9253.617: Vessel 14 - Container 94 loaded onto truck
Time 9255.018: Vessel 13 - Container 95 loaded onto truck
Time 9259.617: Vessel 14 - Truck transported container 94 to yard
Time 9259.617: Vessel 14 - Crane moved container 95
Time 9261.018: Vessel 13 - Truck transported container 95 to yard
Time 9261.018: Vessel 13 - Crane moved container 96
Time 9262.617: Vessel 14 - Container 95 loaded onto truck
Time 9264.018: Vessel 13 - Container 96 loaded onto truck
Time 9268.617: Vessel 14 - Truck transported container 95 to yard
Time 9268.617: Vessel 14 - Crane moved container 96
Time 9270.018: Vessel 13 - Truck transported container 96 to yard
Time 9270.018: Vessel 13 - Crane moved container 97
Time 9271.617: Vessel 14 - Container 96 loaded onto truck
Time 9273.018: Vessel 13 - Container 97 loaded onto truck
Time 9277.617: Vessel 14 - Truck transported container 96 to yard
Time 9277.617: Vessel 14 - Crane moved container 97
Time 9279.018: Vessel 13 - Truck transported container 97 to yard
Time 9279.018: Vessel 13 - Crane moved container 98
Time 9280.617: Vessel 14 - Container 97 loaded onto truck
Time 9282.018: Vessel 13 - Container 98 loaded onto truck
Time 9286.617: Vessel 14 - Truck transported container 97 to yard
Time 9286.617: Vessel 14 - Crane moved container 98
Time 9288.018: Vessel 13 - Truck transported container 98 to yard
Time 9288.018: Vessel 13 - Crane moved container 99
Time 9289.617: Vessel 14 - Container 98 loaded onto truck
Time 9291.018: Vessel 13 - Container 99 loaded onto truck
Time 9295.617: Vessel 14 - Truck transported container 98 to yard
Time 9295.617: Vessel 14 - Crane moved container 99
Time 9297.018: Vessel 13 - Truck transported container 99 to yard
Time 9297.018: Vessel 13 - Crane moved container 100
Time 9298.617: Vessel 14 - Container 99 loaded onto truck
Time 9300.018: Vessel 13 - Container 100 loaded onto truck
Time 9304.617: Vessel 14 - Truck transported container 99 to yard
Time 9304.617: Vessel 14 - Crane moved container 100
Time 9306.018: Vessel 13 - Truck transported container 100 to yard
Time 9306.018: Vessel 13 - Crane moved container 101
Time 9307.617: Vessel 14 - Container 100 loaded onto truck
Time 9309.018: Vessel 13 - Container 101 loaded onto truck
Time 9313.617: Vessel 14 - Truck transported container 100 to yard
Time 9313.617: Vessel 14 - Crane moved container 101
Time 9315.018: Vessel 13 - Truck transported container 101 to yard
Time 9315.018: Vessel 13 - Crane moved container 102
Time 9316.617: Vessel 14 - Container 101 loaded onto truck
Time 9318.018: Vessel 13 - Container 102 loaded onto truck
Time 9322.617: Vessel 14 - Truck transported container 101 to yard
Time 9322.617: Vessel 14 - Crane moved container 102
Time 9324.018: Vessel 13 - Truck transported container 102 to yard
Time 9324.018: Vessel 13 - Crane moved container 103
Time 9325.617: Vessel 14 - Container 102 loaded onto truck
Time 9327.018: Vessel 13 - Container 103 loaded onto truck
Time 9331.617: Vessel 14 - Truck transported container 102 to yard
Time 9331.617: Vessel 14 - Crane moved container 103
Time 9333.018: Vessel 13 - Truck transported container 103 to yard
Time 9333.018: Vessel 13 - Crane moved container 104
Time 9334.617: Vessel 14 - Container 103 loaded onto truck
Time 9336.018: Vessel 13 - Container 104 loaded onto truck
Time 9340.617: Vessel 14 - Truck transported container 103 to yard
Time 9340.617: Vessel 14 - Crane moved container 104
Time 9342.018: Vessel 13 - Truck transported container 104 to yard
Time 9342.018: Vessel 13 - Crane moved container 105
Time 9343.617: Vessel 14 - Container 104 loaded onto truck
Time 9345.018: Vessel 13 - Container 105 loaded onto truck
Time 9349.617: Vessel 14 - Truck transported container 104 to yard
Time 9349.617: Vessel 14 - Crane moved container 105
Time 9351.018: Vessel 13 - Truck transported container 105 to yard
Time 9351.018: Vessel 13 - Crane moved container 106
Time 9352.617: Vessel 14 - Container 105 loaded onto truck
Time 9354.018: Vessel 13 - Container 106 loaded onto truck
Time 9358.617: Vessel 14 - Truck transported container 105 to yard
Time 9358.617: Vessel 14 - Crane moved container 106
Time 9360.018: Vessel 13 - Truck transported container 106 to yard
Time 9360.018: Vessel 13 - Crane moved container 107
Time 9361.617: Vessel 14 - Container 106 loaded onto truck
Time 9363.018: Vessel 13 - Container 107 loaded onto truck
Time 9367.617: Vessel 14 - Truck transported container 106 to yard
Time 9367.617: Vessel 14 - Crane moved container 107
Time 9369.018: Vessel 13 - Truck transported container 107 to yard
Time 9369.018: Vessel 13 - Crane moved container 108
Time 9370.617: Vessel 14 - Container 107 loaded onto truck
Time 9372.018: Vessel 13 - Container 108 loaded onto truck
Time 9376.617: Vessel 14 - Truck transported container 107 to yard
Time 9376.617: Vessel 14 - Crane moved container 108
Time 9378.018: Vessel 13 - Truck transported container 108 to yard
Time 9378.018: Vessel 13 - Crane moved container 109
Time 9379.617: Vessel 14 - Container 108 loaded onto truck
Time 9381.018: Vessel 13 - Container 109 loaded onto truck
Time 9385.617: Vessel 14 - Truck transported container 108 to yard
Time 9385.617: Vessel 14 - Crane moved container 109
Time 9387.018: Vessel 13 - Truck transported container 109 to yard
Time 9387.018: Vessel 13 - Crane moved container 110
Time 9388.617: Vessel 14 - Container 109 loaded onto truck
Time 9390.018: Vessel 13 - Container 110 loaded onto truck
Time 9394.617: Vessel 14 - Truck transported container 109 to yard
Time 9394.617: Vessel 14 - Crane moved container 110
Time 9396.018: Vessel 13 - Truck transported container 110 to yard
Time 9396.018: Vessel 13 - Crane moved container 111
Time 9397.617: Vessel 14 - Container 110 loaded onto truck
Time 9399.018: Vessel 13 - Container 111 loaded onto truck
Time 9403.617: Vessel 14 - Truck transported container 110 to yard
Time 9403.617: Vessel 14 - Crane moved container 111
Time 9405.018: Vessel 13 - Truck transported container 111 to yard
Time 9405.018: Vessel 13 - Crane moved container 112
Time 9406.617: Vessel 14 - Container 111 loaded onto truck
Time 9408.018: Vessel 13 - Container 112 loaded onto truck
Time 9412.617: Vessel 14 - Truck transported container 111 to yard
Time 9412.617: Vessel 14 - Crane moved container 112
Time 9414.018: Vessel 13 - Truck transported container 112 to yard
Time 9414.018: Vessel 13 - Crane moved container 113
Time 9415.617: Vessel 14 - Container 112 loaded onto truck
Time 9417.018: Vessel 13 - Container 113 loaded onto truck
Time 9421.617: Vessel 14 - Truck transported container 112 to yard
Time 9421.617: Vessel 14 - Crane moved container 113
Time 9423.018: Vessel 13 - Truck transported container 113 to yard
Time 9423.018: Vessel 13 - Crane moved container 114
Time 9424.617: Vessel 14 - Container 113 loaded onto truck
Time 9426.018: Vessel 13 - Container 114 loaded onto truck
Time 9427.258: Vessel 36 Arrived
Time 9427.258: Vessel 36 Waiting for a berth
Time 9430.617: Vessel 14 - Truck transported container 113 to yard
Time 9430.617: Vessel 14 - Crane moved container 114
Time 9432.018: Vessel 13 - Truck transported container 114 to yard
Time 9432.018: Vessel 13 - Crane moved container 115
Time 9433.617: Vessel 14 - Container 114 loaded onto truck
Time 9435.018: Vessel 13 - Container 115 loaded onto truck
Time 9439.617: Vessel 14 - Truck transported container 114 to yard
Time 9439.617: Vessel 14 - Crane moved container 115
Time 9441.018: Vessel 13 - Truck transported container 115 to yard
Time 9441.018: Vessel 13 - Crane moved container 116
Time 9442.617: Vessel 14 - Container 115 loaded onto truck
Time 9444.018: Vessel 13 - Container 116 loaded onto truck
Time 9448.617: Vessel 14 - Truck transported container 115 to yard
Time 9448.617: Vessel 14 - Crane moved container 116
Time 9450.018: Vessel 13 - Truck transported container 116 to yard
Time 9450.018: Vessel 13 - Crane moved container 117
Time 9451.617: Vessel 14 - Container 116 loaded onto truck
Time 9453.018: Vessel 13 - Container 117 loaded onto truck
Time 9457.617: Vessel 14 - Truck transported container 116 to yard
Time 9457.617: Vessel 14 - Crane moved container 117
Time 9459.018: Vessel 13 - Truck transported container 117 to yard
Time 9459.018: Vessel 13 - Crane moved container 118
Time 9460.617: Vessel 14 - Container 117 loaded onto truck
Time 9462.018: Vessel 13 - Container 118 loaded onto truck
Time 9466.617: Vessel 14 - Truck transported container 117 to yard
Time 9466.617: Vessel 14 - Crane moved container 118
Time 9468.018: Vessel 13 - Truck transported container 118 to yard
Time 9468.018: Vessel 13 - Crane moved container 119
Time 9469.617: Vessel 14 - Container 118 loaded onto truck
Time 9471.018: Vessel 13 - Container 119 loaded onto truck
Time 9475.617: Vessel 14 - Truck transported container 118 to yard
Time 9475.617: Vessel 14 - Crane moved container 119
Time 9477.018: Vessel 13 - Truck transported container 119 to yard
Time 9477.018: Vessel 13 - Crane moved container 120
Time 9478.617: Vessel 14 - Container 119 loaded onto truck
Time 9480.018: Vessel 13 - Container 120 loaded onto truck
Time 9484.617: Vessel 14 - Truck transported container 119 to yard
Time 9484.617: Vessel 14 - Crane moved container 120
Time 9486.018: Vessel 13 - Truck transported container 120 to yard
Time 9486.018: Vessel 13 - Crane moved container 121
Time 9487.617: Vessel 14 - Container 120 loaded onto truck
Time 9489.018: Vessel 13 - Container 121 loaded onto truck
Time 9493.617: Vessel 14 - Truck transported container 120 to yard
Time 9493.617: Vessel 14 - Crane moved container 121
Time 9495.018: Vessel 13 - Truck transported container 121 to yard
Time 9495.018: Vessel 13 - Crane moved container 122
Time 9496.617: Vessel 14 - Container 121 loaded onto truck
Time 9498.018: Vessel 13 - Container 122 loaded onto truck
Time 9502.617: Vessel 14 - Truck transported container 121 to yard
Time 9502.617: Vessel 14 - Crane moved container 122
Time 9504.018: Vessel 13 - Truck transported container 122 to yard
Time 9504.018: Vessel 13 - Crane moved container 123
Time 9505.617: Vessel 14 - Container 122 loaded onto truck
Time 9507.018: Vessel 13 - Container 123 loaded onto truck
Time 9511.617: Vessel 14 - Truck transported container 122 to yard
Time 9511.617: Vessel 14 - Crane moved container 123
Time 9513.018: Vessel 13 - Truck transported container 123 to yard
Time 9513.018: Vessel 13 - Crane moved container 124
Time 9514.617: Vessel 14 - Container 123 loaded onto truck
Time 9516.018: Vessel 13 - Container 124 loaded onto truck
Time 9520.617: Vessel 14 - Truck transported container 123 to yard
Time 9520.617: Vessel 14 - Crane moved container 124
Time 9522.018: Vessel 13 - Truck transported container 124 to yard
Time 9522.018: Vessel 13 - Crane moved container 125
Time 9523.617: Vessel 14 - Container 124 loaded onto truck
Time 9525.018: Vessel 13 - Container 125 loaded onto truck
Time 9529.617: Vessel 14 - Truck transported container 124 to yard
Time 9529.617: Vessel 14 - Crane moved container 125
Time 9531.018: Vessel 13 - Truck transported container 125 to yard
Time 9531.018: Vessel 13 - Crane moved container 126
Time 9532.617: Vessel 14 - Container 125 loaded onto truck
Time 9534.018: Vessel 13 - Container 126 loaded onto truck
Time 9538.617: Vessel 14 - Truck transported container 125 to yard
Time 9538.617: Vessel 14 - Crane moved container 126
Time 9540.018: Vessel 13 - Truck transported container 126 to yard
Time 9540.018: Vessel 13 - Crane moved container 127
Time 9541.617: Vessel 14 - Container 126 loaded onto truck
Time 9543.018: Vessel 13 - Container 127 loaded onto truck
Time 9547.617: Vessel 14 - Truck transported container 126 to yard
Time 9547.617: Vessel 14 - Crane moved container 127
Time 9549.018: Vessel 13 - Truck transported container 127 to yard
Time 9549.018: Vessel 13 - Crane moved container 128
Time 9550.617: Vessel 14 - Container 127 loaded onto truck
Time 9552.018: Vessel 13 - Container 128 loaded onto truck
Time 9556.617: Vessel 14 - Truck transported container 127 to yard
Time 9556.617: Vessel 14 - Crane moved container 128
Time 9558.018: Vessel 13 - Truck transported container 128 to yard
Time 9558.018: Vessel 13 - Crane moved container 129
Time 9559.617: Vessel 14 - Container 128 loaded onto truck
Time 9561.018: Vessel 13 - Container 129 loaded onto truck
Time 9565.617: Vessel 14 - Truck transported container 128 to yard
Time 9565.617: Vessel 14 - Crane moved container 129
Time 9567.018: Vessel 13 - Truck transported container 129 to yard
Time 9567.018: Vessel 13 - Crane moved container 130
Time 9568.617: Vessel 14 - Container 129 loaded onto truck
Time 9570.018: Vessel 13 - Container 130 loaded onto truck
Time 9574.617: Vessel 14 - Truck transported container 129 to yard
Time 9574.617: Vessel 14 - Crane moved container 130
Time 9576.018: Vessel 13 - Truck transported container 130 to yard
Time 9576.018: Vessel 13 - Crane moved container 131
Time 9577.617: Vessel 14 - Container 130 loaded onto truck
Time 9579.018: Vessel 13 - Container 131 loaded onto truck
Time 9583.617: Vessel 14 - Truck transported container 130 to yard
Time 9583.617: Vessel 14 - Crane moved container 131
Time 9585.018: Vessel 13 - Truck transported container 131 to yard
Time 9585.018: Vessel 13 - Crane moved container 132
Time 9586.617: Vessel 14 - Container 131 loaded onto truck
Time 9588.018: Vessel 13 - Container 132 loaded onto truck
Time 9592.617: Vessel 14 - Truck transported container 131 to yard
Time 9592.617: Vessel 14 - Crane moved container 132
Time 9594.018: Vessel 13 - Truck transported container 132 to yard
Time 9594.018: Vessel 13 - Crane moved container 133
Time 9595.617: Vessel 14 - Container 132 loaded onto truck
Time 9597.018: Vessel 13 - Container 133 loaded onto truck
Time 9601.617: Vessel 14 - Truck transported container 132 to yard
Time 9601.617: Vessel 14 - Crane moved container 133
Time 9603.018: Vessel 13 - Truck transported container 133 to yard
Time 9603.018: Vessel 13 - Crane moved container 134
Time 9604.617: Vessel 14 - Container 133 loaded onto truck
Time 9606.018: Vessel 13 - Container 134 loaded onto truck
Time 9610.617: Vessel 14 - Truck transported container 133 to yard
Time 9610.617: Vessel 14 - Crane moved container 134
Time 9612.018: Vessel 13 - Truck transported container 134 to yard
Time 9612.018: Vessel 13 - Crane moved container 135
Time 9613.617: Vessel 14 - Container 134 loaded onto truck
Time 9615.018: Vessel 13 - Container 135 loaded onto truck
Time 9619.617: Vessel 14 - Truck transported container 134 to yard
Time 9619.617: Vessel 14 - Crane moved container 135
Time 9621.018: Vessel 13 - Truck transported container 135 to yard
Time 9621.018: Vessel 13 - Crane moved container 136
Time 9622.617: Vessel 14 - Container 135 loaded onto truck
Time 9624.018: Vessel 13 - Container 136 loaded onto truck
Time 9628.617: Vessel 14 - Truck transported container 135 to yard
Time 9628.617: Vessel 14 - Crane moved container 136
Time 9630.018: Vessel 13 - Truck transported container 136 to yard
Time 9630.018: Vessel 13 - Crane moved container 137
Time 9631.617: Vessel 14 - Container 136 loaded onto truck
Time 9633.018: Vessel 13 - Container 137 loaded onto truck
Time 9637.617: Vessel 14 - Truck transported container 136 to yard
Time 9637.617: Vessel 14 - Crane moved container 137
Time 9639.018: Vessel 13 - Truck transported container 137 to yard
Time 9639.018: Vessel 13 - Crane moved container 138
Time 9640.617: Vessel 14 - Container 137 loaded onto truck
Time 9642.018: Vessel 13 - Container 138 loaded onto truck
Time 9646.617: Vessel 14 - Truck transported container 137 to yard
Time 9646.617: Vessel 14 - Crane moved container 138
Time 9648.018: Vessel 13 - Truck transported container 138 to yard
Time 9648.018: Vessel 13 - Crane moved container 139
Time 9649.617: Vessel 14 - Container 138 loaded onto truck
Time 9651.018: Vessel 13 - Container 139 loaded onto truck
Time 9655.617: Vessel 14 - Truck transported container 138 to yard
Time 9655.617: Vessel 14 - Crane moved container 139
Time 9657.018: Vessel 13 - Truck transported container 139 to yard
Time 9657.018: Vessel 13 - Crane moved container 140
Time 9658.617: Vessel 14 - Container 139 loaded onto truck
Time 9660.018: Vessel 13 - Container 140 loaded onto truck
Time 9664.617: Vessel 14 - Truck transported container 139 to yard
Time 9664.617: Vessel 14 - Crane moved container 140
Time 9666.018: Vessel 13 - Truck transported container 140 to yard
Time 9666.018: Vessel 13 - Crane moved container 141
Time 9667.617: Vessel 14 - Container 140 loaded onto truck
Time 9669.018: Vessel 13 - Container 141 loaded onto truck
Time 9673.617: Vessel 14 - Truck transported container 140 to yard
Time 9673.617: Vessel 14 - Crane moved container 141
Time 9675.018: Vessel 13 - Truck transported container 141 to yard
Time 9675.018: Vessel 13 - Crane moved container 142
Time 9676.617: Vessel 14 - Container 141 loaded onto truck
Time 9678.018: Vessel 13 - Container 142 loaded onto truck
Time 9682.617: Vessel 14 - Truck transported container 141 to yard
Time 9682.617: Vessel 14 - Crane moved container 142
Time 9684.018: Vessel 13 - Truck transported container 142 to yard
Time 9684.018: Vessel 13 - Crane moved container 143
Time 9685.617: Vessel 14 - Container 142 loaded onto truck
Time 9687.018: Vessel 13 - Container 143 loaded onto truck
Time 9691.617: Vessel 14 - Truck transported container 142 to yard
Time 9691.617: Vessel 14 - Crane moved container 143
Time 9693.018: Vessel 13 - Truck transported container 143 to yard
Time 9693.018: Vessel 13 - Crane moved container 144
Time 9694.617: Vessel 14 - Container 143 loaded onto truck
Time 9696.018: Vessel 13 - Container 144 loaded onto truck
Time 9700.617: Vessel 14 - Truck transported container 143 to yard
Time 9700.617: Vessel 14 - Crane moved container 144
Time 9702.018: Vessel 13 - Truck transported container 144 to yard
Time 9702.018: Vessel 13 - Crane moved container 145
Time 9703.617: Vessel 14 - Container 144 loaded onto truck
Time 9705.018: Vessel 13 - Container 145 loaded onto truck
Time 9709.617: Vessel 14 - Truck transported container 144 to yard
Time 9709.617: Vessel 14 - Crane moved container 145
Time 9711.018: Vessel 13 - Truck transported container 145 to yard
Time 9711.018: Vessel 13 - Crane moved container 146
Time 9712.617: Vessel 14 - Container 145 loaded onto truck
Time 9714.018: Vessel 13 - Container 146 loaded onto truck
Time 9718.617: Vessel 14 - Truck transported container 145 to yard
Time 9718.617: Vessel 14 - Crane moved container 146
Time 9720.018: Vessel 13 - Truck transported container 146 to yard
Time 9720.018: Vessel 13 - Crane moved container 147
Time 9721.617: Vessel 14 - Container 146 loaded onto truck
Time 9723.018: Vessel 13 - Container 147 loaded onto truck
Time 9727.617: Vessel 14 - Truck transported container 146 to yard
Time 9727.617: Vessel 14 - Crane moved container 147
Time 9729.018: Vessel 13 - Truck transported container 147 to yard
Time 9729.018: Vessel 13 - Crane moved container 148
Time 9730.617: Vessel 14 - Container 147 loaded onto truck
Time 9732.018: Vessel 13 - Container 148 loaded onto truck
Time 9736.617: Vessel 14 - Truck transported container 147 to yard
Time 9736.617: Vessel 14 - Crane moved container 148
Time 9738.018: Vessel 13 - Truck transported container 148 to yard
Time 9738.018: Vessel 13 - Crane moved container 149
Time 9739.617: Vessel 14 - Container 148 loaded onto truck
Time 9741.018: Vessel 13 - Container 149 loaded onto truck
Time 9745.617: Vessel 14 - Truck transported container 148 to yard
Time 9745.617: Vessel 14 - Crane moved container 149
Time 9747.018: Vessel 13 - Truck transported container 149 to yard
Time 9747.018: Vessel 13 - Crane moved container 150
Time 9748.617: Vessel 14 - Container 149 loaded onto truck
Time 9750.018: Vessel 13 - Container 150 loaded onto truck
Time 9754.617: Vessel 14 - Truck transported container 149 to yard
Time 9754.617: Vessel 14 - Crane moved container 150
Time 9756.018: Vessel 13 - Truck transported container 150 to yard
Time 9756.018: Vessel 13 finished unloading and leaves
Time 9756.018: Vessel 15 berthed
Time 9756.018: Vessel 15 - Crane allocated
Time 9756.018: Vessel 15 - Crane moved container 1
Time 9757.617: Vessel 14 - Container 150 loaded onto truck
Time 9759.018: Vessel 15 - Container 1 loaded onto truck
Time 9763.617: Vessel 14 - Truck transported container 150 to yard
Time 9763.617: Vessel 14 finished unloading and leaves
Time 9763.617: Vessel 16 berthed
Time 9763.617: Vessel 16 - Crane allocated
Time 9763.617: Vessel 16 - Crane moved container 1
Time 9765.018: Vessel 15 - Truck transported container 1 to yard
Time 9765.018: Vessel 15 - Crane moved container 2
Time 9766.617: Vessel 16 - Container 1 loaded onto truck
Time 9768.018: Vessel 15 - Container 2 loaded onto truck
Time 9772.617: Vessel 16 - Truck transported container 1 to yard
Time 9772.617: Vessel 16 - Crane moved container 2
Time 9774.018: Vessel 15 - Truck transported container 2 to yard
Time 9774.018: Vessel 15 - Crane moved container 3
Time 9775.617: Vessel 16 - Container 2 loaded onto truck
Time 9777.018: Vessel 15 - Container 3 loaded onto truck
Time 9781.617: Vessel 16 - Truck transported container 2 to yard
Time 9781.617: Vessel 16 - Crane moved container 3
Time 9783.018: Vessel 15 - Truck transported container 3 to yard
Time 9783.018: Vessel 15 - Crane moved container 4
Time 9784.617: Vessel 16 - Container 3 loaded onto truck
Time 9786.018: Vessel 15 - Container 4 loaded onto truck
Time 9790.617: Vessel 16 - Truck transported container 3 to yard
Time 9790.617: Vessel 16 - Crane moved container 4
Time 9792.018: Vessel 15 - Truck transported container 4 to yard
Time 9792.018: Vessel 15 - Crane moved container 5
Time 9793.617: Vessel 16 - Container 4 loaded onto truck
Time 9795.018: Vessel 15 - Container 5 loaded onto truck
Time 9799.617: Vessel 16 - Truck transported container 4 to yard
Time 9799.617: Vessel 16 - Crane moved container 5
Time 9801.018: Vessel 15 - Truck transported container 5 to yard
Time 9801.018: Vessel 15 - Crane moved container 6
Time 9802.617: Vessel 16 - Container 5 loaded onto truck
Time 9804.018: Vessel 15 - Container 6 loaded onto truck
Time 9808.617: Vessel 16 - Truck transported container 5 to yard
Time 9808.617: Vessel 16 - Crane moved container 6
Time 9810.018: Vessel 15 - Truck transported container 6 to yard
Time 9810.018: Vessel 15 - Crane moved container 7
Time 9811.617: Vessel 16 - Container 6 loaded onto truck
Time 9813.018: Vessel 15 - Container 7 loaded onto truck
Time 9817.617: Vessel 16 - Truck transported container 6 to yard
Time 9817.617: Vessel 16 - Crane moved container 7
Time 9819.018: Vessel 15 - Truck transported container 7 to yard
Time 9819.018: Vessel 15 - Crane moved container 8
Time 9820.617: Vessel 16 - Container 7 loaded onto truck
Time 9822.018: Vessel 15 - Container 8 loaded onto truck
Time 9826.617: Vessel 16 - Truck transported container 7 to yard
Time 9826.617: Vessel 16 - Crane moved container 8
Time 9828.018: Vessel 15 - Truck transported container 8 to yard
Time 9828.018: Vessel 15 - Crane moved container 9
Time 9829.617: Vessel 16 - Container 8 loaded onto truck
Time 9831.018: Vessel 15 - Container 9 loaded onto truck
Time 9835.617: Vessel 16 - Truck transported container 8 to yard
Time 9835.617: Vessel 16 - Crane moved container 9
Time 9837.018: Vessel 15 - Truck transported container 9 to yard
Time 9837.018: Vessel 15 - Crane moved container 10
Time 9838.617: Vessel 16 - Container 9 loaded onto truck
Time 9840.018: Vessel 15 - Container 10 loaded onto truck
Time 9844.617: Vessel 16 - Truck transported container 9 to yard
Time 9844.617: Vessel 16 - Crane moved container 10
Time 9846.018: Vessel 15 - Truck transported container 10 to yard
Time 9846.018: Vessel 15 - Crane moved container 11
Time 9847.617: Vessel 16 - Container 10 loaded onto truck
Time 9849.018: Vessel 15 - Container 11 loaded onto truck
Time 9853.617: Vessel 16 - Truck transported container 10 to yard
Time 9853.617: Vessel 16 - Crane moved container 11
Time 9855.018: Vessel 15 - Truck transported container 11 to yard
Time 9855.018: Vessel 15 - Crane moved container 12
Time 9856.617: Vessel 16 - Container 11 loaded onto truck
Time 9858.018: Vessel 15 - Container 12 loaded onto truck
Time 9862.617: Vessel 16 - Truck transported container 11 to yard
Time 9862.617: Vessel 16 - Crane moved container 12
Time 9864.018: Vessel 15 - Truck transported container 12 to yard
Time 9864.018: Vessel 15 - Crane moved container 13
Time 9865.617: Vessel 16 - Container 12 loaded onto truck
Time 9867.018: Vessel 15 - Container 13 loaded onto truck
Time 9871.617: Vessel 16 - Truck transported container 12 to yard
Time 9871.617: Vessel 16 - Crane moved container 13
Time 9873.018: Vessel 15 - Truck transported container 13 to yard
Time 9873.018: Vessel 15 - Crane moved container 14
Time 9874.617: Vessel 16 - Container 13 loaded onto truck
Time 9876.018: Vessel 15 - Container 14 loaded onto truck
Time 9880.617: Vessel 16 - Truck transported container 13 to yard
Time 9880.617: Vessel 16 - Crane moved container 14
Time 9882.018: Vessel 15 - Truck transported container 14 to yard
Time 9882.018: Vessel 15 - Crane moved container 15
Time 9883.617: Vessel 16 - Container 14 loaded onto truck
Time 9885.018: Vessel 15 - Container 15 loaded onto truck
Time 9889.617: Vessel 16 - Truck transported container 14 to yard
Time 9889.617: Vessel 16 - Crane moved container 15
Time 9891.018: Vessel 15 - Truck transported container 15 to yard
Time 9891.018: Vessel 15 - Crane moved container 16
Time 9892.617: Vessel 16 - Container 15 loaded onto truck
Time 9894.018: Vessel 15 - Container 16 loaded onto truck
Time 9898.617: Vessel 16 - Truck transported container 15 to yard
Time 9898.617: Vessel 16 - Crane moved container 16
Time 9900.018: Vessel 15 - Truck transported container 16 to yard
Time 9900.018: Vessel 15 - Crane moved container 17
Time 9901.617: Vessel 16 - Container 16 loaded onto truck
Time 9903.018: Vessel 15 - Container 17 loaded onto truck
Time 9907.617: Vessel 16 - Truck transported container 16 to yard
Time 9907.617: Vessel 16 - Crane moved container 17
Time 9909.018: Vessel 15 - Truck transported container 17 to yard
Time 9909.018: Vessel 15 - Crane moved container 18
Time 9910.617: Vessel 16 - Container 17 loaded onto truck
Time 9912.018: Vessel 15 - Container 18 loaded onto truck
Time 9916.617: Vessel 16 - Truck transported container 17 to yard
Time 9916.617: Vessel 16 - Crane moved container 18
Time 9918.018: Vessel 15 - Truck transported container 18 to yard
Time 9918.018: Vessel 15 - Crane moved container 19
Time 9919.617: Vessel 16 - Container 18 loaded onto truck
Time 9921.018: Vessel 15 - Container 19 loaded onto truck
Time 9925.617: Vessel 16 - Truck transported container 18 to yard
Time 9925.617: Vessel 16 - Crane moved container 19
Time 9927.018: Vessel 15 - Truck transported container 19 to yard
Time 9927.018: Vessel 15 - Crane moved container 20
Time 9928.617: Vessel 16 - Container 19 loaded onto truck
Time 9930.018: Vessel 15 - Container 20 loaded onto truck
Time 9934.617: Vessel 16 - Truck transported container 19 to yard
Time 9934.617: Vessel 16 - Crane moved container 20
Time 9936.018: Vessel 15 - Truck transported container 20 to yard
Time 9936.018: Vessel 15 - Crane moved container 21
Time 9937.617: Vessel 16 - Container 20 loaded onto truck
Time 9939.018: Vessel 15 - Container 21 loaded onto truck
Time 9943.617: Vessel 16 - Truck transported container 20 to yard
Time 9943.617: Vessel 16 - Crane moved container 21
Time 9945.018: Vessel 15 - Truck transported container 21 to yard
Time 9945.018: Vessel 15 - Crane moved container 22
Time 9946.617: Vessel 16 - Container 21 loaded onto truck
Time 9948.018: Vessel 15 - Container 22 loaded onto truck
Time 9952.617: Vessel 16 - Truck transported container 21 to yard
Time 9952.617: Vessel 16 - Crane moved container 22
Time 9954.018: Vessel 15 - Truck transported container 22 to yard
Time 9954.018: Vessel 15 - Crane moved container 23
Time 9955.617: Vessel 16 - Container 22 loaded onto truck
Time 9957.018: Vessel 15 - Container 23 loaded onto truck
Time 9957.796: Vessel 37 Arrived
Time 9957.796: Vessel 37 Waiting for a berth
Time 9961.617: Vessel 16 - Truck transported container 22 to yard
Time 9961.617: Vessel 16 - Crane moved container 23
Time 9963.018: Vessel 15 - Truck transported container 23 to yard
Time 9963.018: Vessel 15 - Crane moved container 24
Time 9964.617: Vessel 16 - Container 23 loaded onto truck
Time 9966.018: Vessel 15 - Container 24 loaded onto truck
Time 9970.617: Vessel 16 - Truck transported container 23 to yard
Time 9970.617: Vessel 16 - Crane moved container 24
Time 9972.018: Vessel 15 - Truck transported container 24 to yard
Time 9972.018: Vessel 15 - Crane moved container 25
Time 9973.617: Vessel 16 - Container 24 loaded onto truck
Time 9975.018: Vessel 15 - Container 25 loaded onto truck
Time 9979.617: Vessel 16 - Truck transported container 24 to yard
Time 9979.617: Vessel 16 - Crane moved container 25
Time 9981.018: Vessel 15 - Truck transported container 25 to yard
Time 9981.018: Vessel 15 - Crane moved container 26
Time 9982.617: Vessel 16 - Container 25 loaded onto truck
Time 9984.018: Vessel 15 - Container 26 loaded onto truck
Time 9988.617: Vessel 16 - Truck transported container 25 to yard
Time 9988.617: Vessel 16 - Crane moved container 26
Time 9990.018: Vessel 15 - Truck transported container 26 to yard
Time 9990.018: Vessel 15 - Crane moved container 27
Time 9991.617: Vessel 16 - Container 26 loaded onto truck
Time 9993.018: Vessel 15 - Container 27 loaded onto truck
Time 9997.617: Vessel 16 - Truck transported container 26 to yard
Time 9997.617: Vessel 16 - Crane moved container 27
Time 9999.018: Vessel 15 - Truck transported container 27 to yard
Time 9999.018: Vessel 15 - Crane moved container 28
```
