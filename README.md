package basicJava;

import java.util.Scanner;

public class Binary {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.println("Please enter a Binary Number:");
		int a = sc.nextInt();

		System.out.println("Please enter a Binary Number:");
		int b = sc.nextInt();
		int[] ar1 = new int[10];
		int[] ar2 = new int[10];
		int[] ar3 = new int[10];
		for (int i = 0; i < 10; i++) {
			ar1[i] = ar2[i] = ar3[i] = 0;
		}

		int n = 0;
		while (a != 0 || b != 0) {
			ar1[n] = a % 10;
			a = a / 10;
			ar2[n] = b % 10;
			b = b / 10;
			n++;
		}

		int carry = 0;
		for (int i = 0; i < ar3.length; i++) {
			if (ar1[i] + ar2[i] <= 1) {
				ar3[i] = ar1[i] + ar2[i] + carry;
				carry = 0;
			} else {
				ar3[i] = carry;
				carry = 1;
			}
		}
		for (int i = n; i >= 0; i--) {
			System.out.println(ar3[i]);
		}
		sc.close();
	}
}
