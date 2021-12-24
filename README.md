# image-colorisation
Its done on kaggle dataset <br>
#### Kaggle Dataset <a href="https://www.kaggle.com/arnaud58/landscape-pictures">Link to Dataset</a>

***Clarity of the image is not good. But after running it on 100 epoches it will be clear <br>
You can find this notebook on my kaggle account***





def largestCycle(edges,ch):
    result = []
    visitedFrom = [-1] * len(edges)
    for startCell in range(0, len(edges)):
        cells = []
        cell = startCell
        while cell > -1 and visitedFrom[cell] == -1:
            visitedFrom[cell] = startCell
            cells.append(cell)
            cell = edges[cell]
        if cell > -1 and visitedFrom[cell] == startCell:
            cells_idx = cells.index(cell)
            cells = cells[cells_idx:]
            if len(cells) > len(result):
                result = cells
    if(len(result)>0):
        print(result[1])
    else:
        print(-1)

t = int(input())
for i in range(t):
    size = int(input())
    edges = []
    for j in range(size):
        k = int(input())
        edges.append(k)
    ch = int(input())
    largestCycle(edges,ch)
