# interviewQuestions
solution for intreview questions
package simple;

import java.util.HashSet;
import java.util.Set;

public class New {

	public static boolean happyNumber(int a) {
		Set<Integer> set = new HashSet<>();
		int rez = squaredDigits(a, set);
		if (rez == -1)
			return true;
		return false;
	}

	private static int squaredDigits(int x, Set<Integer> set) {

		if (!set.add(x))
			return 0;
		int input = x;
		if (input == 1) {
			return -1;
		}
		int sum = 0;
		while (input != 0) {
			int mod = input % 10;
			sum += mod * mod;
			input = input / 10;
		}
		return squaredDigits(sum, set);
	}

	public static void main(String[] args) {

		System.out.println(happyNumber(1));
		System.out.println(happyNumber(0));
	}

}
