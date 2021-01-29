# DataSet



------

## DataFrames are actually Datasets.

```scala
type DataFrame = Dataset[Row]
```



###### Datasets can be considered as typed distributed colletion of data

###### Dataset API unifies the DataFrame and RDD APIs: typesafety !

###### Schemas and Encoders core part of Datasets.



------

## Common Transformations on Datasets

###### map, flatMap, distinct ...

###### filter(pred: T => Boolean): Dataset[T]

```scala
/*SQL*/
popleDs.filter("age > 15")

/*The following are equivalent:*/
peopleDs.filter($"age" > 15)
peopleDs.where($"age" > 15)
```



------

## Grouped Operations on Datasets: How to group & aggregate on Datasets?

###### Using the General agg Operation



###### agg[U] (col: TypedColumn[v, u]): Dataset[(K, U)]

```scala
someDS.agg(avg($"column").as[Double])

ds.agg(max($"age"), avg($"salary"))
ds.groupBy().agg(max($"age"), avg($"salary"))
```



------

## reduceByKey with an Aggregator

###### implementing the aggregation part of reduceByKey operation with an Aggregator.



```scala
val keyValues =
	List((3, "Me"), (1, "Thi"), (2, "Se"), (3, "ssa"),
       (1,"sIsA"), (3, "ge:"), (3,"-)"), (2, "cre"), (2, "t"))

val keyValuesDS = keyValues.toDS
```



```scala
val strConcat = new Aggregator[(Int, String), String, String]{
  	/*what should Aggregator's type parameters be?*/
  def zero: String= ""
  def reduce(b: String, a: (Int, String)): String = b + a._2
  /*what should the rest of types be?*/
  def merge(bl : String, b2: String) : String = bl + b2
  def finish(r: String) : String = r /*implement the methods*/
  override def bufferEncoder: Encoder[String] = Encoders.STRING
  override def outputEncoder: Encoder[String] = Encoders.STRING
  /*without encoder, this causes errors. here telling Spark
  which Encoders needed*/
}.toColumn /*pass it to your aggregator*/
```

```scala
keyValuesDS.groupByKey(pair => pair._1).agg(strConcat.as[String]).show
```



------

## Encoders: convert data between JVM objects and Spark SQL's. They're required by all Datasets.

###### Two ways of Encoders

###### : Automatically via implicits from a SparkSession. (general)

###### 	: Explicitly via org.apache.spark.sql.Encoder







> ###### from Big data analysis with Scala and Spark
>
> 