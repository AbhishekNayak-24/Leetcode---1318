# Leetcode---1318
Minimum Flips to Make a OR b Equal to c
// Code in java
public class Solution {
    public int minFlips(int a, int b, int c) {
        int flips = 0;
        while (a > 0 || b > 0 || c > 0) {
            int bitA = a & 1;
            int bitB = b & 1;
            int bitC = c & 1;

            if (bitC == 0) {
                flips += bitA + bitB;
            } else {
                if (bitA == 0 && bitB == 0) {
                    flips++;
                }
            }

            a >>= 1;
            b >>= 1;
            c >>= 1;
        }
        return flips;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        int a = 2; // Example input
        int b = 6; // Example input
        int c = 5; // Example input
        int result = solution.minFlips(a, b, c);
        System.out.println(result); // Output: 3
    }
}
