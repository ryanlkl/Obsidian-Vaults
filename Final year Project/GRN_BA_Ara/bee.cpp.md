# Class
The class is initialised for both the bees and algorithm as well as the gene regulatory network. The structure of the file is defined in **bee.h**
 ``` C++
 class Bee
 {
 private: // Not accessible or viewable from outside the class
	// GRN
	int nodes; // Nodes of the Network
	int edges; // Edges in the Network
	int extremes[2]; // lower and upper extreme of the edge weights and node activation threshold interval

	// Bees Algorithm
	int ttl; // Bees time-to-live
	int nghSize; // The neighbourhood size
	int recruited; // number of recruited foragers
	// ** means the value is pointed to by a pointer which is pointed to by adjMatrix (declares a pointer to a pointer to an integer)
	int** adjMatrix; // The adjacency matrix of the Network
	// * means the value is pointed to by thrVector (declares a pointer to an integer)
	int* thrVector; // Vector of thresholds for activation of network nodes
	double fitness; // fitness of the visited solution

	// void means the function doesn't return anything
	void initialiseGRN(); // Creates and initialises the adjacency matrix and threshold vector where all initial values are 0
	void randomSeedGRN(); // randomly initialises the GRN matrix and threshold vector
	void readTarget(string fileTarget); // Reads a target GRN's adjacency matrix and threshold vector from the file. the target can be used in the fitness evaluation function or to seed the population

public: // Can be accessed and modified from outside of the code
	Bee(int numberOfNodes, int lowerExtreme, int upperExtreme, int stlim, int ngh);
	Bee(int numberOfNodes, int lowerExtreme, int upperExtreme, string targetGRM); // This constructor is only to create a target GRN fo fitness evaluation function
	~Bee();
	void setTtle(int remaining); // Sets the time-to-live of the bee i.e. number of cycles of stagnation left before site abondonment
	void decreaseTtl(); // Decreases time-to-live of bee by 1 cycle
	void setNghSize(int size); // Sets the size of the bee neighbourhood, that is the maximum number of edges that local search will change
	void decreaseNghSize(); // Decreases size of bee neighbourhood by 1
	void setRecruited(int foragers); // Sets the number of forages recruited by the bee
	void reinitAdjMatrix(); // Reinitialises the values of the adjacency matrix elements to random values
	void reinitThrVector(); // Reinitialises the values of the threhold vector elements to random values
	void setFitness(double evaluation); // Sets the fitness of a solution evaluated by a bee (inputs the fitness of the bee)
	void setAdjMatrixElement(int row, int column, int value); // Modifies the value of an element in an adjacency matrix
	void setThrVectorElement(int element, int value); // Modifies the value of an alement of the threshold vector
	int getTtl(); // Retrieves the time-to-live of the bee
	int getNghSize(); // Returns the size of the bee neighbourhood (maximum number of edges that local search will change)
	int getRecruited(); // Returns the number of foragers recruited by the bee
	int getNumberOfNodes(); // Returns number of vertices of the network
	int getLowerExtreme(); // Returns the lowest possible value of edge weights and node activation threshold interval
	int getUpperExtreme(); // Returns the upper extreme of edge weights and node activation threshold interval
	int getAdjMatrixElement(int row, int column); // Returns value of an element of the adjacency matrix
	int getThrVectorElement(int element); // Returns value of an element of the threshold vector
	void countEdges(); // Counts the number of edges in the network (non-zero elements of adjacency matrix and threshold vector)
	void incrementEdges(); // Increments number of edges in network
	void decrementEdges(); // Decrements number of edges in network
	int getEdges(); // Returns the number of edges in the network (non-zero elements of adjacency matrix and threshold vector)
	double getFitness(); // Retrieves the fitness of the bee
	void synchNextState(bool* currentState, bool* nextState); // Updates the configuration of GRN according to eq. (1) in DOI: 10.1109/CEC.2018.8477964 (all nodes updated synchronously)
	void aSynchNextState(bool* currentState, bool* nextState); // Updates configuration of GRN according to eq.(1) in DOI: 10.1109/CEC.2018.8477964 (updated synchronously), customised for arabidopsis thaliana GRN in DOI: 10.1109/CEC.2018.8477964
	Bee* createCopy(); // Creates an exact copy of the bee
	void evaluateGRN(); // Evaluates goodness of a solution. Fitness is measured based on how well the candidate solution matches the target sequence. Measured fitness is set as solution's new fitness
	
 }
```