# BookStore
 an ASP.CORE Net book store web app

the tables that you'd need to use the app are listed below

CREATE TABLE [dbo].[cart] ( [Id] INT IDENTITY (1, 1) NOT NULL, [name] VARCHAR (50) NULL, [quantity] INT NULL, [userid] INT NULL, [itemid] INT NULL, PRIMARY KEY CLUSTERED ([Id] ASC) );

CREATE TABLE [dbo].[items] ( [Id] INT IDENTITY (1, 1) NOT NULL, [name] VARCHAR (50) NULL, [description] VARCHAR (MAX) NULL, [price] INT NULL, [quantity] INT NULL, [discount] VARCHAR (50) NULL, [category] VARCHAR (50) NULL, [image] VARCHAR (MAX) NULL, PRIMARY KEY CLUSTERED ([Id] ASC) );

CREATE TABLE [dbo].[orders] ( [Id] INT IDENTITY (1, 1) NOT NULL, [userid] INT NULL, [itemid] INT NULL, [buyDate] DATETIME NULL, [quantity] INT NULL, PRIMARY KEY CLUSTERED ([Id] ASC), CONSTRAINT [FK_orders_items] FOREIGN KEY ([itemid]) REFERENCES [dbo].[items] ([Id]) );

CREATE TABLE [dbo].[users] ( [Id] INT IDENTITY (1, 1) NOT NULL, [name] VARCHAR (50) NULL, [password] VARCHAR (50) NULL, [role] VARCHAR (50) NULL, [registerDate] DATETIME NULL, PRIMARY KEY CLUSTERED ([Id] ASC) );
