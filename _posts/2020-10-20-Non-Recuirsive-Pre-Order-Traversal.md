---
layout: single
excerpt: "A non-recursive solution for Pre-Order Traversal."
header:
  overlay_color: "#333"
  teaser: /assets/images/coding.jpg
title: "Non-Recursive Pre-Order Traversal"
date:  2020-10-20
last_modified_at:  2020-10-20
category: Algorithms
tags:
- Algo
- DS
- Trees
- STL
---

Given a binary tree, we have to find the pre-order of it. We will do this with the help of while loop(iterative-solution).

We will take a stack to save the node and then read them one by one by popping them and then going right to it.

Below is the function to perform a non-recursive pre-order solution:

```
void preOrder(BinaryTreeNode *root){
    stack <BinaryTreeNode*> s;
    while(1){
        while(root){
            //process the curren node
            cout<<root->data;
            s.push(root);
            root=root->left;
        }
        if(s.empty())
            break; //if stack is empty, then break
        root=s.top();
        s.pop();
        root=root->right;
    }
}
```