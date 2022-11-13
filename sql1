create database relation;
use relation;

create table person(
driver_id varchar(20) primary key,
name varchar(20),
address varchar(20)

);

create table CAR(
reg_num varchar(20) primary key,
model varchar(20),
year int
);

show tables;
desc person;

create table owns(
driver_id varchar(20),
reg_no varchar(20),
primary key(driver_id,reg_no),
foreign key(driver_id) references person(driver_id) on delete cascade,
foreign key(reg_no) references car(reg_num) on delete cascade
);

create table accident(
report_num int primary key,
accident_date date,
location varchar(20)
);

create table participated(
driver_id varchar(20),
reg_num varchar(20),
report_num int,
damage_amount int,
primary key(driver_id,reg_num,report_num),
foreign key(driver_id) references person(driver_id),
foreign key(reg_num) references car(reg_num),
foreign key(report_num) references accident(report_num)
);

insert into accident 
values(11,'2003-01-01','Mysore road');
insert into accident 
values(12,'2004-02-02','South end');
insert into accident 
values(13,'2003-01-21','Bull temple road');
insert into accident 
values(14,'2003-01-01','Mysore road');
insert into accident 
values(15,'2004-03-05','Kanakpura road');

insert into person
values('a01','abc','bangalore');
insert into person
values('a02','sa','mysore');
insert into person
values('a03','a12','shirsi');

insert into car
values('KA052250','verna',2019);
insert into car
values('KA053408','benz',2022);
insert into car
values('KA095477','bucati',2015);

insert into owns
values('a01','KA052250');
insert into owns
values('a02','KA053408');
insert into owns
values('a03','KA095477');

insert into participated
values('a01','KA052250',11,10000);
insert into participated
values('a02','KA053408',12,50000);
insert into participated
values('a03','KA095477',13,25000);

update participated
set damage_amount = '75000'
where reg_num = 'KA053408'and report_num = 12;

select * from participated;

select count(distinct driver_id) as 'COUNT' from participated
where accident_date = '2003-01-01';

select * from participated 
order by damage_amount desc;
select avg(damage_amount) from participated;

select accident_date,location from accident;

select driver_id from participated
where damage_amount>10000;

select location from accident
where location like '%bull';

alter table accident(
add column accident_time int
);

alter table accident(
modify accident_date varchar(20)
);

select * from accident 
where report_num between 12 and 14;
