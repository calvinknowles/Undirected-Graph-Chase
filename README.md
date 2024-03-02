# Undirected-Graph-Chase
Independent project on cat and mouse game over an undirected graph following optimal game theory with exploration.

This document follows my experience throughout this project.

I first decided to attack this problem after seeing a Tom and Jerry game filter on TikTok. The premise is simple: on some given undirected graph, a cat and a mouse reside on a unique starting node where the cat must catch the mouse by ending up on the same node. The cat and mouse take turns moving from one node to another. 

The game can be challenging, but I wanted to take it further than just playing on TikTok. My goal is to build the game in Python, and then train A.I. to optimize the strategy for both the cat and the mouse. 

STEP ONE: Establish rules for the game.
1) On a player's turn (cat/mouse), they must move to a different node than the one they are currently on.
2) A player can only move to a node that is connected to the node they are currently standing on. i.e. there is a path between the start and finish node.
3) The cat wins the game if it can catch the mouse. i.e. ends up on the same node as the mouse.
4) The mouse wins the game if it can trap the cat in an infinite loop. i.e. there is no move the cat can make to force the mouse out of this loop.
5) Within the undirected graph, there must exist at least one loop players can traverse. 

STEP TWO: Determine how many rule-compliant and unique board combinations exist given n nodes.

We will first start with the base case and build up. Given the rules, we cannot have a 1-node or 2-node board for trivial reasons. Therefore, our base case is a 3-node board. For a 3-node board to be rule-compliant, there must be a path between every node. For simplicity, I will write out an adjacency list.

Node 1: {Node 2, Node 3},
Node 2: {Node 1, Node 3},
Node 3: {Node 1, Node 2}

To count the number of paths on the board

The maximum number of paths between n nodes is (n^2-n)/2
