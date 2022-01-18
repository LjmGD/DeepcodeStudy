# 349.两个数组的交集

```java
class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
         HashSet<Integer> n1 = new HashSet<>();
        HashSet<Integer> n2 = new HashSet<>();
        for (int i = 0; i < nums1.length; i++) {
            n1.add(nums1[i]);
        }
        for (int i = 0; i < nums2.length; i++) {
            n2.add(nums2[i]);
        }
        n1.retainAll(n2);
        int[] res = new int[n1.size()];
        int j = 0;
        Iterator<Integer> iterator = n1.iterator();
        while (iterator.hasNext()) {
            Integer next =  iterator.next();
            res[j++] = next;
        }
        return res;

    }
}
```

# 88.合并两个有序数组

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int[] res = new int[m+n];
        int i1=0,i2=0;
        int j = 0;
        while(i1 < m || i2 < n){
            if (i1 == m){
                j = nums2[i2++];
            }else if (i2 == n){
                j = nums1[i1++];
            }else if (nums1[i1] > nums2[i2]){
                j = nums2[i2++];
            }else {
                j = nums1[i1++];
            }
            res[i1+i2-1] = j;
        }
        for (int i = 0; i < res.length; i++) {
            nums1[i] = res[i];
        }
    }
}
```

# 234.回文链表
