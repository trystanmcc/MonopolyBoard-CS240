Build and run instructions.
- In "Advanced Feature Demos" you can :
  remove spaces based on property names using "removeByName"
  remove spaces based on color using "findByColor"
- The board is built using a vector pushed with board spaces which are added till max capacity with addMany

Description of the data structures used.
- We use a circular singley-linked list
- Each node stores data: "propertyName", "propertyColor", "value", "rent"
- Nodes also store a pointer to the next node, the tail node in a circular stores next as the head
- Vectors are dynamic arrays in C++ and stores our board spaces before adding it to our actual board list

A complete list of functions with short explanations.
- isEqual: checks if two nodes propertynames are the same value
- print: format of printing a properties data
- addSpace: adds an empty node to end of list if MAX_SPACES is greater than nodeCount
- addMany: adds multiple node spaces to list so long as MAX_SPACES is not hit
- movePlayer: sets playerNode to the node of the pointer of the current playerNode
- printFromPlayer: iterates through linked-list starting from playerNode printing each node data
- printBoardOnce: starting from head iterates through printing nodes data
- removeByName: iterates through linked list from head deleting and reconnecting from node with same name as function parameter
- findByColor: if node data propertyColor matches color then adds to vector which is returned
- countSpaces: iterates through list without relying on nodeCount and counts amount of nodes
- clear: resets all node points and deletes nodes

Explanation of traversal and movement logic.
- We store three unique important nodes: head, player, tail
- The head starts the list and tail ends the list keeping our list organized into playable board space
- The player node is to track which node our player is playing on and can be adjusted

Explicit mention of the 40-space board limit.
- This circular singley-linked list implementation of a monopoly board has a cap of 40 spaces
- All methods that modify the count take this into account making it impossible to go over 40
