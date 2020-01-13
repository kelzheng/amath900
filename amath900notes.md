# AMATH 900: Quantum Computer Programming

*Prof*: Achim Kempf (akempf@uwaterloo.ca) and Nadine Stritzelberger (nstritze@uwaterloo.ca) <br>
*Schedule*: MW, 4:00 - 5:30 pm, MC 6460 <br>
*Enrollment*: To enroll in AMATH495 or AMATH900 obtain a permission number from Nadia Linares (nlinares@uwaterloo.ca). To enroll in QIC895, obtain a permission number from Kaitlyn McDonell (kmcdonell@uwaterloo.ca).  

*Pre-req*: Ch.1 + Toolkit in [Quantum Computing, An Applied Approach by Hidary](https://github.com/jackhidary/quantumcomputingbook). The book consists of:

1. Necessary frameworks that drive the design of quantum computers and circuits, what kinds of problems may be amenable to quantum computation in treatment of complexity classes (Ch 1-4)
2. Programming that makes these new machines tick (Ch 5-10)
3. Tools to use in journey to master quantum computing. Core concepts of linear algebra, table of operators and circuit elements (Ch. 14) for designing own quantum computing protocols (Ch 11-13)

*Course Outline*: Given the accelerating progress in quantum computing hardware and the recent achievement of quantum supremacy, this special topics graduate reading course is an introduction to the programming of quantum computers. We will follow the recent text "Quantum Computing: An Applied Approach" by Jack D. Hidary (Springer, Oct. 2019) and we will therefore mostly work with Python-based Cirq. The intended audience are graduate and advanced undergraduate students in related fields such as applied mathematics, physics and computer science. Students are expected to give presentations during the term.

*Contents*:

* Basics of quantum computing
* Complexity theory
* Quantum hardware
* Development libraries for quantum computer programming (esp. Cirq)
* Applications to quantum protocols and algorithms for near-term and for future error-corrected machines, from quantum machine learning and quantum chemistry to Shor’s algorithm.

*[Schedule](https://sites.google.com/view/quantum-computer-programming/schedule)*

* Lecture 1 (2020-01-06): Introduction  (Achim, Nadine, Evan)
    * Format of reading course, Guidelines for presentations
    * Presentation schedule
    * Please enter your email address here so that we can contact you (even if you are not enrolled!)
    * Installation of Python and Cirq: Colab Notebook
* Lecture 2 (2020-01-08): Basics and   History of Quantum Computing (Nadine)
    * Ch. 1, 2, 3 (p. 3-36)
    * Optional: see also video and slides by Stefan Leichenauer and this worksheet. 
* Lecture 3 (2020-01-13): Basics and History of Quantum Computing (Nadine)
    * Ch. 1, 2, 3 (p. 3-36)
* Lecture 4 (2020-01-15): Complexity Theory (Evan)
    * Ch. 4 (p. 37-44)
* Lecture 5 (2020-01-20): Hardware: Building a Quantum Computer (Evan)
    * Ch. 5 (p. 47-60)
    * See also video by Ken Brown and video and slides by Eric Ostby. 
* Lecture 6 (2020-01-22): Development Libraries for QC Programming (Evan)
    * Ch. 6 (p. 61-79)
* Lecture 7 (2020-01-27): Teleportation and Superdense Coding (Nadine)
    * Ch. 7.1 - 7.3 (p. 80-88)
* Lecture 8 (2020-01-29): Quantum Games, Bell Inequalities and Bell Inequality Test 
    * Ch. 7.4 (p. 88-93)
* Lecture 9 (2020-02-03): Deutsch-Jozsa Algorithm 
    * Ch. 8.1 (p. 95-104)
    * See also this worksheet for this and other textbook algorithms.
* Lecture 10 (2020-02-05): Bernstein-Vazirani Algorithm, Simon's Problem 
    * Ch. 8.2 - 8.3 (p. 104-108)
* Lecture 11 (2020-02-10): Quantum Fourier Transform 
    * Ch. 8.4 (p. 108-111)
    * See also the first part of this video by Stefan Leichenauer. 
* Lecture 12 (2020-02-12): Shor's Algorithm 
    * Ch. 8.5 (p. 111-126)
* Lecture 13 (2020-02-24): Shor's Algorithm 
    * Ch. 8.5 (p. 111-126)
* Lecture 14 (2020-02-26): Grover's Search Algorithm 
    * Ch. 8.6 (p. 126-130)
* Lecture 15 (2020-03-02): Variational Quantum Eigensolver 
    * Ch. 9.1 (p. 131-139)
* Lecture 16 (2020-03-04): Quantum Chemistry 
    * Ch. 9.2 (p. 139-144)
* Lecture 17 (2020-03-09): Quantum neural networks and gradients (Guillaume) 
    * Assigned reading: Quantum Approximate Optimization Algorithm (QAOA), Ch. 9.3 (p. 144-154)
    * See also this video by E. Farhi
    * See also the second part of this video by Stefan Leichenauer along with this worksheet.
* Lecture 18 (2020-03-11): Quantum optimization, adiabatic quantum computing, QAOA and other variants (Guillaume)
* Lecture 19 (2020-03-16): Quantum-classical hybrid neural networks and hybrid backpropagation (Guillaume)
    * Assigned reading: Machine Learning on Quantum Processors, Ch. 9.4 (p. 154-160)
* Lecture 20 (2020-03-18): Applications of hybrid quantum-classical neural networks for quantum simulation (Guillaume)
* Lecture 21 (2020-03-23): Google Quantum Machine Learning Software Tutorial (Guillaume, Evan, Trevor)
* Lecture 22 (2020-03-25): Quantum Phase Estimation 
    * Ch. 9.5 (p. 160-166)
* Lecture 23 (2020-03-30): Solving Linear Systems 
    * Ch. 9.6 (p. 166-178)
* Lecture 24 (2020-04-01): Quantum Random Number Generator, Quantum Walks and Implementation of a Quantum Walk 
    * Ch. 9.7 - 9.8 (p. 178-187)
* Lecture 25: Assigned reading: Applications and Quantum Supremacy, Ch. 10 (p. 189-198)

# Lecture 0: Pre-reqs

## Chapter 1: Superposition, Entanglement, Reversibility

**Quantum computing** is part of the larger field of **quantum information sciences (QIS)**, which has three branches: computation, communication, and sensing.

* **Quantum communcation** leverages unusual properties of quantum systems to transmit information in a manner that no eavesdropper can read, and is important in the post-quantum cryptography regime. Topics include **quantum specific protocols** including *quantum teleportation* and *superdense coding* (Ch. 7)
* **Quantum sensing** uses quantum devices to move beyond classical limits in sensing magnetic and other fields. Micro-PNTs (position, navigation, and timing) are a class of these kinds of sensorsthat provide highly accurate positioning data when GPS is unavailable.
* **Quantum computation** manipulates quantum states themselves, giving us a much large computing space to work in than in classical computers (which model real-world quantum physical systems in representations of subch a system (instead of the system itself)).

**Quantum computers** are devices that leverage specific properties described by quantum mechanics to perform computation.

* Every classical computer can be described by quantum mechanics since QM is the basis of the physical universe
  * However, a classical computer doesn't take advantage of specific properties and states that QM affords when doing its calculations

**3 key concepts of quantum mechanics** we use in QC are:

1. The superposition principle
2. Entanglement
3. Reversibility (and its connection with computation and physical systems)

### 1. The Superposition Principle

According to principles of QM, systems are set to a definite state only once they are **measured**.

* Before a measurement, systems are in an **indeterminate state**
* After we measure them, systems are in a **definite state** 

If we have a system that can take on one of **two discrete state states when measured**, we can represent the two states in **Dirac notation** as $|0>$ and $|1>$.

* **ket**: a vector, e.g.
    * | $\psi$> $= \begin{pmatrix}0\\1\end{pmatrix}$
    * | $\psi$>$=f(\vec{r},t)$
* **bra**: conjugate of the ket vector
    * < $\psi$| = (| $\psi$>*)$^T$ $= \begin{pmatrix}1&0\end{pmatrix}$
* **braket** < $\psi$|$\psi$> is the inner product in the Hilbert space

We can then represent a superpostion of states as a linear combination of these states such as $\frac{1}{\sqrt{2}}|0>+\frac{1}{\sqrt{2}}|1>$

> **The Superposition Principle**: The linear combination of two or more state vectors is another state vector in the same HIlber space and describes another state of the system

An example that illustrates a superposition of states is the intrinsic property of light called *polarization*. 

* Poliarization states can be selected by means of a polarizing filter, a thin film with an axis that only allows light with polarization parallel to that axis to pass through.
    * with a single polarizing filter, we can select one polarization of light, for example
        * vertical polarization, which we can denote as | $\uparrow$>
        * horization polarization, which we can denote as | $\rightarrow$>, is an orthoganol state to vertical polarization
    * Together, these states form a basis for any polarization of light.
        * Any polarization state | $\psi$> can be written as linear combination of these states. We use the Greek letter $\psi$ to denote the state of the system
        * |$\psi$> = $\alpha$| $\uparrow$> + $\beta$| $\psi$>
            * The coefficients $\alpha$ and $\beta$ are complex numbers known as **amplitudes**. 

> **The Born Rule**: In a superpostion of states, the modulus squared of the amplitutde of a state is the probability of that state resulting after measurement. Furthermore, the sum of the squares of the amplitudes of all possible states in the superposition is equal to 1. So, for the state |$\psi$> = $\alpha$|0> + $\beta$|1>, we have
$|\alpha|^2 + |\beta|^2 = 1$.

### 2. Entanglement

# Lecture 1: Jan 6, Monday
Presentation
* walk everyone through the code
* prepare a worksheet in colab
* 45 min lecture
* not a demonstration that you have read the text, it's to expalin what's in the book to fellow students, assuming that they have read it already (add value, be better than book)
    * description vs *explanation**

Scheduled for Jan 29, Ch. 7.4 (p 88-93)

Evan on [colab](https://colab.research.google.com/drive/1FvnMWhn9T7UDGhAFwSLPgGrNbr7DmDCv).

Nadine will give a lecture on Wed, will cover the first three chapters of the book (3-36)
Video and slides by Stefan in schedule along with the worksheet

# Lecture 2: Jan 8, Monday
Nadine, Ch. 1-3 - Introduction to basic concepts

**What is a quantum computer?**

* **Computers** are physical objects
    * classical computers: bits (physical objects) made up of large number of atoms, behave like macroscopic classical objects
        * **Bit**: basic unit of information in classical computing (binary digit, values 0 or 1)
        * What if bits were single atoms? They would start to behave like quantum objects (conditions for quantum behaviour to occur: system is out of contact with rest of universe, i.e. **unobserved**)
    * **Quantum computers** take advantage of QM to perform computation. We change the underlying laws of physics of computer. With **qubits**, basic unit of information, which can have:
        * a superposition of 0 and 1
        * entanglement between qubits

What is a qubit?

* **Qubits** are QM 2-level systems. 
    * Physical realization of a qubit: 
        * Two electronic energy states in a single **atom**.
            * Ground state |0>, and excited state |1> (disregard all other states)
            * By shining light on the atom, can move elctron from |0> to |1> and vice versea, but also can move electron "halfway" into a superposition of |+>
        * Position of atoms in trap or lattice
        * Two spin states of spin 1/2 particles
        * Vertical and horizontal polarization fo single photons
        * Presence or absence of phonotns in optimcal vacity (in lec 5)
    * In math, represent qubit as a 2-dim Hilbert space C2 (complex vector state)
    * States |0> and |1> are the computational basis states, can represent as column vectors
        * These form and orthonormal basis

The superposition principle
* The linear combination (superposition) of two or more states describes another state of the system in the same Hilbert space. Each term in the superposition has a complex coefficient (amplitude)

The Born Rule
* What happens when we purposely bring quantum system in contact w the rest of universe by measuring it?
> Born (1926): In a superposition of states, the modulus squared of the amplitude of a sate is the probability of that state resulting after measurement. The sum of the modulus suared of the amplitudes is 1.

* If given a qubit, no way of examining the quantum state (determine a and b)
    * can only acuqire much more resticted information (either 0 or 1) when mearuing the qubit
    * State vectors are normalized to length 1

Bloch spehere
* Geometric representation of 1 qubit
* In Notes

The measurement postulate
* In classical mecahnics:
    * Measurement has no effect on measure item
    * After measruing property A, can measure property B and be sure that A still retains its observed value
* In QM
    * Every measurable physical quantity of a system is described by an observable (M) (a Hermitian operator) acting on the state psi of the system
    * In notes 3.6
* How much information is in a qubit
    * Infinite number of points on Bloch spehre = infinite amount of information in single qubit?
        * No: measurement gives only one bit of information (0 or 1)
            * measurement changes the state of the qubit, will get the same measurement
* No simple generalization of Bloch spehere for multiple qubits
    * 2-quibit system: 4 computational basis states |00>, |01>, |10>, |11>
    * n-qubits: 2^n combitational basis states

Multiple qubits
* **Bell state** aka ERP pair, a resource to perform tasks we cannot accomplish classically (7,8)
    * 2 qubits that are entangled.
> A state of a composite system is called **entangled** if it cannot be written as a product of states of its component systems. Otherwise it is called separable

* Measurement outcomes on two qubits perfectly correlated
* Entanglement as different way of encoding information: not locally in each particle, but in correlations of different particles
* Knowing everything about subsystems doesn't necess imply we know state of composite system (missing part = entanglement)

Qudits
* Usually use qubits to build quantum comptuers, other types of computing arch are poss. 3-level qutrit, d-level qudit

Classical vs quantum state space
* CC with N bits has 2^N poss states
* QC with N qubits has 2^N basis sates (2^N-dim Hilbert space)
    * To even descirbe such a state on a CC would require 2^N-1 complex numbers (the coefficients)
* QC with N qudits has d^N basis sates (d^N-dim Hilbert space)
    * Ex 63 qutrites can rep same number of states as 100 qubits
* Ex quantum processor w 53 qubits (2^53 ==10^16) == 1 petabytpe (on 8 bit binary computer) to represent a state

What is a quantum operator?
> A quantum operator U can be represented as a matrix acting on the state vector of a quantum system. It needs to be unitary (UdaggerU=I) to preserve nomralization of states

* Quantum operators inherently reversible (as opposed to classical gates). Reverse operator by daggering it.
    * Diff from classical AND/OR gates not reversible. NOT is

Quantum circuit diagrams
* Constructed and read from left to right
* Circuit wire represented as line
* Initial state represented as ket on left of wire
* Slash n symbol for wire carrying n quibits
* ox across qubit lines for operators (unitary U) acting on those qubits
Meausrement (projection onto o or 1)


Unary Operators
* Pauli matricies

Binary Operators

Ternary Operators

[Notebook](https://colab.research.google.com/drive/1acTtPkZNdWQT1pia4OFt_VGw39Xy1f2C#scrollTo=MK4pgOtIS4pU)


vanevar 5
claude 2
jaques 4
genghis 1
landau 3
shockley 6

vanevar 5
claude 1
jaques 2
genghis 3
landau 4
shockley

10
3
6
4
7
