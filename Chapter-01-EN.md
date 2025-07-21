# Chapter 1: What is DFT? 

### 1.1 & 1.2: Learning to "Drive", Not to "Build a Car"

This chapter started by telling me that learning DFT is like learning to drive a car; our goal is to learn how to use it, not to dive deep into the engine's internal structure right from the start. Section 1.2 gave examples like catalysis and material embrittlement, mainly to show us that DFT can solve cutting-edge problems. This part is mostly about building confidence, and it's okay if you don't fully understand it as a beginner.

### 1.3 & 1.4: The Core Idea of DFT

The content of these two sections can be looked at together, as they explain the core logic of DFT.

First is the concept of a "functional". It's different from a function: a function is "input a number, output a number," whereas a functional is more like "input a function, output a number." The ground state energy E is a functional of the electron density n(**r**).

To find the system's ground state energy E, we need to solve the Schrödinger equation, HΨ=EΨ. But this wave function Ψ contains the coordinates of all N electrons, making it a 3N-dimensional monster, which is intimidating.

The power of DFT is that it tells us we don't need to solve for that 3N-dimensional Ψ. We can use a simple 3-dimensional variable instead—the electron density n(**r**). The validity of this idea is guaranteed by the two Hohenberg-Kohn (H-K) theorems.

1.  The ground state energy is uniquely determined by the ground state electron density n(**r**).
2.  Only the true ground state electron density will cause the energy functional E[n(**r**)] to reach its minimum value.

> In plain language: a specific charge density corresponds to only one ground state energy, and the charge density that makes the energy lowest is the true solution we're looking for. This immediately reduces the problem from 3N dimensions down to 3!

So how do we find the n(**r**) that corresponds to this lowest energy? We use a method called "self-consistent solution":

1.  First, we "guess" an initial electron density n(**r**).
2.  We plug this n(**r**) into the Kohn-Sham (K-S) equations and solve for a set of single-electron wave functions, ψᵢ.
3.  We then use this set of ψᵢ to calculate a new electron density n(**r**).
4.  We compare the "guessed" n(**r**) with the calculated n(**r**). If they are more or less the same, we're done! The n(**r**) at this point is the solution we need. If they're different, we take the newly calculated n(**r**) and repeat the process, iterating until they are consistent.

### 1.5: The Approximation in DFT

A part of the K-S equations is called the "exchange-correlation functional." This part is very complex and has no exact formula. We can only use approximations to handle it, such as LDA and GGA. The choice of approximation directly determines the accuracy of the calculation.

### 1.6: DFT's Place in the Computational Chemistry Family

I initially felt this section wasn't very important; it's more like a "travel guide" that introduces other computational methods besides DFT.

These methods are called "wave function methods" (e.g., HF, CCSD) and can be seen as different brands of "cars." Their goal is also to solve the Schrödinger equation, but they take the route of directly solving for the 3N-dimensional wave function Ψ.

Their advantage is that, in theory, they can be made infinitely accurate. But the disadvantage is that they are extremely slow and expensive!

The reason DFT is so popular is because it's highly cost-effective. It can produce very good results within an acceptable amount of time, making it a very practical choice in scientific research.

### 1.7: The Limitations of DFT

Finally, section 1.7 lists a few things DFT can't do well, such as being inaccurate for excited states, underestimating band gaps, struggling with weak interactions, and being limited to a certain number of atoms (a few hundred atoms is already very demanding). It's enough to just be aware of this part; in short, it lets us know that this tool is not omnipotent.
