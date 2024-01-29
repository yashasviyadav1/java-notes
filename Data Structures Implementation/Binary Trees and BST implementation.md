## BST Implementation from Scratch

```c
input : 
5 
4 6 8 1 3

Output :-
[[4], [1, 6], [3, 8]]  //level order
```

```java
// Create BST from array then find its level order

import java.util.*;
class Node{
    int data;
    Node left;
    Node right;
    Node(int data){
        this.data = data;
        left = null;
        right = null;
    }
}

public class BSTImplement {

    private static Node insertInBST(Node root, int newData){
        
        if(root == null) return new Node(newData); 

        // recursively create left and right subtrees for root
        if(newData > root.data) // new node will be somwhere on right of root
            root.right = insertInBST(root.right, newData);
        else root.left = insertInBST(root.left, newData);
        return root; 
    }

    public static void main(String ... args){

        /* input :- 
            5 
            4 6 8 1 3

            BST :-    4
                    /  \
                   1    6
                    \    \
                     3    8

        */
        Scanner scn = new Scanner(System.in);
        int n = scn.nextInt();
        int arr[] = new int[n];
        for(int i=0; i < n; i++) arr[i] = scn.nextInt();

        //insert each node 1 by 1 into BST
        Node root = new Node(arr[0]); //root
        for(int i=1; i < n; i++){
            int newData = arr[i];
            insertInBST(root, newData); 
        }  


        // lets find the level order of this BST
        ArrayList<ArrayList<Integer>> levelOrder = new ArrayList<>();
        Queue<Node> q = new LinkedList<>();
        q.add(root);

        while(q.size() != 0){
            int size = q.size();
            ArrayList<Integer> currLevel = new ArrayList<>();
            for(int i=0; i < size; i++){ // only traversing the curr level elements
                Node front = q.remove();
                if(front.left != null) q.add(front.left);
                if(front.right != null) q.add(front.right);
                currLevel.add(front.data);
            }

            //add each level to levelOrder
            levelOrder.add(currLevel); 
        }


        // printing each level
        System.out.print(levelOrder);  //[[4], [1, 6], [3, 8]]




    }
    
}

```

## Binary Tree implementation

```c
Input :
6
4 6 8 1 3 9

Output :
[[4], [6, 8], [1, 3, 9]]
```

```java

// Binary Tree Implementation from scratch 

import java.util.*;
class Node{
    int data;
    Node left;
    Node right;
    Node(int data){
        this.data = data;
        left = null;
        right = null;
    }
}

public class BTImplementation {
    
    private static void buildTreeFromlevelOrder(Node root, int[] arr){
        int index = 1; // not 0 coz root already has data of arr[0]
        Queue<Node> q = new LinkedList<>();
        q.add(root);
        
        while(q.size() != 0){
            Node front = q.remove();

            if(index >= arr.length) break; // all ele completed
            front.left = new Node(arr[index++]); // create left child
            q.add(front.left);

            if(index >= arr.length) break; // all ele completed
            front.right = new Node(arr[index++]); // create right child
            q.add(front.right);

        }
    }

    public static void main(String ... args){

        /* input :- 
            6 
            4 6 8 1 3 9


            BT :-    4
                   /   \
                  6     8
                 / \   / 
                1  3   9   

        */
        Scanner scn = new Scanner(System.in);
        int n = scn.nextInt();
        int arr[] = new int[n];
        for(int i=0; i < n; i++) arr[i] = scn.nextInt();

        //insert each node 1 by 1 into BT
        Node root = new Node(arr[0]); //root
        buildTreeFromlevelOrder(root, arr);

        // lets find the level order of this BST
        ArrayList<ArrayList<Integer>> levelOrder = new ArrayList<>();
        Queue<Node> q = new LinkedList<>();
        q.add(root);

        while(q.size() != 0){
            int size = q.size();
            ArrayList<Integer> currLevel = new ArrayList<>();
            for(int i=0; i < size; i++){ // only traversing the curr level elements
                Node front = q.remove();
                if(front.left != null) q.add(front.left);
                if(front.right != null) q.add(front.right);
                currLevel.add(front.data);
            }

            //add each level to levelOrder
            levelOrder.add(currLevel); 
        }


        // printing each level
        System.out.print(levelOrder);  // [[4], [6, 7], [1, 3, 9]]

    }
    
}


```
