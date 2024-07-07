Problem Statement

The primary objective is to optimize route assignments for orders within a supply chain logistics network. The aim is to minimize freight and warehousing costs while adhering to constraints such as supply capacities, demand requirements, and specific operational rules. The problem involves determining the optimal routes from plants to a designated port for different products, given historical data on past assignments.

About the Dataset

The dataset consists of seven preprocessed CSV files, each containing specific information relevant to the supply chain logistics problem:

OrderList: Contains order details including origin port, carrier, transport time, service level, ship ahead/late day counts, customer, product ID, plant code, destination port, unit quantity, and weight.

FreightRates: Provides information on freight rates including carrier, origin and destination ports, weight range, service code, minimum cost, rate, transport days, and carrier type.

WhCosts: Lists warehousing costs per unit for different warehouses/plants.

WhCapacities: Contains daily capacity information for different plants.

ProductsPerPlant: Indicates which products can be handled by which plants.

VmiCustomers: Specifies customers that can only be serviced by specific plants.

PlantPorts: Describes the physical connections between plants and ports.

Approach

Data Preprocessing:

Merge relevant tables to create a comprehensive dataset for analysis.
Ensure that all constraints and operational rules are represented in the merged dataset.

Optimization Model Formulation:

Define decision variables representing the quantity of each product assigned to each route from each plant.
Construct the objective function to minimize the total cost, including freight and warehousing costs.
Add constraints to ensure that supply capacities are not exceeded and demand requirements are met.
Include additional constraints to comply with operational rules (e.g., specific customers served by specific plants).

Solving the Model:

Use Linear Programming (LP) to find the optimal solution for the formulated problem.
Utilize a solver like PuLP to handle the LP model and obtain the optimal route assignments.

Evaluation:

Validate the solution to ensure it meets all constraints.
Analyze the results to understand the cost implications and feasibility of the route assignments.

Model Analysis

Objective Function:

The objective function aims to minimize the total cost associated with routing products from plants to the designated port.
Costs are calculated based on fixed freight rates and warehousing costs for each route.

Constraints:

Supply Constraints: Ensure that the total quantity of products assigned from each plant does not exceed the plant's daily capacity.
Demand Constraints: Ensure that the total quantity of each product delivered meets or exceeds the demand requirements.
Operational Constraints: Ensure compliance with specific business rules, such as servicing certain customers only from specific plants.

Results:

The solution provides the optimal quantity of each product to be shipped from each plant to the port via each route.
The total cost associated with the optimal solution is computed and serves as the primary metric for evaluation.

Validation:

The results are checked against the original constraints to ensure feasibility.
Any deviations or infeasibilities are analyzed to refine the model or adjust constraints accordingly.

Conclusion

The dataset and problem at hand are best suited for a Linear Programming (LP) optimization model due to the need for balancing multiple constraints and minimizing costs. Predictive models like regression or classification are not appropriate in this context because the problem is deterministic and requires finding an optimal solution under specific operational rules and constraints. The LP model provides a structured approach to determine the most cost-effective route assignments while ensuring all business requirements are met.
