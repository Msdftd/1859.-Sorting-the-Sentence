# 1859.-Sorting-the-Sentence
1859. Sorting the Sentence leetcode Solution

class Solution {
    public String sortSentence(String s) {
        Map<Integer, String> indexMap = new TreeMap<>(); // Use TreeMap to automatically sort by index

        String[] words = s.split(" ");
        
        for (String word : words) {
            int lastIndex = word.length() - 1;
            int index = word.charAt(lastIndex) - '0';
            String actualWord = word.substring(0, lastIndex);
            indexMap.put(index, actualWord);
        }

        StringBuilder actualString = new StringBuilder();
        
        for (Map.Entry<Integer, String> indexWord : indexMap.entrySet()) {
            actualString.append(indexWord.getValue());
            actualString.append(" ");
        }
        
        return actualString.toString().trim();
    }
}
