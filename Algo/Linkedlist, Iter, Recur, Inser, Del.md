compare recur for different purpose
- when sum up is needed
- when no operation is needed
	
	
search in sorted
- early exist when target < current

Insert into place
- prev, cur, nex
- insert at head? insert and move head until head isn't the place anymore
- insert into body: 
- while(cur && cur not at place)
	- prev = cur;
	- cur = cur.next;
- now either cur == null || cur is at place
	- prev.next = new Node, prev.next.next = cur

Delete target
- prev = new, cur= head, prev.next =cur
- delete at head: while (head == target) head = head.next; cur = cur.next;
- while (cur ), if(cur.value == target) prev.next = cur.next; else, prev = prev,next
- cur.next