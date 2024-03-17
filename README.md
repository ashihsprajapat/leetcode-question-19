# leetcode-question-19
leetcode question 19
[[Given the head of a linked list, remove the nth node from the end of the list and return its head.
[Example 1:])
//Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]
Example 2:
Input: head = [1], n = 1
Output: []
Example 3:
Input: head = [1,2], n = 1
Output: [1]](url)])
 /**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
        //if(head == null){
        //    return null;
        //}
        //size claculate
        ListNode size= head;
        int sz=0;
        while(size != null){
            size= size.next;
            sz++;
        }
         if (n > sz) {
            // Handle the case where n is greater than the size
            return head;
        }
        if (sz == n) {
            return head.next;
        }
        ListNode pre=head;
        for(int i=0;i<sz - n -1 ;i++){
            pre=pre.next;
        }
       pre.next = pre.next.next;

        return head;
        
    }
}
