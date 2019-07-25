# GraphxBFS

This is a simple implementation of performing Breadth First Search using GraphX library in Apache Spark

#Requirements:

* Java - 1.7 / 1.8
* Scala - 2.10 / 2.11
* sbt - 0.13.8
* Apache Spark - 1.4.1 -- 1.5.1
* python - 2.7 ( tested on , should work on 3.x)


sbt default packaging will not work , as scopt will not be added to the jar.
Hence create a fat jar to include scopt

sbt
> assembly

```
Usage: <jar-file> [options]  
  
  -g <value> | --graphType <value>  
        Type of graph to be generated  
  -p <value> | --partitionStrategy <value>  
        partitionStrategy to be used  
  -v <value> | --numVertices <value>  
        Number of Vertices  
  -e <value> | --numEdges <value>  
        Number of Edges  
  -n <value> | --partitionCount <value>  
        Number of edge partitions to be made  
  -m <value> | --mu <value>  
        Mu value for graph generation  
  -s <value> | --sigma <value>  
        Sigma  value for graph generation  
  --seed <value>  
        Seed value for graph generation  
  -f <value> | --edgeListFile <value>  
        Edge List file path  
  --help  
        prints this usage text  

```

##Example Run

> java -jar target/scala-2.12/Graph-BFS-assembly-1.0-SNAPSHOT.jar -g "LogNormal" -v 65536 -e 16384 -n 4

#GraphType values  
* Star Graph   
* Log Normal graph - Taken out of pregel paper (https://kowshik.github.io/JPregel/pregel_paper.pdf)  
* RMAT graph - http://snap.stanford.edu/class/cs224w-readings/chakrabarti04rmat.pdf  
* EdgeList - Custom user defined edge list ( each line of format : srcId dstId)  
  
#Partition Strategies that can be used  
* RandomVertexCut  
* CanonicalRandomVertexCut  
* EdgePartition1D  
* EdgePartition2D  

  



