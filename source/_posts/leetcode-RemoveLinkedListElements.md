title: leetcode ���� RemoveLinkedListElements
  - ���
date: 2015-04-24 22:47:00
---

leetcode�����³���һ���⣬�����203���������˼�����һ����д������AC�ˡ������ѶȲ��󣬾��������鷳��

��Ŀ�ǣ�����һ�������һ��ֵ���Ƴ����д����ֵ�Ľڵ㣬����������ͷ��

[https://leetcode.com/problems/remove-linked-list-elements/](https://leetcode.com/problems/remove-linked-list-elements/)

<!-- more -->

�������Ѷ����ڣ�

+ ɾ��ĳ���ڵ�ʱ����Ҫ������ǰ�����ӵ����ĺ��������һ����������nextָ�룬��ôͨ�����Ҳ�������ǰ��ڵ㡣
+ �����Ǹ��������ͨ�����ַ��������һ����ÿ�ζ�������ָ��ڵ�ĺ�һ������һ���Ǳ���nextָ��ĵ�ַ�����������õ��Ǻ�һ�֣������֪����ָ�������Щ�Ѿ���
+ ɾ���ڵ��ʱ��Ҫ�ж����ǲ���head��

���루��ע�͵Ķ�ע���ˣ���

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) 
    {
        // p����head����next�ĵ�ַ
        ListNode **p = &head;
        while(*p)
        {
            // tmp�������浱ǰ��nextָ��
            ListNode *tmp = *p;
            if(tmp->val == val)
            {
                // �ڵ���Ҫ�Ƴ������
                // ���Ȱ�*p��ǰ�����ӵ�����
                *p = (*p)->next;
                // ���Ҫɾ����head����head����Ųһ��
                if(tmp == head)
                    head = *p;
                delete tmp;
            }
            else
                // �ڵ㲻��Ҫ�Ƴ������*p����Ųһ��
                p = &((*p)->next);
        }
        return head;
        
    }
};
```