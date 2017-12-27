# 探索阿德莱德及西安的未来气候发展趋势

这篇报告是优达学城数据分析纳米学位的第一个项目的作业。在这份报告中，我们将会通过分析1750年至2015年的气候数据，来探索澳大利亚阿德莱德和中国西安于全球气候变化的关系。首先我们会计算出1750年至2015年气温数据的**移动平均数**，然后再将它以可视化方式展现出来。最后根据数据的变化图提出四项观察分析。

## 气候数据获取及处理

1. 确定城市名

    首先我们通过SQL语句中的```LIKE```关键字模糊查询到了阿德莱德在我们的```city_list```中。

    ```sql
    SELECT *
    FROM city_list
    WHERE city LIKE 'Adelaide';
    ```

    然而当我用同样的SQL语句模糊查询西安的时候,系统却没有找到。

    ```sql
    SELECT *
    FROM city_list
    WHERE city LIKE 'XiAn';
    ```

    于是我列出了全部中国的城市，然后发现原来```WHERE```的查询是区分大小写的,西安正确的查询语句为```'Xian'```。

    ```sql
    SELECT *
    FROM city_list
    WHERE country LIKE 'China';
    ```

2. 导出气候数据

    通过下面的SQL语句查询出1750年至2015年全球的平均气温(ºC)
    ```sql
    SELECT *
    FROM global_data;
    ```

    通过下面的SQL语句查询出西安(Xian)和阿德莱德(Adelaide)的1820年至2013年的年平均气温(ºC)。

    ```sql
    SELECT *
    FROM city_data
    WHERE city = 'Xian';
    ```
    ```sql
    SELECT *
    FROM city_data
    WHERE city = 'Adelaide';
    ```

## 未来气候的分析