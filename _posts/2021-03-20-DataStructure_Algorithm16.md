---
layout: post
title: (Java) 큐로 스택 만들기
tags:
  - 자료구조_알고리즘
---

<br>

### [LeetCode 225번. Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/)

---

- Queue에 데이터를 넣을 때, 최근에 push된 데이터가 가장 먼저 들어온 데이터가 되어야 한다.

- 따라서 데이터를 넣기 전에 큐사이즈를 기억하고, 데이터를 넣은 후에, 사이즈만큼 돌면서 기존 데이터를 poll()해서 다시 큐에 넣는다. 
  
  ```java
  class MyStack {
  
    Queue<Integer> queue = new LinkedList<>();
  
    public MyStack() {
  
    }
  
    public void push(int x) {
        int size = queue.size();
        queue.offer(x);
        for(int i=0; i<size; i++){
            queue.offer(queue.poll());
        }
    }
  
    public int pop() {
        return queue.poll();
    }
  
    public int top() {
        return queue.peek();
    }
  
    public boolean empty() {
        return queue.isEmpty();
    }
  }
  ```

/**

* Your MyStack object will be instantiated and called as such:
* MyStack obj = new MyStack();
* obj.push(x);
* int param_2 = obj.pop();
* int param_3 = obj.top();
* boolean param_4 = obj.empty();
  */
  
  ```
  
  ```
