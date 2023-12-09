# Sql_WorkShop

Sql Commands


create database firstDb; --Burada database oluşturulmaktadır

use firstDb --Bu komut ile bundan sonra yazılacak olan komutların nerede kullanılacağı seçilmektedir.

create table firstTable (
	object1 varchar(10),
	object2 varchar(20),
	object3 varchar(30),
)--Burada oluşturulan database için tablo oluşturulması yapılmaktadır.

alter table firstTable add firstColumn tinyint --Burada ise belirtilen tabloya field eklemesi yapılmaktadır.
alter table firstTable add secondColumn type,thirdColumn type --burada ise alter komutu ile birden fazla field eklemesi yapılmaktadır.
alter table firstTable alter column object1 type --burada ise var olan bir field için tip değişikliği veya güncellemesi yapılmaktadır.

drop table firstTable --bu komut ile ilgili tablo silinir.
alter table firstTable drop column object1 --burada belirtilen tablodan ilgili field silinmektedir.
l
truncate table ogr --belirtlilen tablo içerisindeki bütün verileri silme işlemi yapar.

select * from firstTable -- burada belirtilen tablo içerisindeki bütün verileri çağırılmaktadır.
select object1,object2 from firstTable --beliritilen tablodan belirtilen kolonları getirmektedir.


select * from firstTable WHERE object1 = "deneme" --where içerisindeki koşula göre sorgu çalıştırır.
select * from firstTable WHERE object2 > 40 --aynı şekilde belirtilen koşul ile sorgu çalıştırmaktadır.
select * from firstTable where object1 > 20 AND object3 < 40 --2 farklı koşula göre sorgu çalıştıran yapıdır.Bu sayı artabilir.Her iki kuaralda uyulması gerekmektedir.
select * from firstTable where object1 > 20 OR object3 < 40 --tek bir koşula uyan verileride getirebilir.1-0 yada 1-1

select * from firstTable where object1 in(10,20,30) -- burada belirtilen kısma göre parantez içerisindeki değerler sağlanıyor ise bu değerler döndürülür.

select - from firstTable where object2 like '%a%' and object1 in(10,20) --burada object2 içerisinde a harfi geçen ve object1 içerisinde 10 ve 20 bulunan ifadeleri getir.

//'a%' a ile başlayan,'%a' a ile biten,'%a%'içerisinde a bulunan ifadelerdir.

insert into AllMail values(9,'fayik.veznedaroglu@dedas.com.tr',1) --Bu komut sayesinde AllMail Tablosuna ekleme işlemi yapılmaktadır.
insert INTO AllMail (SapDataId,MailAddress) values (199,'deneme@dedas.com.tr')--Bu komut sayesinde ise satırlarda seçilen değerlere göre ekleme işlemi yapılmaktadır.

update AllMail set SapDataId = '200' where SapDataId  = '199' --Burada güncelleme işlemi yapılmaktadır.

update AllMail set SapDataId = '205' , MailAddress = 'deneme5@dedas.com.tr' where SapDataId = 200 -- aynı satırda birden fazla değişken ismini değiştirmek için kullanılmaktadır.

delete from AllMail where SapDataId = 203 --203 numaralı SapDataId'ye sahip kaydı silmek için kullanılmaktadır.
select * from MyExampleTable where ExistDate BETWEEN '2023-11-20' AND '2023-11-24' -- bU KOMUT İLE belirlenen satır için aralık değeri baz alınmaktadır.


										Other Sql Commands
			
insert into AllMail values(9,'fayik.veznedaroglu@dedas.com.tr',1)
select * from AllMail where SAPDataId = 9
select * from AllMail where MailAddress = 'deneme@dedas.com.tr'
insert INTO AllMail (SapDataId,MailAddress) values (199,'deneme@dedas.com.tr')
update AllMail set SapDataId = '200' where SapDataId  = '199' 


insert into AllMail (SapDataId,MailAddress) values(202,'ahmet.lala@dedas.com.tr')


update AllMail set SAPDataId = 202,MailAddress = 'ahmet.haris.lala@dedas.com.tr' where SAPDataId  = '202'
select * from AllMail where SAPDataId = 202

