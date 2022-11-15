# Qiskit vs OpenQASM 

### Qiskit
Qiskit is IBM's open source software library for quantum computing. It covers a wide functional range, allowing modeling of high-level algorithms to low-level quantum qubits, gates, and pulses.  
  
### OpenQASM
OpenQASM is the open source quantum assembly language. It allows focused work on qubits and gates. 
<br>
<br>
|Name|Language|Code Level|Type|Used For|
|---|---|---|---|---|
|Qiskit|Python|Higher level|SDK (Software Development Kit)|Solving problems using classical and quantum computation|
|OpenQASM|C|Intermediate level|Assembly Language|Describing and visualizing quantum circuits|  
<br>
<br>

### Code Flow 
* Human writes Qiskit 
* Qiskit translates Python into OpenQASM (quantum machine language) 
* Stuff gets optimized  
* Low level code is sent to the physical quantum device (or simulator)  
<br>
<br>


### References
* [IBM Glossary: Qiskit](https://quantum-computing.ibm.com/lab/docs/iql/terms-glossary#term-qiskit-program)
* [IBM Glossary: OpenQASM](https://quantum-computing.ibm.com/lab/docs/iql/terms-glossary#term-openqasm)
