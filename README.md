# LeetCode-InvertBinaryTree-CS
A solution to Leetcode's Invert Binary Tree problem in C#

## Explanation
In this problem you have to invert a binary tree. This means that each's node's left and right node are flipped. The tree is of an unknown length so hacks such as for-loops, etc will not work. To solve this problem we write a recursive function. We check if the node is null and if so go head and return null otherwise we perform a traditional swap operation that involves a placeholder variable then call the function on itself with root.left and root.right as the argumenets and return the root node in the function.

**Stats**

Runtime: 76 ms, faster than 97.44% of C# online submissions for Invert Binary Tree.

Memory Usage: 38.6 MB, less than 7.96% of C# online submissions for Invert Binary Tree.

## Solution
```cs
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     public int val;
 *     public TreeNode left;
 *     public TreeNode right;
 *     public TreeNode(int val=0, TreeNode left=null, TreeNode right=null) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
public class Solution {
    public TreeNode InvertTree(TreeNode root) {
        if (root == null) {
            return null;
        }
        
        TreeNode tmp = root.left;
        root.left = root.right;
        root.right = tmp;
        InvertTree(root.left);
        InvertTree(root.right);
        
        return root;
    }
}
```
