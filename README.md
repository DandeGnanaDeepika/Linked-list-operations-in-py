# Linked-list-operations-in-py
Inserting, Deleting operations in a linked list in python
class node:
    def __init__(self,val):
        self.val=val
        self.nex=None
class linked_list():
    def __init__(self):
        self.head=None
        self.rear=None
    def insert_beg(self,val):
        if(self.head==None and self.rear==None):
            self.head=self.rear=node(val)
        else:
            temp=self.head
            self.head=node(val)
            self.head.nex=temp
    def insert_end(self,val):
        if(self.head==None and self.rear==None):
            self.head=self.rear=node(val)
        else:
            self.rear.nex=node(val)
            self.rear=self.rear.nex
    def del_beg(self):
        if(self.head==None and self.rear==None):
            print("Nothing to delete")
        else:
            temp=self.head
            self.head=temp.nex
            temp=None
    def del_end(self):
        if(self.head==None and self.rear==None):
            print("Nothing to delete")
        else:
            temp=self.head
            while(temp.nex.nex!=None):
                temp=temp.nex
            self.rear=temp
            self.rear.nex=None
    def print_list(self):
        temp=self.head
        while(temp!=None):
            print(temp.val,end=" ")
            temp=temp.nex
        print()
def main():
    link=linked_list()
    while(True):
        print("1.insert at the beginning")
        print("2.insert at the end")
        print("3.delete at end")
        print("4.delete at beginning")
        print("5.print the list")
        n=int(input())
        if(n==1):
            val=int(input())
            link.insert_beg(val)
        elif(n==2):
            val=int(input())
            link.insert_end(val)
        elif(n==3):
            link.del_end()
        elif(n==4):
            link.del_beg()
        elif(n==5):
            link.print_list()
if(__name__=='__main__'):
    main()
