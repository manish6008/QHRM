1.Need to create Database with name:- DapperDB 

2.Create table:- CREATE TABLE [dbo].[AddProduct] ( [SN] INT IDENTITY (1, 1) NOT NULL, [Product] VARCHAR (100) NULL, [Description] VARCHAR (100) NULL, [Price] INT NULL, [Created] DATETIME NULL, PRIMARY KEY CLUSTERED ([SN] ASC) );

3.Create below stored procedures:- 
i)CREATE PROCEDURE AddOrEditProduct @SN int, @Product VARCHAR(50), @Description VARCHAR(90), @Price int, @Created DATETIME
AS BEGIN if @SN = 0 INSERT INTO AddProduct (Product, Description, Price, Created) VALUES (@Product, @Description, @Price, @Created); else UPDATE AddProduct set Product=@Product, Description=@Description, Price=@Price, Created = @Created where SN=@SN

END
CREATE PROCEDURE GetAllProducts

AS BEGIN select * from AddProduct; END

ii)CREATE PROCEDURE ProductViewById @SN int AS BEGIN select * from AddProduct where SN = @SN; END

iii)CREATE PROCEDURE ShowProduct @SN int AS BEGIN select * from AddProduct where SN = @SN; END

iv)CREATE PROCEDURE ProductDeleteById @SN int AS BEGIN Delete from AddProduct where SN = @SN; END

4.Check for connection string in DapperOrm Model 

5.EXECUTE!
