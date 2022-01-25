# Python Data structure 
## Assignment 10.2, week 6

name = input('Enter a file name')

if len(name) < 1: name = "mbox-short.txt"

hand = open(name)

counts = dict()

for line in hand :

    line.rstrip()
    
    if line.startswith('From ') :
    
        wds = line.split()[5].split(':')
        
        counts[wds[0]] = counts.get(wds[0],0) + 1
    else :
        continue
        
lst = list()       

for wds,count in counts.items() :

    lst.append((wds,count))
    
lst = sorted(lst, reverse=True)

for wds,count in lst:

    print(wds,count)
       
