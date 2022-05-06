# Implementation: Trees

To turn in your reading “Reply” to this discussion by teaching something that you learned. Then review what one of your classmates learned, and leave a comment.

Some ideas for how you might want to teach:

* Use an analogy
* Explain a detail in depth
* Use WHY, WHAT, HOW structure
* Tutorial / walk through an example
* Write a quiz
* Create a vocabulary/definition list
* Write a cheat sheet
* Create a diagram / visualization / cartoon of a topic
* Anthropomorphize the concepts, and write a conversation between them
* Build a map of the information
* Construct a fill-in-the-blank worksheet for the topic

#### Common Terms
* Node - A tree node is a component which may contain it's own values, and refences to other nodes
* Root - the root is the node at the beginning of the tree
* K - number that specifies max number of children any node can have
* Left - Reference to one child node (In a binary tree where k is 2)
* Right - Reference to the other child node (In a binary tree where k is 2)
* Edge - Edge of the tree which is liinked between a parent and child
* Leaf - leafe is a node that doesn't have any children
* height- height of the tree is the number of edges from root to furthest leaf

#### Two Methods of Traversals
* Depth first - prioiritzing going through the heigh of the tree first
	![[Pasted image 20220505200019.png]]
	* pre-order - root -> left -> right [A,B,D,E,C,F]
	* in-order - left -> root -> right [D,B,E,A,F,C]
	* post-order - left -> right -> root [D,E,B,F,C,A]
* Breadth first- iterates through the tree by going through each level node-by-node
	* output: [A,B,C,D,E,F]

#### Adding a Node
There's no structural rule for where nodes are suppose to go within a binary tree. So it doesn't matter where a new node gets placed. 

So the strategy used is to add a new node till each "child" position is filled. if there is a left but not a right add to right, if there isn't a child position open to make a child a parent. 

In the event of adding a node being placed in a specific location, you need to reference both the new node to create and the parent node which the child is attached too.

Big(O)
Big O time for inserting a new node is O(n). 
Searching for a specific node would also be O(n)
Space completity would be O(w) for width, 
Height can be calculated as log n where n is the number of nodes 

Excited to dive into this new data structure. 

## Resources

Read: [Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)