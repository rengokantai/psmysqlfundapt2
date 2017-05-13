# psmysqlfundapt2

### Demo: Before Trigger
```
delimiter //
create trigger language_Before_Insert
before insert on language
for each row
begin
set new.name = concat(upper(substring(new.name,1,1)),
lower(substring(new.name from 2)));
end //
delimiter;
```


### Demo: Single Time Event
```
delimiter//
create event one_time_event
on scedule at now() + internal 1 minute
do begin
  insert into event_audit(last_update)
  values(now());
end//
delimiter;
```
