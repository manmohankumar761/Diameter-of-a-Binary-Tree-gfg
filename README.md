# Diameter-of-a-Binary-Tree-gfg

Given a binary tree, the diameter (also known as the width) is defined as the number of edges on the longest path between two leaf nodes in the tree. This path may or may not pass through the root. Your task is to find the diameter of the tree.

Examples:

Input: root[] = [1, 2, 3]

Output: 2
Explanation: The longest path has 2 edges (node 2 -> node 1 -> node 3).

Input: root[] = [5, 8, 6, 3, 7, 9]

Output: 4
Explanation: The longest path has 4 edges (node 3 -> node 8 -> node 5 -> node 6 -> node 9).

#code
class Solution {
  public:

    int solve(Node* node,int &d){
        if(!node)
        return 0;
        
        int l=solve(node->left,d);
        int r=solve(node->right,d);
        
        d=max(d,l+r+1);
        
        return 1 + max(l,r);
    }
    int diameter(Node* root) {
        int d=0;
        solve(root,d);
        
        return d-1;
        
    }
};
