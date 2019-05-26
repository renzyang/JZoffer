# try1
这写法在确定pLast上有点问题
```
class Solution {
public:
    ListNode* FindKthToTail(ListNode* pListHead, unsigned int k) {
        if(pListHead == NULL || k <= 0)
            return NULL;
               
        ListNode* pFirst = pListHead;
        for(int i=0;i<k; i++)
        {
            pFirst = pFirst->next;
            if(pFirst==NULL)
                return NULL;
        }
        ListNode* pLast = pListHead;
        
        while(pFirst!=NULL)
        {
            pFirst = pFirst->next;
            pLast = pLast->next;
            
        }
        
        return pLast;
        
    }
};
```

# try2
仅仅添加i!=(k-1)就可以包含倒数第size()个情况！

```
class Solution {
public:
    ListNode* FindKthToTail(ListNode* pListHead, unsigned int k) {
        if(pListHead == NULL || k <= 0)
            return NULL;
               
        ListNode* pFirst = pListHead;
        for(int i=0;i<k; i++)
        {
            pFirst = pFirst->next;
            if(pFirst==NULL && i!=(k-1))
                return NULL;
        }
        ListNode* pLast = pListHead;
        
        while(pFirst!=NULL)
        {
            pFirst = pFirst->next;
            pLast = pLast->next;
            
        }
        
        return pLast;
        
    }
};
```