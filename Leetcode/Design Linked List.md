**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```c
typedef struct Node {
    int val_;
    struct Node *next_;
} Node;

Node *NodeCreate(int val, Node *next) {
    Node *new_node = (Node *)malloc(sizeof(Node));
    if (new_node == NULL)
        return NULL;

    new_node->val_ = val;
    new_node->next_ = next;

    return new_node;
}

void NodeFree(Node **tmp) {
    free(*tmp);
    *tmp = NULL;
}

typedef struct {
    Node *head_;
    Node *tail_;
    int size_;
} MyLinkedList;

MyLinkedList* myLinkedListCreate() {
    MyLinkedList *obj = (MyLinkedList *)malloc(sizeof(MyLinkedList));
    if (obj == NULL)
        return NULL;
    
    obj->head_ = NULL;
    obj->tail_ = NULL;
    obj->size_ = 0;

    return obj;
}

int myLinkedListGet(MyLinkedList *obj, int index) {
    if (index < 0 || index >= obj->size_)
        return -1;

    Node *iter = obj->head_;
    for (int i = 0; i < index; ++i)
        iter = iter->next_;

    return iter->val_;
}

void myLinkedListDeleteAtHead(MyLinkedList *obj) {
    Node *tmp = obj->head_;
    obj->head_ = obj->head_->next_;
    NodeFree(&tmp);
    /*
    Node *tmp = obj->head->next_;
    NodeFree(obj->head_);
    obj->head_ = tmp;
    */
    obj->size_--;
    if (obj->size_ == 0)
        obj->tail_ = NULL;
}

void myLinkedListAddAtHead(MyLinkedList *obj, int val) {
    Node *new_node = NodeCreate(val, obj->head_);
    if (new_node == NULL)
        return;
    if (obj->size_ == 0)
        obj->tail_ = new_node;

    obj->head_ = new_node;

    obj->size_++;
}

void myLinkedListAddAtTail(MyLinkedList *obj, int val) {
    Node *new_node = NodeCreate(val, NULL);

    if (obj->size_ == 0)
        obj->head_ = new_node;
    else
        obj->tail_->next_ = new_node;

    obj->tail_ = new_node;

    obj->size_++;
}

void myLinkedListAddAtIndex(MyLinkedList *obj, int index, int val) {
    if (index < 0 || index > obj->size_)
        return;

    if (index == 0) {
        myLinkedListAddAtHead(obj, val);
        return;
    }
        
    if (index == obj->size_) {
        myLinkedListAddAtTail(obj, val);
        return;
    }  

    Node *iter = obj->head_;
    for (int i = 0; i < index-1; ++i)
        iter = iter->next_;

    Node *new_node = NodeCreate(val, iter->next_);
    if (new_node == NULL)
        return;
    iter->next_ = new_node;
    obj->size_++;
}

void myLinkedListDeleteAtIndex(MyLinkedList *obj, int index) {
    if ((index < 0) || (index >= obj->size_))
        return;

    if (index == 0) {
        myLinkedListDeleteAtHead(obj);
        return;
    }

    Node *iter = obj->head_;
    for (int i = 0; i < index-1; ++i)
        iter = iter->next_;

    Node *tmp = iter->next_;
    iter->next_ = iter->next_->next_;
    if (obj->tail_ == tmp)
        obj->tail_ = iter;
    NodeFree(&tmp);

    obj->size_--;
}

void myLinkedListFree(MyLinkedList *obj) {
    Node *cur = obj->head_;
    while (cur != NULL) {
        Node *tmp = cur->next_;
        NodeFree(&cur);
        cur = tmp;
    }

    obj->head_ = NULL;
    obj->size_ = 0;
    free(obj);
}

/**
 * Your MyLinkedList struct will be instantiated and called as such:
 * MyLinkedList* obj = myLinkedListCreate();
 * int param_1 = myLinkedListGet(obj, index);
 
 * myLinkedListAddAtHead(obj, val);
 
 * myLinkedListAddAtTail(obj, val);
 
 * myLinkedListAddAtIndex(obj, index, val);
 
 * myLinkedListDeleteAtIndex(obj, index);
 
 * myLinkedListFree(obj);
*/
```
**Explanation:**
	Цель: Нужно реализовать Linked List.
	Pешение: Реализован Linked List с head, tail и size. Можно сказать почи ванильная версия, но добавление в конец за O(1).
