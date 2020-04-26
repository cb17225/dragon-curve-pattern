# Dragon-Curve-Pattern
Determines 15 patterns that can be used to graph the dragon fractal.

import java.util.ArrayList;
public class DragonCurve {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("1: " + "R");
		System.out.println("2: " + "RRL");
		determinePattern("RRL", 2);
	}
	
	public static void determinePattern(String s, int n) {
		if (n == 15) {
			return;
		} else {
			String newString = s + "R" + reverseString(s);
			System.out.println((n + 1) + ": " + newString);
			determinePattern(newString, n + 1);
		}
	}
	
	public static String reverseString(String g) {
		char temp = 'a';
		String reverse = "";
		ArrayList<Character> array = new ArrayList();
		for (int i = 0; i < g.length(); i++) {
			array.add(g.charAt(i));
		}
		
		for (int i = 0; i < array.size() / 2; i++) {
			temp = array.get(i);
			array.set(i, array.get(array.size() - 1 - i));
			array.set(array.size() - 1 - i, temp);
		}
		
		for (int i = 0; i < array.size(); i++) {
			if (array.get(i) == 'R') {
				array.set(i, 'L');
			} else {
				array.set(i, 'R');
			}
		}
		
		for (int i = 0; i < array.size(); i++) {
			reverse += Character.toString(array.get(i));
		}
		
		
		return reverse;
	}

}

