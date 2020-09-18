# binary tree
package com.pcsetting.example;
import java.util.Random;
import java.util.Scanner;
public class MyHelloWorld {
	public static void main(String[] args) {
		Scanner cin=new Scanner(System.in);
		Random ran=new Random();
		int [] a= {15,41,35,50,32};
		Node root,tem,child;
		tem=new Node();
		root=new Node();		
		child=new Node();
		tem.data=30;
		root=tem;
		child=tem;
		for(int i=0;i<5;i++) {	
			child=root;
			tem=new Node();
			tem.data=a[i];
			while(true) { //放到適合的子樹
				if(tem.data>child.data) {
					if(child.right==null) {
						child.right=tem;
						break; //如果放進去了 則跳出迴圈
					}
					else {
						child=child.right;
					}
				}
				if(tem.data<child.data) {
					if(child.left==null) {
						child.left=tem;
						break;
					}
					else {
						child=child.left;
					}
				}
			}	
		}
		output(root);
	}
	static void output(Node child) {
		Node tem=child;
		if(tem!=null) {
			System.out.print(tem.data+" ");
			output(tem.left);
			output(tem.right);
		}
	}
}
class Node{
	int data;
	Node left;
	Node right;
}
