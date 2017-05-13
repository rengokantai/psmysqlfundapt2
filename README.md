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