delete from AllMail where SAPDataId = 202
select * from AllMail WHERE SAPDataId = 202


insert into AllMail (SapDataId,MailAddress) values (1000, 'test_dedas@dedas.com.tr' ) 
select * from AllMail where SapDataId = 1000
Update AllMail set Statu = 0 where SapDataId = 1000
insert into AllMail (SapDataId,MailAddress,Statu) values (1001,'test2Dedas@dedas.com.tr',1) 
select * from AllMail where SapDataId = 1001
update AllMail set MailAddress = 'seriously@dedas.com.tr' , Statu = 0 where Id = 3573

select * from AllMail am where MailAddress = 'seriously@dedas.com.tr'

select * from AllMail where SAPDataId = 1001

delete from AllMail where SAPDataId = 1001

select * from AllMail where SAPDataId = 1001
insert into AllMail (SAPDataId,MailAddress,Statu) values (7279,'naci.demir@dedas.com.tr',1)

select * from AllMail am where MailAddress like ('Naci%')

select DISTINCT MailAddress from AllMail am where MailAddress ='naci.demir@dedas.com.tr'
select Count(*) from AllMail am2 
select * from AllMail am3 where MailAddress = 'naci.demir@dedas.com.tr'

create table MyExampleTable(
	BookId Int,
	BookName VARCHAR(30) ,
	Author VARCHAR(15) ,

);

alter table MyExampleTable add BookPrice int
alter table MyExampleTable add ExistDate DATE

insert into MyExampleTable (BookId,BookName,Author) values (1,'İktidar','Robert Greene')

update MyExampleTable set BookPrice = 20 where BookId = 1
select * from MyExampleTable where Author like ('rOber%')
select * from MyExampleTable met 

insert into MyExampleTable (BookId,BookName,Author,BookPrice) values (2,'Lider Sensin','Levent Hancı',15)

select * from MyExampleTable met order by BookPrice asc
select * from MyExampleTable met order by BookPrice desc
select * from MyExampleTable met2 order by BookName

select BookName as 'Yazar' from MyExampleTable met 

select * from AllMail am 
select SAPDataId  as 'SapIdentity' from AllMail am2 order by SAPDataId asc 

select BookId,BookName,Author,BookPrice,BookPrice*2 as 'NewBookPrice' from MyExampleTable met  
select BookId,BookName,BookPrice,BookPrice+5 as 'NewBookPrice' from MyExampleTable met2 
SELECT * from MyExampleTable met3 order by ExistDate asc
insert into MyExampleTable (ExistDate) values ('2023-12-02')
delete from MyExampleTable where ExistDate = '2023-12-02'
update MyExampleTable set ExistDate = '2023-11-23' where BookPrice = 15
select * from MyExampleTable where ExistDate BETWEEN '2023-11-20' AND '2023-11-24'
drop table MyRepeatExampleTable
create table MyRepeatExampleTable (

	StudentNo int not null primary key,
	StudentName varchar(20),
	StudentSurname varchar(20),
	StudentAddress varchar(20),
	StudentDistrict varchar(25) default 'Yenisehir',
	StudentExam1 tinyint check (StudentExam1 > 0 and StudentExam1 <101),
	StudentExam2 int,
	Constraint CheckExam check (StudentExam2 >= 0 and StudentExam2 <= 100),
	StudentClub nvarchar(30),
	Constraint CheckStudentClub check (StudentClub in ('Sport','Environment','Technology'))

)

alter table MyRepeatExampleTable add StudentClass varchar(20)
alter table MyRepeatExampleTable add Discontunity int 
alter table MyRepeatExampleTable add IsItSucessStudent bit 
alter table MyRepeatExampleTable add StudentWeight int
alter table MyRepeatExampleTable add StudentHeight int,StudentDepartment nvarchar(30)
alter table MyRepeatExampleTable drop column StudentHeight


