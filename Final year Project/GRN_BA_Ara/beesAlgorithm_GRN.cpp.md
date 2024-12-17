This class stores the parameters and methods defining the class and contains the colony of agents (class bee) as well as the main parameters defining the GRN.

``` C++

class BeesAlgorithm_GRN // the population size is nc = ns + nb * (nb - ne) + ne * nre
{
private:
	int solutCounter; // counter for the number of good solutions (fitness < 0) produced
	Bee** colony; // Array where the population (scouts) is stored
	double bestFitness; // fitness of the best-so-far solution in the whole search
	FitnessFunction* fitnessFixedPoints; // Fitness function used for solutions sufficiently similar to target GRN
	string saveFiles; // path + name root of files where results are saved by 'saveSolution' function
	int T; // number of iterations of the main cycle
	int ns; // number of scout bees
	int nb; // number of best sites
	int ne; // number of elite sites
	int nrb; // recruited bees for best sties
	int nre; // recruited bees for elite sites
	int nghShr; // flag indicating whether neighbourhood is used, or neighbourhood size is shrinking if not used
	int initNgh; // initial size of neighbourhood if used, or neighbhourhood size if shrinking is not used
	int minNgh; // min size of neighbourhood
	int stlim; // limit of stagnation cycles for site abandonment]
	int sites; // number of parallel local + global searches (ns + nb)
	double searchThreshold; // fitness threshold for switching search from 'target' to 'attractors'
	double saveThreshold; // fitness threshold for saving abandoned solution
	bool synchMode; // synchronous update mode (true or false)
	lSearch searchType; // type of ocal search: delta = + or - 1, reinit = random reinitialisation of adj matrix/ thr vector element
	int getT(); // Returns number of iterations T of the main BA loop
	int getNs(); // Returns the number of scouts (ns)
	int getNb(); // Return number of best sites (nb)
	int getNe(); // Return the number of elite sites (ne)
	int getNrb(); // Returns number of foragers per best site (nrb)
	int getNre(); // Returns the number of foragers per elite site (nre)
	bool getNghShr(); // Returns the flag indicating whether neighbourhood shrinking is used
	int getInitNgh(); // Returns initial neighbourhood size initNgh, that is the number of connections weights that local search modifies. If neighbourhood shrinking is not used, the returned value is the constant neighbourhood used throughout the search
	int getMinNgh(); // Returns the minimum neighbourhood size minNgh, that is the minimum number of connection weights that local search modifies
	int getStlim(); // Returns the stagnation limit stlim for the site abondonment procedure
	int getSites(); // Returns the number of BA sites concurrently searched (nb + ns)
	bool getSynchMode(); // Returns whether the update mode is synchronous
	double getSearchThreshold(); // Returns the fitness threshold for switching search
	double getSaveThreshold(); // Returns the fitness threshold to save an abandoned solution
	lSearch getSearchType();  // Returns local search performed (delta or reinit)
	void setColonyMember(int nr, Bee* member); // Sets element 'nr' of the array of pointers to colony members (scout bees) to a new bee, can be used to reshuffle/sort the order of the elements in the array or to substitute one of the scouts to avoid memory leaks make sure old memeber is destroyed
	Bee* getColonyMember(int nr); // Returns a pointer to a colony member (scoutr bee)
	FitnessFunction* getAttractFunction(); // Returns the attractor fitness function
	int getSolutCounter(); // Returns number of good (fitness < 0) solutions found
	void resetSolutCounter(); // Resets number of good solutions found
	void incrementSolutCounter(); // Increments number of good solutions found
	void popDestructor(); // Deletes the population
	void fFunctDestructor(); // Deletes the objective function
	void abandon(Bee* solution); // Simply abandons and reinitialises a given bee
	void saveSolution(Bee* solution);
	void beesRanking(); // Ranks the scouts in increasing order of fitness
	void waggleDance(); // Implements the waggle dance routine. Elite and best sites are allocated nre and nrb foragers respectively
	void localSearch(); // Implements local search and neighbourhood shrinking routines. nre and nrb foragers are generated for the ne elite and nb-ne best sites respectively. ngh elements picked from adjacency matrix and threshold vector are randomly reinitialised. if one of the foragers is fitter than the scout, it replaces the scout, if none of the foragers is fitter, the neighbourhood size is reduced by one
	Bee* deltaSearch(Bee* scout); // Implements local search and neighbourhood shrinking routines. nre and nrb foragers are generated for the ne elite and nb-ne best sites respectively. ngh elements picked from the adj matrix and thr vector are randomly reinitialised. if one of the foragers is fitter, it replaces the scout else if none are then the neighbourhood size is reduced by 1
	Bee* reinitSearch(Bee* scout); // Implements the local search and neighbourhood shrinking routines. nre and nrb foragers are generated for the ne elite and nb-ne best sites respectively. ngh elements picked from the adjacency matrix and threshold vector are randomly reinitialised. if one of the foragers is fitter than the scout, it replaces the scout. if none, the neighbourhood size is reduced by one
	void gSearch(); // implements global search routine. 'ns' scouts who haven't been selected for local search are randomly reinitialised, and their new fitness is evaluated. ttl is set equal to maximum 'stlim' and their neighbourhood to the initial value 'initNgh'
	void siteAbandonment(); // Implements site abandonment procedure. all 'nrb' scouts who were selected for local search, and whose time-to-live ttl is equal to zero, are randomly reinitialised. new fitness is evaluated, their ttl is set equal to maximum 'stlim', and their neighbourhood to initial value 'initNgh'
	void setBestFitness(double newBest); // Stores a copy of the bee who found the current best solution
	double getBestFitness(); // Returns the bee who found the current best solution
	void monitorProgress(ofstream& outFile, int iteration); // Saves in outfile the current iteration, the current best fitness, and best-so-far-fitness. function assumes the scouts have been sorted in ascending order of error
	void saveSolution(Bee* solution, ofstream& outFile); // Saves a solution to a progressively numbered file
	string getSaveFiles(); // Reads the files of best solutions, displays their fitness along with main features
public:
	BeesAlgorithm_GRN(string filename); // reads and stores the GRN parameters and how Bees Algorithm hyperparameters then initialises the bee colony
	~BeesAlgorithm_GRN(void); // Creates an objective function which will evaluate the fitness of the solutions based on the type of fitness criterion used: either how well it replicates a target GRN, or by the number of states ending in one of the four fixed points associated to A. Thaliana flower tissue
	void beesAlgInitialisation(string fileBAPars, string fileGRNPars);
	void setObjFunction(string seqFile); // Evaluates the fitness of solutions based on type of fitness criterion userd: either how well it replicates a target GRN, or by number of states ending in one of the four fixed points associated to A. thaliana flower tissue
	void beesAlgorithm(); // Implements the bees algorithm
	void displayResults(); // Reads the files of best solutions, and displays their fitness along with main features
	void setSolutCounter(int solutions) // Sets number of good solutions found
	
}
```