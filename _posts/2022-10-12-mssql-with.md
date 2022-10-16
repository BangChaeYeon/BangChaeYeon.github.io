---
title: MS-SQL WITH(작성중)
author: BCY
date: 2022-10-12 21:45:00 +0900
categories: [sql, mssql]
tags: [study]
render_with_liquid: false
---

> 해당 글은 SQL Server 2014 이후 버전을 기준으로 작성되었습니다.
{: .prompt-warning }

## 개요
MS-SQL에서는 WITH는 Transaction-SQL을 작성할 때 사용합니다.

Transaction은 데이터베이스 상에서 단일 또는 다중 활동을 수행하는 논리적 작업 단위입니다.

Transaction-SQL을 작성할 때는 등 다양한 구문을 사용할 수 있지만, 이번에는 WITH에 대해 중점적으로 알아보겠습니다.

WITH 구문은 크게 CTE, Table hints 방식으로 구분지어 확인할 수 있습니다.

## CTE(Common Table Expression)
WITH를 사용하여 테이블 결과를 임시로 확인할 수 있습니다.


```sql
-- CTE example
WITH TEST AS(
	SELECT 1 AS val FROM DUAL;
)
SELECT val FROM TEST; -- result: 1
```


## Table hints
FROM 구문 뒤에 WITH를 사용하여 TABLE HINTS로 사용할 수 있습니다.

Table hints 종류

| Index | Table hints | WITH 필요 여부 | 설명 | 기타 |
|---------|---------|---------|---------|---------|
|1| NOEXPAND |  |  |  |
|2| KEEPIDENTITY |  |  |  |
|3| KEEPDEFAULTS |  |  |  |
|4| FORCESEEK |  |  |  |
|5| FORCESCAN |  |  |  |
|6| HOLDLOCK |  |  |  |
|7| IGNORE_CONSTRAINTS |  |  |  |
|8| IGNORE_TRIGGERS |  |  |  |
|9| NOLOCK |  |  |  |
|10| NOWAIT |  |  |  |
|11| PAGLOCK |  |  |  |
|12| READCOMMITTED |  |  |  |
|13| READCOMMITTEDLOCK |  |  |  |
|14| READPAST |  |  |  |
|15| READUNCOMMITTED |  |  |  |
|16| REPEATABLEREAD |  |  |  |
|17| ROWLOCK |  |  |  |
|18| SNAPSHOT |  |  |  |
|19| TABLOCK |  |  |  |
|20| TABLOCKX |  |  |  |
|21| UPDLOCK |  |  |  |
|22| XLOCK |  |  |  |


```sql
-- table hints example
SELECT 1 FROM DUAL WITH (NOLOCK);
```

<br>

> 출처
> * [https://www.sqlshack.com/transactions-in-sql-server-for-beginners/](https://www.sqlshack.com/transactions-in-sql-server-for-beginners/)
>* [https://learn.microsoft.com/ko-kr/sql/t-sql/queries/with-common-table-expression-transact-sql?view=sql-server-ver16](https://learn.microsoft.com/ko-kr/sql/t-sql/queries/with-common-table-expression-transact-sql?view=sql-server-ver16)
>* [https://learn.microsoft.com/ko-kr/sql/t-sql/queries/hints-transact-sql-table?view=sql-server-ver16](https://learn.microsoft.com/ko-kr/sql/t-sql/queries/hints-transact-sql-table?view=sql-server-ver16)
