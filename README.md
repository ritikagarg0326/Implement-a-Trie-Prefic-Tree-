# Implement-a-Trie-Prefic-Tree-
#A trie (pronounced as "try") or prefix tree is a tree data structure used to efficiently store and retrieve keys in a dataset of strings. There are various applications of this data structure, such as autocomplete and spellchecker.
#example:-
#Input
["Trie", "insert", "search", "search", "startsWith", "insert", "search"]
[[], ["apple"], ["apple"], ["app"], ["app"], ["app"], ["app"]]
Output
[null, null, true, false, true, null, true]
#
#
#
class Trienode:
    def __init__(self):
        self.isend=False
        self.child={}

class Trie:

    def __init__(self):
        self.root=Trienode()
        

    def insert(self, word: str) -> None:
        current = self.root
        for i in word:
            if i not in current.child:
                current.child[i]=Trienode()
            current = current.child[i]
        current.isend=True 
        

    def search(self, word: str) -> bool:
        current=self.root
        for i in word:
            if i not in current.child:
                return False
            current = current.child[i]
        return  current.isend
            
        

    def startsWith(self, prefix: str) -> bool:
        current=self.root
        for i in prefix:
            if i not in current.child:
                return False
            current=current.child[i]
        return True
 
        
