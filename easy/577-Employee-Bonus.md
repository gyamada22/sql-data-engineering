# 577. Employee Bonus

**Data:** 11/12/2025  
**Dificuldade:** Easy  
**Tópicos:** SQL, LEFT JOIN, NULL Handling  
**Link:** [Employee Bonus - LeetCode](https://leetcode.com/problems/employee-bonus/description/)

## Descrição
Encontre o nome dos funcionários que têm bônus menor que 1000 ou não têm bônus.

## Solução (SQL Server)

```sql
select e.name, b.bonus
from Employee e left join Bonus b on e.empid = b.empid
where b.bonus < 1000 or b.bonus is null