insert into MyRepeatExampleTable (StudentNo,StudentName,StudentSurname,StudentAddress,StudentExam1,StudentExam2,StudentClub,Discontunity,IsItSucessStudent,StudentWeight,StudentHeight,StudentDepartment,StudentClass) 
values (2,'fayik','veznedaroglu','Usa New York',60,100,'Environment',20,1,172,70,'17','17')

insert into MyRepeatExampleTable (StudentNo,StudentName,StudentSurname,StudentAddress,StudentExam1,StudentExam2,StudentClub,Discontunity,IsItSucessStudent,StudentWeight,StudentHeight,StudentDepartment,StudentClass) 
values (3,'Elon','Musk','Usa,Chicago',70,100,'Technology',20,1,172,70,'17','17')

update MyRepeatExampleTable set StudentDepartment='Software' where StudentNo = 2

update MyRepeatExampleTable set StudentDepartment='AirShip' where StudentNo = 3
select * from MyRepeatExampleTable mret 
select * from MyRepeatExampleTable mret2 where StudentSurname like ('mu%')

TRUNCATE  table MyRepeatExampleTable 

alter table MyRepeatExampleTable drop column StudentClass

select cast(StudentClass as text) from MyRepeatExampleTable

select MyRepeatExampleTable.StudentName , MyExampleTable.BookName tr from MyRepeatExampleTable,MyExampleTable --Burada görüldüğü üzere iki farklı tablo ile genel bir işlem yapılmaktadır.

select * from MyExampleTable met 
select * from MyExampleTable where Author like 'r%'


select 20+5 as 'Toplam'

select 20-5 as 'Fark'

select * from MyExampleTable met 

select BookName,Author,BookPrice,BookPrice * 2 as 'NewBookPrice' from MyExampleTable met 

select SUBSTRING(BookName,0,6) from MyExampleTable met  --Burada BookName için 0.indeksten 6.indeks'e kadar olan kısmı almaktadır.

select RIGHT (BookName,2) from MyExampleTable met --Kolonlardaki field'lar için en sağ taraftan 2 harfi alıp ilerletmektedir.
select Left (BookName,3) from MyExampleTable met2 --Kolonlardaki fieldlar için en sol taraftan değer alarak kaç adet girilmişse o kadar indisi alıp yazdırma işlemi yapmaktadır.


select UPPER(BookName) from MyExampleTable met --İlgili field için Normalizasyon sağlamaktadır.Bütün verileri büyük harfe çevirmektedir.
select LOWER(BookName) from MyExampleTable met2  

select BookName,LEN(BookName) from MyExampleTable met --İlgili field için bütün değerlerin uzunluğunu bulmaya yarayan fonksiyındur.Len



select abs(BookPrice) from MyExampleTable met --Buradaki abs() negatif değerleri mutlak pozitif hale getiermektedir.

select sum(BookPrice) from MyExampleTable met 

select AVG(BookPrice) from MyExampleTable met 

SELECT max(BookPrice) from MyExampleTable met 
select min(BookPrice) from MyExampleTable met2 

select datepart(YEAR,GETDATE()) as 'Year' ,datepart(MONTH,GETDATE()) as 'Month' ,datepart(DAY,GETDATE()) as 'Day',datepart(WEEK,GETDATE()) as 'Week' ,datepart(HOUR,GETDATE()) as 'Hour'
select datepart(MONTH,GETDATE()) as 'Month'
select datepart(DAY,GETDATE()) as 'Day'
SELECT datepart(WEEK,GETDATE()) AS 'Week'
select datepart(HOUR,GETDATE()) as 'Hour'

select datepart(YEAR,GETDATE())-2020 


select Author,count(BookName) as 'Alias' from MyBookStoreHouse mbsh group by Author --Burada gruplama yapılmaktadır.Auhtor'u aynı olan kitaplar için gruplandırma yapılmaktadır.Ve sayma işlemi

select ExistYear,Count(BookName) as 'BookCounter' from MyBookStoreHouse mbsh group by ExistYear order by ExistYear desc --Buda kitapların çıkış yılına göre sıralama yapmaktadır.


select Author,Sum(BookPrice) as 'Total Book Price' from MyBookStoreHouse mbsh group by Author --Gruplandırma yapılarak total'de kitap fiyatlarının toplamları bulunmaktadır


