# Developer Log (DEVLOG.md)
## Monopoly Board Simulator (Spring 2026)

Minimum **6 entries** required.

Each entry must document learning and reasoning. Fabricated bugs are not expected.

---

## Allowed Entry Types
Each entry may be one of the following:

1) **Bug Fix Entry**
- The issue encountered.
- Error messages or symptoms.
- Attempts made.
- Final resolution.

2) **Edge Case / Testing Entry**
- A failure discovered through testing.
- The specific input/state that caused it.
- The change you made to handle it correctly.

3) **Engineering Decision Entry (up to 2 allowed)**
- A design decision you made.
- An alternative approach you considered.
- Why you chose one approach over another (tradeoffs).

---

### Entry 1
**Date:** 2026-03-03  
**Entry Type:** Edge Case / Testing Entry 
**Task worked on:**  Constructors, addSpace, addMany
**Issue or decision:**  My addSpace function was not implemented in a functional method
**Error message / symptom (if applicable):** addSpace unwritten
**What I tried:** First I realized that my constructor was setup incorrectly by using this. instead of this->. Second I noticed that in the case of an empty list I was not creating new nodes.
**Fix / resolution (or final decision):**  I changed my this to proper C++ syntax. Then I changed from Node<T>* newNode = new Node<T>(value); to newNode.
**Commit(s):**  Fixed constructor and added addSpace method

---

### Entry 2
**Date:** 2026-03-07  
**Entry Type:** Bug Fix Entry 
**Task worked on:**  Created the addMany function
**Issue or decision:**  Used wrong comparison of ">=" when it should only be "<" reimplemented addSpace function when I could just call it.
**Error message / symptom (if applicable):**  No error message
**What I tried:**  I rewrote the logic with a simpler setup calling the addSpace method.
**Fix / resolution (or final decision):**  Replace with "<" to stop when less than MAX_SPACES.
**Commit(s):**  Added "addMany" function and fixed logic issues within function

---

### Entry 3
**Date:** 2026-03-08  
**Entry Type:** Bug Fix 
**Task worked on:**  Implemented movePlayer, printFromPlayer, printBoardOnce, and removeByName
**Issue or decision:**  Implementaiton for connecting tail to head node did not work if head or tail was removed if the name matched
**Error message / symptom (if applicable):**  List no longer maintains circular pattern
**What I tried:**  I first added a "setup" condition that checked if the tail, head, or player node was removed otherwise setting the prev node to the current nodes next node essentially skipping over the curr node.
**Fix / resolution (or final decision):**  I decided to start with that implemnetation either way since logically I only had the check conditions to maintain the circular loops if the name matched with one of the nodes that were different from a middle node.
**Commit(s):**  Added "removeByName" bool function debugged logic

---

### Entry 4
**Date:** 2026-03-08  
**Entry Type:** Edge Case  
**Task worked on:**  Implemented clear method
**Issue or decision:**  Removed nodes but did not reset nodeCount or unique nodes
**Error message / symptom (if applicable):**  No error message
**What I tried:**  I tried originally iterating through the linked list and only deleting the nodes after storing the current.
**Fix / resolution (or final decision):**  After iterating through the list I also added a few lines to reset unique nodes like head, tail, and player node and reset the nodeCount back to zero.
**Commit(s):**  Reset unique nodes and nodeCount in clear

---

### Entry 5
**Date:** 2026-03-08  
**Entry Type:** Engineering Decision  
**Task worked on:**  Adding spaces for the board
**Issue or decision:**  Separated sides based on color and type of space. Added corners similar to that of a real monopoly board.
**Error message / symptom (if applicable):**  No error message
**What I tried:**  
**Fix / resolution (or final decision):**  Searched real monopoly boards to hard-code a similar setup. Used a vector to push each space then used my addmany implementation to only add as many places as spaces as I have.
**Commit(s):**  Implemented board spaces separated by color and vector hardcoded option

---

### Entry 6
**Date:** 2026-03-08  
**Entry Type:** Edge Case
**Task worked on:**  Fixing findByColor and removeByNmae
**Issue or decision:**  findByColor was not working, this was discovering when testing at the end
**Error message / symptom (if applicable):**  No error message
**What I tried:**  Before I had only deleted the same node first node if it matched the color
**Fix / resolution (or final decision):**  I had to iterate to the next node by adding curr=curr->nextNode after the if check and in the for loop.
**Commit(s):**  Fixed removeByColor
