# Direct-Randomzied-Benchmarking-using-Qiskit
Implement the characterization protocol presented in [1] using Qiskit and use it to characterise an IBMQ device. [1] TJ Proctor, A Carignan-Dugas, K Rudinger, E Nielsen, R Blume-Kohout, K Young, Direct randomized benchmarking for multi-qubit devices Phys. Rev. Lett. 123, 030503 (2019).

## Note 
This work is a part of Qiskit-Heckathon at CQT, Singapore. The project is still on-going, and, the code is still using an outside package (Pygsti) apart from Qiskit and contains some bugs.

## Description 
Given a quantum device, how do we know if the device behaves quantum mechanically as we would like it to. Randomized benchmarking is the procedure to verify performance of a quantum hardware and estimate errors of quantum gates. The traditional randomized benchmarking (also known as Clifford Randomized Benchmarking, CRB) is ineffient to evaluate the performance of more than two qubit gates because the size of clifford becomes large for multi-qubits. Only errors of individual one- and two-qubit gates cannot be used to properly evaluate the multi-qubit performance due to correlated errors which happens when all qubits run at the same time. Near-term quantum hardware will contains tenth to few hundred qubits. Therefore, it is crucial we can properly benchmark multi-qubit gates to check performance of the quantum computers.

In this project, we follow a new procedure proposed in the paper above which can benchmark multi-qubit gates and try to reproduce the results using Qiskit. The new procedure which is called Direct Randomized Benchmarking (DRB) consists of three parts.
1. creating a random stabilizer for n-qubits. (this part is done using Pygsti to produce openqasm of a random circuit and then converted into Qiskit). 
2. randomly pick native gates for m layers. (this is entirely done in Qiskit)
3. convert the stabilizer into one of the computational basis (called stabilizer measurement). (partially, in Pygsti).

## What's next
We will try to fix the bugs, reproduce the complete results, and convert codes in only Qiskit.
