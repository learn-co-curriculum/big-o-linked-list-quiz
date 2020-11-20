# Day 2: Big O Linked List Quiz

In this quiz we'll ask you to calculate the time complexity for several of the methods declared inside the LinkedList class.

1. Mult choice

Calculate the time complexity for the following method:

<h3>JavaScript</h3>
<pre>
<code>
print() {
  this.iterate(node => console.log(node.value));
}
</code>
</pre>

<h3>Ruby</h3>
<pre>
<code>
def print
  iterate { |node| puts node.value }
end
</code>
</pre>

- O(n): Linear time
  - Correct! The number of Nodes in the Linked List determines how many values are printed, so this method runs in linear time.
- O(1): Constant time
  - Not quite. How many times will the values be printed to the console?
- I don't know
  - With time and practice, it'll start to sink in. Keep studying and you'll get there.

2. Mult choice

Calculate the time complexity for the following method:

<h3>JavaScript</h3>
<pre>
<code>
addFirst(node) {
  node.next = this.head;
  this.head = node;
}
</code>
</pre>

<h3>Ruby</h3>
<pre>
<code>
def add_first(node)
  node.next_node = @head
  @head = node
end
</code>
</pre>

- O(1): Constant time
  - Correct! There are two operations here that both run in constant time, so Big O is O(1).
- O(2): Constant time
  - Not quite. Remember that we need to simplify our notation, so constant time is always expressed as O(1).
- O(log n): Logarithmic time
  - Not quite. Keep in mind that for logarithmic time operations, the input gets divided as it's operated upon. Here we're just setting the <code>head</code> attribute to a new value and the <code>next</code> attribute also.
- I don't know
  - With time and practice, it'll start to sink in. Keep studying and you'll get there.

3. Mult choice

Calculate the time complexity for the following method:

<h3>JavaScript</h3>
<pre>
<code>
removeFirst() {
  const oldHead = this.head;

  if (this.head !== null) {
    this.head = this.head.next;
  }

  return oldHead;
}
</code>
</pre>

<h3>Ruby</h3>
<pre>
<code>
def remove_first
  old_head = @head
  @head = @head.next_node unless @head.nil?
  old_head
end
</code>
</pre>

- O(1): Constant time
  - Yes! Updating attributes runs in constant time! How does this compare to calling <code>shift</code> on an Array?
- O(n): Linear time
  - Not quite. What is Big O for accessing an attribute on an object?
- I don't know
  - With time and practice, it'll start to sink in. Keep studying and you'll get there.

4. Mult choice

Calculate the time complexity for the following method:

<h3>JavaScript</h3>
<pre>
<code>
remove(idx) {
  if (idx === 0) {
    return this.removeFirst();
  }

  let oldNode = null;

  this.iterate((node, count) => {
    if (count === idx - 1) {
      oldNode = node.next;
      node.next = node.next.next;

      return true;
    }
  }); 

  return oldNode;
}
</code>
</pre>

<h3>Ruby</h3>
<pre>
<code>
def remove(idx)
  if idx.zero?
    return remove_first
  end

  iterate do |node, count|
    if count == idx - 1
      old_node = node.next_node
      node.next_node = node.next_node.next_node
      return old_node
    end
  end
end
</code>
</pre>

- O(n): Linear time
  - Yes! Iterating over the list to find the correct location is the weakest link and depends on the provided index. Inserting the node and updating the <code>next</code> pointers is a constant time operation, so iteration wins the Battle of the Big O, giving us linear time.
- O(1): Constant time
  - Not quite. What is Big O for iterating until the correct location is found?
- I don't know
  - With time and practice, it'll start to sink in. Keep studying and you'll get there.