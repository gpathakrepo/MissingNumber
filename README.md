package com.test.recursive;

import java.util.HashSet;
import java.util.Set;

//Java Find smallest positive number NOT in unsorted array
//For example, given A = [1, 3, 6, 4, 1, 2], the function should return 5.
//Given A = [1, 2, 3], the function should return 4.
//Given A = [-1, -3], the function should return 1.
public class MissingNumber {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Set<Integer> s = new HashSet<Integer>();
//		int[] A = new int[] {1,3,6,4,1,2};
		int[] A = new int[] {-1,-3,-6,-4,-1,-2};
		System.out.println(sol(1,A,s));
	}


	static int sol(int n,int[] A, Set<Integer> s ) {
		for (int i : A) {
			if(!s.contains(i)) {
				int r = i - n;
				System.out.println("num " + n + " arr[i] " + i + " result " + r);
				if (r == 0) {
					s.add(i);
					return sol(++n, A, s);
				}
			}
		}
		return n;
	}

}
