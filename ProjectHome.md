On Intel Xeon E5645 CPU **2**

Put(key,value): Over 90000 queries per second.
Get(key): Over 100000 queries per second.

一、BigSea 的 普通功能：

二、BigSea 的 LIST 功能：
1、LIST PUT 写入：
http://115.182.33.223:55521/test/?opt=listput&username=zhangyan&password=y.zhang.yijia&value=内容

2、LIST GET 获取：
http://115.182.33.223:55521/test/?opt=listget&start=0&limit=10&order=desc

start=0&limit=10 相当于 MySQL SQL 查询的 limit 0,10
order=desc 为排序方式，asc 为升序，desc 为降序

返回示例（JSON）：
{
> "count":        3,
> "data": [{
> > "listid":       1,
> > "value":        "内容"
> > }, {
> > > "listid":       2,
> > > "value":        "内容"

> > }, {
> > > "listid":       3,
> > > "value":        "内容"

> > }]
}

数据为空时，返回（JSON）：


{

> "count":        0,
> "data": [.md](.md)
}

3、LIST DELETE 删除：

http://115.182.33.223:55521/test/?opt=listdelete&username=zhangyan&password=y.zhang.yijia&listid=2
listid=2为要删除的list id值

4、PUT 修改 LIST 中的单条记录（相当于UPDATE）


http://115.182.33.223:55521/test/~data~3?opt=put&username=zhangyan&password=y.zhang.yijia&value=新内容


come soon...