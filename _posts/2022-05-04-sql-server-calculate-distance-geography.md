---
layout: post
title:  "How to calculate distance between two places in SQL Sever!"
tags: "sql-server geography maps"
category: database-tricks
author: Sudarshan Kadam
excerpt_separator: <!--more-->
---

You can easily calculate straight line distance between two locations using SQL Server if you have latitude and longitude of both locations.

Here is a simple example:

{% highlight sql %}
DECLARE @PointA geography = geography::Point(33.016329,100.394447, 4326) ---Rotan, TX 79546
,@PointB geography = geography::Point(32.681059,98.303269,4326) ---Palo Pinto, TX 76484

SELECT CAST(@PointB.STDistance(@PointA)/1609.344 AS decimal(8,2)) AS distance_in_miles

Output:
distance_in_miles
123.81
{% endhighlight %}

You can also do this with single line instead of decalring variables. This way you can use this in select queries directly on multiple rows.

{% highlight sql %}
SELECT CAST(GEOGRAPHY::Point(33.016329,100.394447, 4326).STDistance(GEOGRAPHY::Point(32.681059,98.303269,4326))/ 1609.344 AS DECIMAL(8, 1)) distance_in_miles
{% endhighlight %}

For more inforamtion and deep dive, visit:
https://docs.microsoft.com/en-us/sql/t-sql/spatial-geography/stdistance-geography-data-type?view=sql-server-ver15
<!--more-->

What is 4326 in the above function? It is called SRID. Ideally you shouldn't need to change this for common uses of geography functions.
>The spatial reference ID (SRID) is an identifier specifying which ellipsoidal coordinate system the geography instance is represented in. Two geography instances with different SRIDs cannot be compared.

Read more here: https://docs.microsoft.com/en-us/sql/relational-databases/spatial/create-construct-and-query-geography-instances?view=sql-server-ver16#supportedsrid
