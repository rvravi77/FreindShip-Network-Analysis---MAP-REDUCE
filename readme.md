## Introduction
Map-Reduce  is a distributed and scalable way of extracting/mining required information from multiple datasets stored on multiple servers.

## TUTORIAL
Say, we have a text file and we want to count the frequency of occurrence of each word. The tutorial below explains how to solve this problem using a map-reduce algorithm.
1. </http://www.michael-noll.com/tutorials/writing-an-hadoop-mapreduce-program-in-python/>

2. </https://www.tutorialspoint.com/map_reduce/map_reduce_tutorial.pdf/>

## Data-set
Facebook network with ​3,892​ users. Please download the data “network.txt”.
### Data Description:
Each line represents an ​undirected edge​ between two users indicated by two node-ids separated by a comma. So, no pair of nodes are repeated in the file.

### Coding Language
Python3.6+

#### Sample code to read the files(in python)
```
fp=open(“network.txt”)
for line in fp:
    node1 , node2=line.split(“,”)
```

## Queries Solved :
1. Creating Network and counting all the users (node-ids) with at least 20 friends.
    **{Usefull in situations when we want to start advertisement campaign and send the advertisement to highly popular nodes (say with 20 freinds)}**
2. Finding The top-10 users (node-ids) with the highest number of friends.
    **{When a advertizer wants to reduce cost , so it sends to only top 10 users with highest number of nodes.In this way his advertisement will easily spread through Facebook shares, and you won’t have to pay anything for the paid ad campaign}**
3. Finding out the users who have friendship with at least one out of the top-10 users.
    **{Since the 2nd way will not benifit Facebook ,so to hide advertisement from the feed of the users who are connected to the top-10 users, so that even if the top-10 users share your ad, it won’t be visible to others and it won’t spread}**
4. Finding Top-10 US users with the highest number of friends in the US.
    ***{node-id between 0 and 999 are the only users from  the US}***
    **{When the advertizer got to know that the advertizement has not spread in US(where the most of the demand was).Due to previous strategy of advertizer the cost of advertisement is increased 10 times per user by Facebook, so advertizer deceides to send advertizement to top-10 US users with the highest number of friends in the US }**

## How to run and test your code:
Since we do not have access to a Hadoop cluster,it will be tested our on a Linux system as follows:
```python3 mapper.py | sort | python3 reducer.py > result.txt```

#### Note : Won't be using array or dictionaries of size greater than 10 as it will defer the purpose of implementing map-reduce.