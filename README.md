# NNP-CuZrO
An implementation of neural network potentials (NNPs) capable of simulating the mechanical/physical behavior of oxidized CuZr (e.g., CuZr(O)) metallic glasses.
## How to use
The NNP files for Cu-Zr-O tenary are available here. They can be loaded in Atomic Simulation Environment (ASE) (https://wiki.fysik.dtu.dk/ase/) linked with the aenet packages (https://github.com/atomisticnet/aenet/). 
```
from ase.io import read
from aenet.calculator import ANNCalculator

a = read("*")
c = {"Cu" : "path-to-Cu.nn",
     "Zr" : "path-to-Zr.nn",
     "O"  : "path-to-O.nn"}
a.calc = ANNCalculator(c)
```
Noted that too many O-O bonds in initial configurations may run out of control due to the high vibrational frequency of oxygen atoms. A long time step may be helpful but not necessary, considering the reliability and stability of simulations. To this end, it is recommended to generate a high-quality initial configuration with more intersititial oxygen atoms and relax the structure afterwards. 
## Reporting errors
If you spot an error in these program files, or the accompanying documentation, please raise an "issue" using the Issues tab. (You will need to be logged in to GitHub to do this). 
