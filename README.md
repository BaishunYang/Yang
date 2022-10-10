# Yang
The codes used to deal with the magnetic interactions between bilayer magnets and twisted bilayer magnets. This script takes twisted bilayer CrI3 with twisted angle 1.41 degree as an example. Including finding the nearestest out-of-plane atoms and nearest in-plane-atoms in twisted bilayer CrI3, as well as how to mapping the exchanges parameters from bilayer CrI3 with different slidings to twisted bilayer CrI3. All the codes are tested by Python 3.10 on windows 11. 
1. input files: "POSCAR_orth" describes the atomic position of twisted bilayer system; "criteria" describes the exchanges between two different Cr atoms via different in-plane sliding.
2. "find_nearest_oop_atoms.py" is used to find the 1-10th nearest out-of-plane atoms with output "nearest_oop.dat".
3. "find_nearest_ip_atoms.py" is used to find the 1-9th in-plane atoms with output "nearest_ip.dat".
4. ”exchange_J_D_each pair“ is used to get the exchange interactions between each two pairs in twisted bilayer CrI3, the output files are Jnearest_oop1.dat~Jnearest_oop10.dat.
5. Due to the angle difference between twisted system and bilayer system with sliding, "input_parameters_fileucf" is used to deal with the angle difference. The output files are inputucf_Jz1.dat~inputucf_Jz10.dat and inputucf_Jxy.dat.
6. In Vampire software, the magnetic interactions must pair occures, that is interactions between atom1-atom2 and atom2-atom1 must be the same. We use "remove_isolate_interactions" to remove the out-of-plane isolate interactions, the output is "inputucf_Jzs_renew".
7. After above steps, we obtain the magnetic interactions "inputucf_Jzs_renew" and "inputucf_Jxy.dat" between each Cr pairs, they will be as input in the micromagnetic simulation by using the Vampire package.
