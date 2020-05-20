+++
title = "Tire(Prefix Tree)"
date = "2020-05-12"
author = "Benjamin Cai"
description = "Learn Data Structure Prefix Tree"
showFullContent = false
+++


## Why Tire?
With Trie, we can do `insert`, `search` in O(L) time, which is obviously faster than BST


Here is the question:
Implement a trie with insert, search, and startsWith methods.

Example:

Trie trie = new Trie();

trie.insert("apple");
trie.search("apple");   // returns true
trie.search("app");     // returns false
trie.startsWith("app"); // returns true
trie.insert("app");   
trie.search("app");     // returns true
Note:

You may assume that all inputs are consist of lowercase letters a-z.
All inputs are guaranteed to be non-empty strings.


We want to have a structure that can find "apple" fastest -- Trie



```Python

# The best solution I see is use two set, one for word, one for prefix
class trie:

def __init__ (self):
    self.set1 = set()
    self.set2 = set()


def insert(self, word:str) -> None:
    self.set1.add(word)
    for i in rang(len(word)):
        self.set2.add(word[:i+1])
    # since set elements are unique, add prefix to set2


# Set 1 to search
def search(self, word:str) -> bool:
    if word in self.set1:
        return True
    else:
        return False


# Set 2 to prefix
def startsWith(self, prefix: str) -> bool:
    if prefix in self.set2:
        return True
    else:
        return False
```