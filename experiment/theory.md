### Theory  

A **Nondeterministic Pushdown Automaton (NPDA)** is a computational model that extends a finite automaton with a stack, giving it the ability to recognize **context-free languages (CFLs)**.  

A **Context-Free Grammar (CFG)** is a formal grammar that generates CFLs, whereas an NPDA recognizes them. Since both CFGs and NPDAs describe the same class of languages, any CFG can be systematically converted into an equivalent NPDA.  

When the CFG is expressed in **Greibach Normal Form (GNF)**, the conversion process to NPDA becomes straightforward:  

- In **GNF**, every production is of the form:  
  \[
  A \rightarrow a\alpha
  \]  
  where:  
  - `A` is a variable (nonterminal),  
  - `a` is a terminal,  
  - `α` is a (possibly empty) string of variables.  

- This structure ensures that every derivation step begins with a terminal, allowing the NPDA to consume one input symbol while manipulating the stack.  

---

#### Conversion of CFG (GNF) → NPDA  

To construct an NPDA \( M \) from a CFG \( G = (V, Σ, R, S) \):  

1. **Initialization**  
   - Start in the initial state `q0`.  
   - Push the start variable `S` onto the stack.  

2. **Variable Expansion**  
   - If the top of the stack is a variable `A`, and there exists a production `A → aα`:  
     - On reading terminal `a`, pop `A` from the stack.  
     - Push the string `α` (with the rightmost symbol on top).  

3. **Terminal Matching**  
   - If the top of the stack is a terminal `a` and the current input symbol is also `a`:  
     - Consume `a` from the input.  
     - Pop `a` from the stack.  

4. **Acceptance**  
   - The NPDA accepts the input if the entire string is read and the stack becomes empty.  
