# Trees

## Teaching Through a Walkthrough Example

## Topic: Adding a Node to a Binary Tree Using Breadth First Traversal

**What I Learned:**
I learned how to add a node to a binary tree using the breadth first traversal strategy. This method ensures that all levels of the tree are filled from top to bottom, left to right.

**Walkthrough Example:**

Imagine we have the following binary tree and we want to add a new node with the value `G`.

    A
   / \
  B   C
 / \
D   E
     \
      F

1. **Start with the Root**:
   - We begin at the root node `A` and place it in a queue.
   - **Queue**: [A]

2. **Dequeue and Check Children**:
   - Dequeue `A`. Check if `A` has both children.
   - `A` has `B` and `C` as children, so enqueue `B` and `C`.
   - **Queue**: [B, C]

3. **Move to the Next Node**:
   - Dequeue `B`. Check if `B` has both children.
   - `B` has `D` and `E` as children, so enqueue `D` and `E`.
   - **Queue**: [C, D, E]

4. **Continue Traversal**:
   - Dequeue `C`. Check if `C` has both children.
   - `C` has no children, so the new node `G` will be added as the left child of `C`.
   - **Queue**: [D, E]

5. **Update the Tree**:
   - The tree now looks like this:
         A
        / \
       B   C
      / \   \
     D   E   G
          \
           F
   - The breadth first traversal ensures the tree is filled top-down, left to right.

## Vocabulary/Definition List

1. **Binary Tree**: A tree data structure where each node has at most two children.
2. **K-ary Tree**: A tree data structure where each node can have up to `k` children.
3. **Node**: An element in the tree containing a value and references to child nodes.
4. **Root**: The top node of a tree.
5. **Leaf**: A node that does not have any children.
6. **Edge**: A link between a parent and child node.
7. **Breadth First Traversal**: Traversal method that explores nodes level by level, left to right.
8. **Queue**: A data structure used to keep track of nodes during breadth first traversal.

## Comment on a Classmate's Post

**Classmate's Post:**
"I learned about the depth first traversal methods in trees: pre-order, in-order, and post-order. Each method processes nodes in a different sequence, which can be useful for various applications."

**My Comment:**
"Great explanation! Depth first traversal is indeed very versatile. For instance, in-order traversal is particularly useful for binary search trees because it processes nodes in ascending order. Could you give an example of when pre-order or post-order traversal might be more advantageous than in-order?"

## Fill-in-the-Blank Worksheet

1. In a binary tree, each node has at most __ children.
2. The __ of a tree is the number of edges from the root to the furthest leaf.
3. Breadth first traversal uses a __ to keep track of nodes.
4. In a binary search tree, nodes to the left of the root are __ than the root.
5. The __ node is the top node of a tree.

**Answers:**
1.two
2.height
3.queue
4.smaller
5.root
