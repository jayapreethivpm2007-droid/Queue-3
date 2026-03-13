Queue with Menu Driven Program

class Node:
    def __init__(self,data):
        self.data=data
        self.next=None

class Queue:
    def __init__(self):
        self.front=None
        self.rear=None

    def enqueue(self,data):
        new=Node(data)

        if self.rear==None:
            self.front=self.rear=new
            return

        self.rear.next=new
        self.rear=new

    def dequeue(self):
        if self.front==None:
            print("Queue Empty")
            return

        temp=self.front
        self.front=temp.next
        print("Deleted:",temp.data)

    def display(self):
        temp=self.front
        while temp:
            print(temp.data,end=" ")
            temp=temp.next
        print()

q=Queue()

while True:
    print("\n1.Enqueue 2.Dequeue 3.Display 4.Exit")
    ch=int(input("Enter choice: "))

    if ch==1:
        x=int(input("Enter element: "))
        q.enqueue(x)

    elif ch==2:
        q.dequeue()

    elif ch==3:
        q.display()

    elif ch==4:
        break

Output:
1.Enqueue 2.Dequeue 3.Display 4.Exit
Enter choice: 1
Enter element: 10

1.Enqueue 2.Dequeue 3.Display 4.Exit
Enter choice: 1
Enter element: 20

1.Enqueue 2.Dequeue 3.Display 4.Exit
Enter choice: 3
10 20

1.Enqueue 2.Dequeue 3.Display 4.Exit
Enter choice: 2
Deleted: 10


1.Enqueue 2.Dequeue 3.Display 4.Exit
Enter choice: 3
20 