select BookPrice,count(Quantity) as 'BookCounter' from MyBookStoreHouse mbsh where BookPrice > 9 group by BookPrice --Burada Kitap Fiyatı 9'dan büyük olanları ve fiyatı aynı olanları grupla anlamına gelmektedir.


DECLARE @myExampleNumber as int = 20,	@mySecondExampleNumber as int = 30 --Burada declare etme işlemi gerçekleştirilir ve ilgili değişkenlere ilgili atamalar gerçekleşir


declare @myExampleNumber2 as int = 45 --Burada değişken ataması yapılmaktador.@myExampleNumber2 değeri için 45 ataması yapılmıştır.



select Author,Count(BookName) as 'Counter' , Sum(BookPrice) as 'Book Price Sum' from MyBookStoreHouse mbsh group by Author having (sum(BookPrice)) >= 55 --Buradaki Having Kullanımı Group By ifadesi ile kullanılmak zorundadır.Ve Group By deyimine koşul anlamı katmaktadır


select * from MyBookStoreHouse mbsh left join MyExampleTable met on mbsh.BookId = met.BookId --bu join operasyonunda sol tarafta joinlenen ifade için joinlenen diğer ifade için ortak kümede birleşen bütün ifadeleri toplan ancak soldaki tablodakilerin hepsini getirir ve ortak kümede buluşmayan elemanları null olarak atamasını yapılmaktadır.

select * from MyExampleTable met2 right join MyExampleTable met3 on met2.BookId = met3.BookId 


select BookName from MyBookStoreHouse mbsh union select BookName from MyExampleTable met --Burada union keyword kullanılarak her iki tablo içerisinde BookName'lere göre filtreleme yapmaktayız aynı zamanda tekrar eden ifadeleri sorgu geri dönüşünde yok sayılmaktadır.

select BookName from MyBookStoreHouse mbsh union all select BookName from MyExampleTable met --Burada union'dan farklı olarak bütün kayıtları getirilmektedir.


select * from MyBookStoreHouse mbsh4 where BookId = (select BookId from MyExampleTable met where BookId = 3) --Burada ise alt sorgu olarak kullanılan bir yapı gözükmektedir.Parantez içerisinden geri dönen değer subQuery için value değer taşımaktadır ve bu değere göre işlem yapılmaktadır.


rollback -- rollback ifadesi transction içerisinde kullanıldığı zaman anlam kazanmaktadır.Yapılan herhangi bir değişikliği geri almak için kullanılmaktadır

declare @sayi1 int = 1,@sayi2 int = 2,@sayi3 int = 3,@sayi4 int = 4,@toplam int
set @sayi2 = 10
set @toplam = @sayi1+@sayi2+@sayi3+@sayi4
print(cast(@toplam as varchar(10))) --Declare ifadesi ile bir toplama işlemi görünmektedir.

---------------------------------------------
declare @newTable table (
	field1 int,
	field2 int,
	field3 varchar(15),
	field4 varchar(15)
)
insert into @newTable  values (10,20,'field3','field4') --Burada ise newTable adı verilen bir declare oluşturulmaktadır ve ekleme işlemi yapılmaktadır.

delete from @newTable2
output deleted.tablefield3 --Burada yapılan silme işlemi baz alınır ve listeleme işlemi yapılır.
-------------------------------------------
declare @decision int

select @decision = 10

if (@decision >= 10 )
begin
	print 'thats correct'
end
else 
begin 
	print 'that is not correct'
end --Burada ise if ve else ifadelerinin kullanımını görmekteyiz diğer karar yapılarından farklı olarak yalnızca syntax farklılığı bulunmaktadır.


declare @newVariable Int
------------------------------

select BookName ,
	CASE 
		WHEN BookPrice > 10 THEN 'Book price greater than 10'
		WHEN BookPrice = 10 THEN 'Book price equals 10'
		WHEN BookPrice < 10 THEN 'Book price smaller than 10'
	END as 'Description'
	


from MyBookStoreHouse mbsh 

