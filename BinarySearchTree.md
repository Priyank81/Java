# Java

//Node
package Tree;

public class Node{
		int data;
		Node left, right;
		
		Node(int data){
			this.data= data;
			left = null;
			right= null;
		}
	}	


package Tree;
///main class
public class BMain {
	
	public static void main(String[] args) {
		BTree bt = new BTree();
		
		bt.insert(10);
		bt.insert(20);
		bt.insert(5);
		bt.insert(3);
		bt.insert(4);
		bt.insert(50);
		bt.insert(60);
		System.out.println("Test"+bt.root.left.data);
		bt.inorder(bt.root);
		System.out.println(" ");
		bt.postorder(bt.root);
		System.out.println(" ");
		bt.preorder(bt.root);
		
	}

}

//Tree functions
package Tree;

public class BTree {
	Node root = null;
	Node temp= root;

	void insert(int data) {
		root = insertRec(root, data);
	}
	Node insertRec(Node root, int data) {
		if(root==null) {
			root = new Node(data);
			return root;
		}
		if(data<root.data) {
			root.left =  insertRec(root.left, data);
		}else if(data>root.data) {
			root.right = insertRec(root.right,data);
		}
		return root;
	}
	
	
	void inorder(Node root) {
		if(root== null) {
			return;
		}
		inorder(root.left);
		System.out.println("Node data = "+root.data);
		inorder(root.right);
	}
	
	void preorder(Node root) {
		if(root== null) {
			return;
		}
		System.out.println("Node data = "+root.data);
		preorder(root.left);
		preorder(root.right);
	}
	
	void postorder(Node root) {
		if(root== null) {
			return;
		}
		postorder(root.left);
		postorder(root.right);
		System.out.println("Node data = "+root.data);
	}
	
}

