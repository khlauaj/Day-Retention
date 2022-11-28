# Day-Retention
SQL - check the user retention
--------------------------------------------------------------------------------------

select *
from gameplays

![image](https://user-images.githubusercontent.com/39978937/204186581-38cfcaef-6cc7-40b4-af75-67364349cdb3.png)


--------------------------------------------------------------------------------------

select *
from gameplays as g1
  left join gameplays as g2 on
    g1.user_id = g2.user_id
    and date(g1.created_at) = date(datetime(g2.created_at, '-1 day'))
group by 1
order by 1
limit 100;

![image](https://user-images.githubusercontent.com/39978937/204186908-df38e2f3-a922-47b1-98d0-a76972523aad.png)
