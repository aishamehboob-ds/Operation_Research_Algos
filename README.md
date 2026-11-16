Operations Research Builds

Sixteen optimization models, built from scratch, one a week. The set covers the main families of operations research: linear and integer programming, network design, scheduling, routing, heuristics, inventory under uncertainty, stochastic programming, dynamic programming and decomposition.

Every project follows the same four steps:

Formulate the problem on paper from a one-line prompt.
Build the model in Python and solve it.
Break it with a targeted experiment, to see where the model stops working.
Explain it in five sentences: the decision, the trade-off, the answer, what would change it, and what comes next.

Each folder holds a notebook with the problem statement, formulation, code, results and chart, the break-it experiment and the explanation. All data is made up.

Tools: Python, PuLP, Pyomo, HiGHS, OR-Tools (CP-SAT and routing), NumPy, pandas, Matplotlib.

The 16 projects
Phase 1: Core models
Week	Project	Model	Concepts covered	Break-it experiment	Used for	Done
1	Supply-Demand Matching Engine	Transportation LP and driver-rider assignment	Linear programming, decision variables, objective, constraints, feasible region, duality, shadow prices, slack, sensitivity analysis, assignment problem, total unimodularity	Cut a capacity and predict the cost change from the shadow price	Shipping plans, ride and order matching	⬜
2	Six-Month Production Planner	Multi-period production and supply plan	Multi-period LP, inventory balance constraints, time indexing, holding cost, backorders, infeasibility diagnosis, soft constraints with penalties	Make it infeasible, then fix it with backorders	Production and supply planning	⬜
3	Warehouse Location Picker	Facility location MIP	Mixed-integer programming, binary variables, fixed-charge costs, big-M linking, LP relaxation, optimality gap, branch and bound, bounds	Use a huge big-M and watch the gap worsen	Distribution network design	⬜
4	Product Sourcing Optimizer	SKU sourcing network	Multi-commodity network flow, min-cost flow, capacity constraints, minimum lot sizes, single-sourcing rules, formulation strength, scenario comparison	Model it two ways and compare solve times	Multi-plant product sourcing	⬜
5	Production Batch Scheduler	Lot sizing with setup costs	Setup variables, capacitated lot sizing, tight vs weak formulations, valid inequalities, reading a solver log, cuts, presolve, time limits	Scale until slow, then tighten	Manufacturing run planning	⬜
Phase 2: Fulfilment, scheduling and routing
Week	Project	Model	Concepts covered	Break-it experiment	Used for	Done
6	Stock Placement and Order Router	Inventory placement and order fulfilment	Inventory placement, order sourcing, split shipments, service-time constraints, cost vs speed trade-off, penalty terms, multi-objective weighting	Add a split-shipment penalty and see the plan change	E-commerce fulfilment	⬜
7	Factory Job Scheduler	Shift or job-shop scheduling in CP-SAT	Constraint programming, interval variables, no-overlap and precedence constraints, makespan, CP-SAT vs MIP, disjunctive constraints, search and propagation	Solve it as a MIP too and compare	Factory and workforce scheduling	⬜
8	Delivery Route Planner	Vehicle routing with time windows	Vehicle routing, capacity and time-window constraints, subtour elimination, construction heuristics, local search, metaheuristics, time limit vs solution quality	Double the customers under a fixed time limit	Last-mile delivery	⬜
9	Solver-Free Heuristic Solver	Your own heuristic	Greedy construction, neighbourhoods, swap and 2-opt moves, local optima, simulated annealing or ALNS, benchmarking, gap to the optimal answer	Compare against exact answers on small cases	Large problems where exact solvers are too slow	⬜
Phase 3: Uncertainty and pricing
Week	Project	Model	Concepts covered	Break-it experiment	Used for	Done
10	Store Reorder Policy Simulator	Single-location inventory under uncertainty	Newsvendor, critical ratio, service level vs fill rate, safety stock, reorder point, (s, S) and (R, Q) policies, lead-time demand, Monte Carlo simulation	Change the demand distribution until the policy fails	Store replenishment	⬜
11	Safety Stock Network Designer	Multi-echelon inventory design	Multi-echelon inventory, risk pooling, guaranteed service model, service times between stages, base-stock policies, upstream vs downstream stock, simulation validation	Raise the plant lead time or one store's variability and see where stock moves	Supply chain inventory design	⬜
12	Dynamic Pricing Engine	Pricing: markdown and surge	Price elasticity, demand curves, revenue maximisation, nonlinear objectives, piecewise linearization, markdown schedules, surge multipliers, model misspecification	Use a wrong elasticity and measure the lost revenue	Retail markdowns, ride pricing	⬜
13	Capacity Reservation Planner	Capacity planning under demand uncertainty	Two-stage stochastic programming, scenarios, first-stage vs recourse decisions, sample average approximation, value of the stochastic solution, robust optimisation	Compute the value of planning for uncertainty vs the average case	Supplier and capacity contracts	⬜
Phase 4: Advanced and capstone
Week	Project	Model	Concepts covered	Break-it experiment	Used for	Done
14	Real-Time Dispatch Engine	Decisions over time	Dynamic programming, states and actions, Bellman equation, value function, Markov decision processes, rolling horizon, batching and matching, look-ahead	Shorten the look-ahead window and measure the loss	Ride dispatch and repositioning	⬜
15	Roll Cutting Optimizer	Column generation	Column generation, restricted master problem, pricing subproblem, reduced cost, using duals, Dantzig-Wolfe idea, cutting stock, set covering	Compare with the full model on a small case	Paper, steel and film cutting; crew patterns	⬜
16	Forecast-to-Decision Pipeline	Capstone: predict, then optimize	Predict-then-optimise, forecast error propagation, simulation as validation, decision-focused evaluation, switchback experiment design, decision memo	Write the one-page decision memo	End-to-end decision systems	⬜

When a project is finished, its name becomes a link to its folder and ⬜ becomes ✅.

Repo layout
weekNN_project_name/: one notebook, a short README with the prompt and result, and a results/ folder for charts.
template/: the blank notebook each week starts from.
common/: helper code reused across weeks.
Setup

Google Colab: open a notebook and run the first cell, which installs the packages.

VS Code:

python -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate
pip install -r requirements.txt


