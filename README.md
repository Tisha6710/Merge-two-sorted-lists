# Merge-two-sorted-lists
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {

        // Create a dummy node to start the merged list
        ListNode dummy = new ListNode(-1);

        // Tail pointer to build the new list
        ListNode tail = dummy;

        // Loop until any one list becomes empty
        while (list1 != null && list2 != null) {

            // If list1 value is smaller → attach list1 node
            if (list1.val < list2.val) {
                tail.next = list1;
                list1 = list1.next;
            } 
            // Else attach list2 node
            else {
                tail.next = list2;
                list2 = list2.next;
            }

            // Move tail ahead
            tail = tail.next;
        }

        // After loop, attach whichever list is remaining
        if (list1 != null) {
            tail.next = list1;
        } else {
            tail.next = list2;
        }

        // Return the real head of merged list
        return dummy.next;
    }
}
