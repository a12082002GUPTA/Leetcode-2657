# Leetcode-2657

# C++

class Solution {
public:
    vector<int> findThePrefixCommonArray(vector<int>& A, vector<int>& B) {
        vector<int>sol;
        map<int,int>mp;
        int count=0;
        for(int i=0;i<A.size();i++)
        {
            mp[A[i]]++;
            if(mp[A[i]]==2)count++;
            mp[B[i]]++;
            if(mp[B[i]]==2)count++;
            sol.push_back(count);
        }
        return sol;
    }
};

# Java

import java.util.*;

class Solution {
    public int[] findThePrefixCommonArray(int[] A, int[] B) {
        List<Integer> sol = new ArrayList<>();
        Map<Integer, Integer> map = new HashMap<>();
        int count = 0;
        
        for (int i = 0; i < A.length; i++) {
            map.put(A[i], map.getOrDefault(A[i], 0) + 1);
            if (map.get(A[i]) == 2) count++;
            
            map.put(B[i], map.getOrDefault(B[i], 0) + 1);
            if (map.get(B[i]) == 2) count++;
            
            sol.add(count);
        }
        
        // Convert List<Integer> to int[]
        int[] result = new int[sol.size()];
        for (int i = 0; i < sol.size(); i++) {
            result[i] = sol.get(i);
        }
        
        return result;
    }
}


# Python


from typing import List

class Solution:
    def findThePrefixCommonArray(self, A: List[int], B: List[int]) -> List[int]:
        sol = []
        mp = {}
        count = 0
        for i in range(len(A)):
            mp[A[i]] = mp.get(A[i], 0) + 1
            if mp[A[i]] == 2:
                count += 1
            mp[B[i]] = mp.get(B[i], 0) + 1
            if mp[B[i]] == 2:
                count += 1
            sol.append(count)
        return sol
