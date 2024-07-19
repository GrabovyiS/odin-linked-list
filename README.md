# Odin linked list

Just wanted to point out an observation about a decision to make here. I've decided to implement size, tail and head as properties of linked list, not via get/set methods. On one hand, "manually" keeping track of what node is the head and what node is the tail and how the size changes adds some constant amount of steps on every insert/delete function call. On the other hand, if I didn't keep track of these things, I would have to traverse the entire list to count up the elements whenever I needed to know the size of my list with time complexity of O(n). Or, similarly, traverse the entire array to get to the tail element pointing at null. I suppose that doing it the way I chose to do it is better in terms of time complexity, which probably will be more significant and apparent on larger list sizes.

Note: in this implementation head is not a pointer/reference to the first element of the list, instead it is the first element itself. This makes it so that there is actually nothing before the first element, making things like popping the first element when its the last one an edge case. I didn't want to bother with this because JS does not have real pointers, but maybe I should have.