--Yukarıda ise Switch-case ifadesi kullanılmaktadır genel tanımla benzerlik göstermektedir.
-----------------------------------

declare @incrementValue int

set @incrementValue = 10

WHILE (@incrementValue < 0) 
BEGIN 
	print 'increment value is not smaller than 0'
END

--Dİğer programlama dillerinden hakim olunan while ifadesidir.
--------------------------------------
create procedure WinnerEveryDay (@resultText varchar(20),@numberResult1 int,@numberResult2 int,@finishText varchar(20) output)

as 

set @finishText = @resultText + cast(@numberResult1 as varchar(15)) + cast(@numberResult2 as varchar(20))



declare @field1 varchar(200) = 'I always winner for this life',@field2 int = 20,@field3 int = 30,@resultField varchar(20) 
exec WinnerEveryDay @field1,@field2,@field3,@resultField output
print @resultField
--Yukarıda declare olmuş bir prosedür ve exec ile aşağıda çağırılan  prosedür bulunmaktadır.
------------------------------------------
create procedure CalcAverage (@number1 int,@number2 int,@average int output)
as 
set @average = (@number1 + @number2)/2


declare @number1 int = 10,@number2 int = 20,@result int,@tempValue int
exec CalcAverage @number1,@number2,@result output
set @tempValue = @result
print @tempValue 
--Yukarıdakide bir prosedür örneğidir.
-------------------------------------------
create function UpperCase(@gelendeger varchar(20))
returns varchar(10)
as
begin
	return upper(@gelendeger)

end
select dbo.UpperCase(BookName) from MyBookStoreHouse
--Yukarıda bir fonksiyon oluşturulup kullanımı gösterilmiştir.
------------------------------------------------
create function MyMathFunction(@mathout int)
returns int
as
begin
	return @mathout - (@mathout*10)/100
end

select BookPrice from MyBookStoreHouse
select dbo.MyMathFunction(BookPrice) from MyBookStoreHouse
--Yukarıda custom bir fonksiyon yazılmıştır ve bu fonksiyon içerisine gönderilen değer'e göre yüzdelik hesabı yaparak dışarı çıkış vermektedir.
------------------------------------------------
create trigger MySecondTrigger
on MyBookStoreHouse

after insert,update
as	
begin
	select 'Update process is success'
end
insert into MyBookStoreHouse values (19,'ForMySecondTrigger',15,'Martin Eden',20,'1905-08-20')
select * from MyBookStoreHouse mbsh 
--Yukarıda trigger oluşturulmuştur ve ekleme,güncelleme gibi operasyonlarda trigger olarak yazdırma işlemi yapılmaktadır.
------------------------------------------------
create trigger MythirdTrigger --Burayı dene
ON MyBookStoreHouse
after UPDATE 
as
begin
	update Counter set tempCounter = tempCounter+1
end
--Yukarıda update trigger'ı bulunmaktadır.Eğer ilgili tabloda güncelleme işlemi yapılırsa hemen sonrasında trigger tetiklenecek ve Counter tablosundaki gerekli değşikliği yapacaktır.
------------------------------------------------
create trigger InsteadOfTrigger 
on MyBookStoreHouse
instead of delete
AS 
BEGIN 
	select 'this trigger for insteadof'
END

delete from MyBookStoreHouse where BookId = 20
--Yukarıdaki trigger silme işlemi yapıldığı zaman tabloya yansıtmaz yalnızca trigger içeriisndeki komutu gerçekleştirir.
--------------------------------------------------------
create trigger MyInsteadOfTrigger
	on MyBookStoreHouse
	instead of DELETE 
	as 'TİTLE'
	begin
		select 'you want delete this item but you have instead of trigger'
	end
	
	delete from MyBookStoreHouse where BookId = 10	
--Yukarıda görüldüğü üzere instead of uygulanarak yalnızca select ile sorgu işlemi gerçekleştirildi.
------------------------------------------------------	
	
	create trigger MyLastInsteadOfTrigger
	on MyBookStoreHouse
	instead of insert,update
	as 
	begin
		update MyBookStoreHouse set BookName = 'Nasıl Büyür' where BookId = 12		
	end
	
	update MyBookStoreHouse set BookName = 'Deneme' where BookId = 12	
