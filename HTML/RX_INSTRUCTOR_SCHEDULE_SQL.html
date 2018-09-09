select * from (

with meetings as (
    select
      descr as title
    , meeting_time_start, meeting_time_end
    , start_dt, end_dt
    , mon, tues as tue, wed, thurs as thu, fri, sat, sun
    from ps_instr_week_schd
    where emplid = :1
)

, dates (dt) as (
    select min(start_dt) from meetings
    union all
    select dt +  1 day from dates
    where dt < (select max(end_dt) from meetings)
)

select
  a.title
, to_char(b.dt,'YYYY-MM-DD') || 'T' || to_char(meeting_time_start,'HH24:MI:SS') as "start"
, to_char(b.dt,'YYYY-MM-DD') || 'T' || to_char(meeting_time_end,'HH24:MI:SS') as "end"
from
  meetings a
, dates b
where b.dt between a.start_dt and a.end_dt
and (
    to_char(b.dt, 'dy') = 'mon' and a.mon = 'Y'
or  to_char(b.dt, 'dy') = 'tue' and a.tue = 'Y'
or  to_char(b.dt, 'dy') = 'wed' and a.wed = 'Y'
or  to_char(b.dt, 'dy') = 'thu' and a.thu = 'Y'
or  to_char(b.dt, 'dy') = 'fri' and a.fri = 'Y'
or  to_char(b.dt, 'dy') = 'sat' and a.sat = 'Y'
or  to_char(b.dt, 'dy') = 'sun' and a.sun = 'Y'
)
order by a.start_dt, a.title, b.dt

) x
