import simpy
import random
import time

# Set a random seed for reproducibility
random_seed = 42
random.seed(random_seed)
 
class Container_Terminal:
    def __init__(self, env, num_berths, num_cranes, num_trucks):
        self.env = env
        self.berths = simpy.Resource(env, num_berths)
        self.cranes = simpy.Resource(env, num_cranes)
        self.trucks = simpy.Resource(env, num_trucks)

    def discharge_containers(self, vessel_id, num_containers):
        crane_request=self.cranes.request()# Request a crane for discharging containers
        yield crane_request
        
        print(f"Time {self.env.now:.3f}: Vessel {vessel_id} - Crane allocated")

        for i in range(num_containers):
            print(f"Time {self.env.now:.3f}: Vessel {vessel_id} - Crane moved container {i + 1}")
            yield self.env.process(self.move_container(vessel_id, i + 1))
            
        self.cranes.release(crane_request)# Release the crane after all containers are moved

    def move_container(self, vessel_id, container_id):
        truck_request = self.trucks.request()# Request a truck for moving the container

        if not truck_request.triggered:
            print(f"Time {self.env.now:.3f}: Vessel {vessel_id} - Crane waiting for a truck")
        # Wait for a truck to become available
        yield truck_request

        # Simulate time to move the container to the truck
        yield self.env.timeout(3)
        print(f"Time {self.env.now:.3f}: Vessel {vessel_id} - Container {container_id} loaded onto truck")
        
        # Simulate Transporting the container
        yield self.env.process(self.transport_container(vessel_id, container_id))

        # Release the truck after transportation
        self.trucks.release(truck_request)

    def transport_container(self, vessel_id, container_id):
        # Simulate time for the truck to drop off the container and return
        yield self.env.timeout(6)  
        print(f"Time {self.env.now:.3f}: Vessel {vessel_id} - Truck transported container {container_id} to yard")

def handle_vessel(env, vessel_id, terminal):
    print(f"Time {env.now:.3f}: Vessel {vessel_id} arrived")
    # Request a berth for the vessel
    berth_request = terminal.berths.request()
    if not berth_request.triggered:
        print(f"Time {env.now:.3f}: Vessel {vessel_id} waiting for a berth")

    # Wait for a berth to become available
    yield berth_request

    print(f"Time {env.now:.3f}: Vessel {vessel_id} berthed")
    
    # Start discharging containers
    yield env.process(terminal.discharge_containers(vessel_id, 100))
    print(f"Time {env.now:.3f}: Vessel {vessel_id} finished unloading and leaves")

    # Release the berth after unloading
    terminal.berths.release(berth_request)

def generate_vessel_arrivals(env, terminal):
    vessel_id = 0
    while True:
        # Simulate time between vessel arrivals (average 5 hours)
        yield env.timeout(random.expovariate(1 / 300))   
        vessel_id += 1
        env.process(handle_vessel(env, vessel_id, terminal))


def get_simulation_parameters():
    print("Select the choices:")
    print("1. Use default values")
    print("2. Enter user-defined values")
    try:
        choice = int(input("Enter your choice (1 or 2): "))
    except ValueError:
        print("Invalid input. Please enter a number (1 or 2).")
        return get_simulation_parameters()  # Recursively call the function for a valid choice
    
    if choice == 2:
        try:
            num_berths = int(input("Enter the number of berths: "))
            num_cranes = int(input("Enter the number of cranes: "))
            num_trucks = int(input("Enter the number of trucks: "))
            simulation_time = int(input("Enter the total simulation time in minutes: "))
        except ValueError:
            print("Invalid input. Please enter integer values for all parameters.")
            return get_simulation_parameters()  # Recursively call the function for valid inputs
    else:
        print("You have chosen to use default values.")
        num_berths = 2
        num_cranes = 2
        num_trucks = 3
        simulation_time = 5000

    return num_berths, num_cranes, num_trucks, simulation_time

def main():
    # Get user input for simulation parameters
    num_berths, num_cranes, num_trucks, simulation_time = get_simulation_parameters()
    ## Print simulation parameters for verification
    print("Simulation parameters:")
    print(f"Number of berths: {num_berths}")
    print(f"Number of cranes: {num_cranes}")
    print(f"Number of trucks: {num_trucks}")
    print(f"Total simulation time: {simulation_time} minutes")
    
    time.sleep(1)  # Pauses the execution for 1 seconds

    # Initialize the simulation environment
    env = simpy.Environment()

    # Create the container terminal with user inputs
    terminal = Container_Terminal(env, num_berths, num_cranes, num_trucks)

    # Start the vessel arrival process
    env.process(generate_vessel_arrivals(env, terminal))

    # Run the simulation
    env.run(until=simulation_time)

if __name__ == "__main__":
    main()
