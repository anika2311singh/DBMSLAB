CREATE DATABASE insu;
USE insu;

CREATE TABLE PERSON( 
	driver_id varchar(20), 
	name varchar(20),
    address varchar(20),
    PRIMARY KEY(driver_id));

CREATE TABLE CAR(
      reg_no varchar(10),
      model varchar(10),
      year_manufacture INT,
      PRIMARY KEY(Reg_no)
);

CREATE TABLE ACCIDENT(
      report_number  INT,
      date_accident date,
      location varchar(20),
      PRIMARY KEY(report_number)
);

CREATE TABLE OWNS(
      driver_id varchar(10),
      reg_no varchar(10),
	  FOREIGN KEY(driver_id) REFERENCES PERSON(driver_id),
      FOREIGN KEY(reg_no) REFERENCES CAR(reg_no)
);

CREATE TABLE PARTICIPATED(
      driver_id varchar(10),
      reg_no varchar(10),
	  report_number  INT,
      damage_amount INT,
	  FOREIGN KEY(driver_id) REFERENCES PERSON(driver_id),
	  FOREIGN KEY(reg_no) REFERENCES CAR(reg_no),
       FOREIGN KEY(report_number) REFERENCES ACCIDENT(report_number)
 );  
 
 INSERT INTO PERSON VALUES('DR1','ARAVIND','CHINA'),('DR2','SIDDHARTH','JAPAN'),('DR3','ARADARTH','MEXICO');
 INSERT INTO CAR VALUES('R1','aaa',2002),('R2','bbb',2003),('R3','ccc',2004);
 INSERT INTO ACCIDENT VALUES(111,'2002-09-09','CHINA'),(222,'2008-07-09','JAPAN'),(333,'2002-08-09','MEXICO');
 INSERT INTO OWNS VALUES('DR1','R1'),('DR2','R2'),('DR3','R3');
 INSERT INTO PARTICIPATED VALUES('DR1','R1',111,52),('DR1','R1',222,65),('DR1','R1',333,12);
 
 select * from PARTICIPATED;
 
 update PARTICIPATED SET damage_amount=25000 WHERE reg_no='R1' AND report_number=111;
 
 select * from ACCIDENT;
 
 insert into ACCIDENT values('444','2020-02-20','AFGHANISTHAN');
 
select 	EXTRACT(YEAR FROM date_accident) as Year, count(*) as total
from ACCIDENT
where EXTRACT(YEAR FROM date_accident)=2002 
group by EXTRACT(YEAR FROM date_accident);

update CAR set model='aaa' WHERE reg_no='R2' OR reg_no='R3';
select * from CAR;

select model, count(*) as total
from CAR
where model='aaa' 
group by model;
