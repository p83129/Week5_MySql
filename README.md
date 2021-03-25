# Week5_MySql
#要求三

#3-1

insert into user(name, username, password)
values('test1name', 'ply', 'ply');
![1616590960689](https://user-images.githubusercontent.com/77446871/112324698-0477d780-8cee-11eb-9800-32ff89d3ddd9.jpg)

insert into user(name, username, password)
values('test2name', 'test2ply', 'test2ply');

insert into user(name, username, password)
values('test3name', 'test3ply', 'test3ply');

insert into user(name, username, password)
values('test4name', 'test4ply', 'test4ply');

insert into user(name, username, password)
values('test5name', 'test5ply', 'test5ply');
![1616591166687](https://user-images.githubusercontent.com/77446871/112324858-27a28700-8cee-11eb-84f0-5f075c66242e.jpg)

#3-2
select * from user;

![1616591354849](https://user-images.githubusercontent.com/77446871/112324979-443ebf00-8cee-11eb-83ea-4d5ddb5f66ea.jpg)

#3-3
select count(*) from user;

![1616591493078](https://user-images.githubusercontent.com/77446871/112325173-6b958c00-8cee-11eb-8e41-c98d8e42b12c.jpg)

#3-4
select * from user 
order by time desc;
![1616591684082](https://user-images.githubusercontent.com/77446871/112325303-85cf6a00-8cee-11eb-8049-f719d025f844.jpg)

#3-5
select * from user order by time desc limit 1,3;
![1616652184385](https://user-images.githubusercontent.com/77446871/112426688-54e54880-8d73-11eb-84ac-7402c558ab60.jpg)

#3-6
select * from user
where username='ply';
![1616592068453](https://user-images.githubusercontent.com/77446871/112325833-fb3b3a80-8cee-11eb-810e-07f13666086b.jpg)

#3-7
select * from user
where username='ply'and password='ply';
![1616592138592](https://user-images.githubusercontent.com/77446871/112326023-20c84400-8cef-11eb-8314-6d9526b4aded.jpg)

#3-8
update user
set name='丁滿'
where username='ply';
![1616592310409](https://user-images.githubusercontent.com/77446871/112326130-39d0f500-8cef-11eb-9552-26750509d4fb.jpg)

#3-9
delete from user;

![1616592535010](https://user-images.githubusercontent.com/77446871/112326243-51a87900-8cef-11eb-89de-6bcc55e62274.jpg)

#要求四

先建立message

create table message (
id bigint unsigned not null auto_increment primary key,
user_id bigint not null,
content varchar(255) not null,
time datetime not null default current_timestamp
);

再建立user兩筆資料

insert into user(name, username, password)
values('test1name', 'ply', 'ply');

insert into user(name, username, password)
values('test2name', 'ply2', 'ply2');

建立message三筆資料

insert into message(user_id, content)
values('6', '哈囉~你好');

insert into message(user_id, content)
values('6', '過得如何~');

insert into message(user_id, content)
values('7', '還不錯!!');

#4-1
select a.name, b.content 
  from user a
	left join message b on(a.id = b.user_id);
![1616594298318](https://user-images.githubusercontent.com/77446871/112327336-4d309000-8cf0-11eb-8983-ed869b6ebc02.jpg)

#4-2
select a.name, b.content 
from user a
	left join message b on(a.id = b.user_id)
where a.username='ply';
![1616594598452](https://user-images.githubusercontent.com/77446871/112327405-5f123300-8cf0-11eb-9057-24a300db35f4.jpg)


  





