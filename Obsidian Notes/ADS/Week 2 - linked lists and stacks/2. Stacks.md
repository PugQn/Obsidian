A stack is like a pile of things. You only have access to the top (Last In First Out - **LIFO**).

Stack operations include:
- Push: put new item on top of stack
- Pop: remove top item
- Top: look at top item
- IsEmpty: true if stack is empty
#### Setting up a stack
A stack is created using classes:

```
//--------- Stack using array --------------

class Stack {
    private:        //Place all data in private scope so it it not directly accessible. Safer
        float data[10];
        int index;  //Identifies the top element of the stack
    public:         //Methods should be public so they can be called by outsiders from the class.
        Stack();    //Constructor. Shoudl always have the same name as the class
        ~Stack();   //Destructor
        void Push(float newThing);
        void Pop();
        float Top();
        bool isEmpty();
};
//---------------------------------------------

//Constructor
Stack::Stack() {
    index = -1;     //Set to -1 as when first value is pushed it will increment up 1
};

//Destructor
Stack::~Stack() {};

void Stack::Push (float newThing) {
    index++;
    data[index] = newThing;
};

void Stack::Pop() {
    if (index > -1) {   //Keeps the index from going beyond the scope of the array
        index --;       //Setting index back will enable overwriting of top array element.
    }
};

  

float Stack::Top() {    //Not a safe method as allows user to look at index -1
    return data[index];
};

bool Stack::isEmpty() {
    if (index <0) {
        return true;
    }
};
```

```
//----------------- Stack using linked list --------------
struct Node {
    float data;
    Node *next;
};

class Stack {
    private:
        Node * listpointer;
    public:
        Stack();    //Constructor. Shoudl always have the same name as the class
        ~Stack();   //Destructor
        void Push(float newThing);
        void Pop();
        float Top();
        bool isEmpty();
};

//---------------------------------------------------------

//Constructor
Stack::Stack() {
    listpointer = NULL;
};

//Destructor
Stack::~Stack() {};
  
void Stack::Push(float newThing) {
    Node *temp;
    temp = new Node;
    temp->data = newThing;
    temp->next = listpointer;   //listpointer is within the class so the method has access
    listpointer = temp;
};

void Stack::Pop() {
    Node *p;
    p = listpointer;
    if (listpointer != NULL) {
        listpointer->next;
        delete p;
    }
};

bool isEmpty() {
    if (listpoiter == NULL) {
        return true;
    }
};

//Always run isEmpty first
float Stack::Top() {
    if (isEmpty == true) {
        return linstpointer->data;
    }
};
```

`main()` will stay the same for both as the methods do the same things but with different underlying data types.