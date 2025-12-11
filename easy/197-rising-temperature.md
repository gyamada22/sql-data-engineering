# 197. Rising Temperature

**Data:** 11/12/2025  
**Dificuldade:** Easy  
**Tópicos:** SQL, Date Functions, Self Join  
**Link:** [Rising Temperature - LeetCode](https://leetcode.com/problems/rising-temperature/description/)

## Descrição
Escreva uma solução em SQL para encontrar todos os IDs dos registros onde a temperatura foi maior no dia seguinte.

## Solução (MySQL)

```sql
select id
from (
    select  id,
            temperature,
            recordDate,
            lag(temperature)over(order by recordDate) as tempp,
            lag(recordDate)over(order by recordDate) as datt
    from Weather
    )  as lagg
where temperature  > tempp and datediff(day,datt,recordDate) = 1
