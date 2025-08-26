### Theory

A pushdown automaton (PDA) is a finite automaton with a stack for memory purposes. A nondeterministic pushdown automaton (NPDA) has one, or more than one, transition for each input that it reads.
A context-free grammar (CFG) is the generator of a language, whereas a PDA and NPDA are the recognizers of a non-regular language.
To convert a CFG to an NPDA, we follow these steps:
  <ul>
    <li>
      <strong>Step 1:</strong> The stack is initially empty. Make the first transition as <code>&epsilon;, &epsilon; → Γ</code>. Before reading or popping the CFG, push the start variable on the stack.
    </li>
    <li>
      <strong>Step 2:</strong> Read nothing from the CFG in case of the start variable, pop it from the top of the stack, and push all the productions that the start variable produces. In the same step, read all the inputs of the CFG, pop, and push from the top of the stack according to the grammar rules mentioned in the CFG. This step transitions into a self-loop until all productions are read, popped, and pushed according to the CFG.
    </li>
    <li>
      <strong>Step 3:</strong> When there are no more productions to be read as input, pop the <code>Γ</code> symbol and push nothing. Make the last state the final state.
    </li>
<li> <strong>Step 4:</strong>
symbol and push nothing. Make the last   When there are no more productions to be read as input, pop the &Gamma;
state the final state. 
    </li>
  </ul>