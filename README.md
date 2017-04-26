Apache Phoenix on Docker
==============

A Docker image to quick start [Apache Phoenix](http://phoenix.apache.org/) on [Apache HBase](https://hbase.apache.org/)
to provide an SQL interface. This image uses the Phoenix Avatica queryserver to allow thin clients to communicate via REST requests over wire protocol.

Apache Phoenix is a SQL skin over HBase delivered as a client-embedded JDBC driver targeting low latency queries over HBase data. Apache Phoenix takes your SQL query, compiles it into a series of HBase scans, and orchestrates the running of those scans to produce regular JDBC result sets. The table metadata is stored in an HBase table and versioned, such that snapshot queries over prior versions will automatically use the correct schema. Direct use of the HBase API, along with coprocessors and custom filters, results in performance on the order of milliseconds for small queries, or seconds for tens of millions of rows.

###Versions
Apache Hadoop - 2.7.2
Apache HBase - 1.2.5
Apache Phoenix - 4.10.0

###Launch
The queryserver can be accessed via the host ip and the port 8765.

####Foreground
`docker run -it --name hp -p 8765:8765 8765:8765 –p 2181:2181 -p 60010:60010 -p 60000:60000 -p 60020:60020 -p 60030:60030 avapno/apache-phoenix`

####Background
`docker run -d --name hp -p 8765:8765 –p 2181:2181 -p 60010:60010 -p 60000:60000 -p 60020:60020 -p 60030:60030 avapno/apache-phoenix`

###sqlline
`docker exec -it phoenix -sqlline`
