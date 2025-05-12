# Finding-3-Digit-Even-Numbers
Leetcode problem day Question Solve
class Solution {
    public int[] findEvenNumbers(int[] digits) {
        Set<Integer> uniqueNumber = new HashSet<>();
        int n = digits.length;
        for (int i = 0; i < n; i++) {
            if (digits[i] == 0)
                continue;
            for (int j = 0; j < n; j++) {
                for (int k = 0; k < n; k++) {
                    if (i == j || j == k || k == i)
                        continue;
                    int nums = digits[i] * 100 + digits[j] * 10 + digits[k];
                    if (nums % 2 == 0) {
                        uniqueNumber.add(nums);
                    }
                }
            }
        }
        List<Integer> resultlist = new ArrayList<>(uniqueNumber);
        Collections.sort(resultlist);

        int[] result = new int[resultlist.size()];
        for (int i = 0; i < result.length; i++) {
            result[i] = resultlist.get(i);
        }

        return result;
    }
}