--Yukarıdaki örnekte görüldüğü üzere ezme işlemi gerçekleştirdik ve kitap ismini Deneme yerine Nasıl Büyür olarak yazdırmış olduk.
---------------------------------------------------
create table Products(
	ProductId int primary key,
	ProductName varchar(255),
	UnitPrice Decimal(10,2)

)
CREATE TABLE OrderDetails (
    OrderDetailID INT PRIMARY KEY,
    OrderID INT,
    ProductID INT,
    Quantity INT,
    Price DECIMAL(10, 2),
    FOREIGN KEY (ProductID) REFERENCES Products(ProductID),

);
--Yukarıda 1'e çok ilişki ile oluşturulmuş tablolar mevcuttur.
-----------------------------------------------------
create table Products(
	ProductId int primary key,
	ProductName varchar(255),
	ProductDescription varchar(255),
	UnitPrice decimal(10,2)
)

create table Orders(
	OrderId int primary key,
	ProductId int,
	Quantity int,
	Foreign key (ProductId) references Products(ProductId)
)

create table OrderTotals(
	OrderTotalId int primary key,
	OrderId int,
	OrderTotalPrice decimal(10,2)
	Foreign Key (OrderId) references Orders(OrderId) 

)

insert into Products values (1,'Lenovo Loq','This super mechanics laptop',39999)

create trigger AddOrder
on Orders 
after insert
as
begin
	declare @orderId int,@totalPrice decimal(10,2)
	select @orderId = OrderId from inserted
	set @totalPrice = dbo.CalculateAndInsertTotalOrderPrice(@orderId)
	insert into OrderTotals values (1,@orderId,@totalPrice)
end

create function CalculateAndInsertTotalOrderPrice(@orderId int)
returns decimal(10,2)
as
begin
	declare @total_order_price decimal(10,2)
	select @total_order_price = Sum(p.UnitPrice * o.Quantity) from Products p inner join Orders o on p.ProductId = o.ProductId
	return @total_order_price
end

select * from Orders
select * from Products

insert into Orders values (1,1,3)
select * from OrderTotals
--Yukarıda mükemmel bir trigger ve function kullanılarak Order eklenince tetiklenip toplam değeri OrderTotals tablosuna yazdıran bir prosedür mevcuttur.
----------------------------------------------------------------------------
create table Employees(
	EmployeeId int primary key,
	EmployeeName varchar(255),
	EmployeeSurname varchar(255),
	Department varchar(255),
)

create table Salaries (
	SalaryId int primary key,
	SalaryAmount decimal(10,2),
	EmployeeId int,
	Foreign key (EmployeeId) references Employees(EmployeeId)
)

create table SalaryChanges(
	SalaryChangeId int,
	SalaryChangesAmount decimal(10,2),
	SalaryId int,
	Foreign key (SalaryId) references Salaries(SalaryId)
)


create trigger ChangeSalaryTrigger
on Salaries
after insert,delete,update
as
		declare @amount decimal(10,2),@salaryChangedId int
	if(select count(*) from inserted) > 0 
		begin
	
			select @salaryChangedId = SalaryId from inserted
			select @amount = dbo.ChangeSalaryAfterToSalaryChanges(@salaryChangedId)
			insert into SalaryChanges values (1,@amount,@salaryChangedId)
		end
	else if (select count(*) from deleted) > 0
		begin 
				select @salaryChangedId = SalaryId from inserted
				delete from SalaryChanges where SalaryId = @salaryChangedId
		end

create function ChangeSalaryAfterToSalaryChanges(@salaryChangeID int)
returns Decimal(10,2)
as
begin
	declare @salaryChangedAmount decimal(10,2)
	select @salaryChangedAmount =  s.SalaryAmount  from Employees e inner join Salaries s on e.EmployeeId =  s.EmployeeId WHERE SalaryId = @salaryChangeID
	return @salaryChangedAmount
end
--Yukarıdaki tablolarda;maaş eklenen yada değişenler için uygulanan bir prosedür bulunmaktadır.
