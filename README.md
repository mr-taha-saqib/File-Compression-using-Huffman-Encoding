# Assignment 2: File Compression using Huffman Encoding

This assignment involves implementing a file compression and decompression mechanism using **Huffman Encoding**. The task is divided into three major components:

## Components to Implement

### 1. Encoder [80 Marks]
- The encoder will:
  - Convert the input file of characters into its binary representation based on the Huffman Encoding algorithm.
  - Store the encoded binary data in a file for later use (compressed format).

### 2. Decoder [20 Marks]
- The decoder will:
  - Convert the binary file back into its original form using the Huffman decoding process.

### 3. Min Heap (Tree Construction)
- **Min Heap** is required for constructing the Huffman Tree.
- You need to implement:
  - All necessary functions for heap operations, such as insertion, deletion, heapify, etc.
  - Use the heap to store and manage character frequencies for tree construction.

---

## Workflow and Steps

### Step 1: Understand Huffman Encoding
- Huffman Encoding is a lossless compression algorithm.
- It assigns variable-length binary codes to characters based on their frequency in the input file.
  - Characters with higher frequencies get shorter codes.
  - Characters with lower frequencies get longer codes.
  
### Step 2: Build a Min Heap
- Create a **Min Heap** to store nodes (characters with their frequencies).
- Each node should have:
  - A character
  - Its frequency
  - Left and right child pointers (for constructing the tree).

- Functions to implement:
  - `insert(node)`: Inserts a node into the heap.
  - `delete_min()`: Removes and returns the node with the smallest frequency.
  - `heapify()`: Maintains the heap property.

### Step 3: Construct the Huffman Tree
- Use the Min Heap to construct the Huffman Tree:
  - Remove two smallest frequency nodes from the heap.
  - Combine them into a new node with a frequency equal to the sum of the two nodes.
  - Insert the new node back into the heap.
  - Repeat until there is only one node left (the root of the tree).

### Step 4: Generate Huffman Codes
- Traverse the tree to generate Huffman Codes for each character:
  - Assign `0` for the left branch and `1` for the right branch.
  - Store the codes in a dictionary for encoding and decoding.

### Step 5: Encode the File
- Read the input file and replace each character with its Huffman Code.
- Write the binary representation to a new file (compressed format).

### Step 6: Decode the File
- Read the binary file and use the Huffman Tree to decode it back into the original text.
- Write the decoded content to a new file.
