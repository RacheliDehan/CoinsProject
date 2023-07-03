# CoinsProject
The graph shows the values of the $ exchange rate for fixed periods (week, month, half year, year) and shows the information from the current date.

הפרויקט הנל- Coins Project הינו פרויקט המציג גרף המיצג את ערכי שער הדולר לפי תקופות של שבוע, חודש , חצי שנה, שנה .
הפרויקט כתוב בשפות C# , Angular, Sql

על מנת להריץ את הפרויקט ולצפות בו-
-  להריץ את קוד הSql המופיע כאן בסוף העמוד ע"מ ליצור את הDB בצורה מקומית.
-  להוריד ולהריץ את הsrver  מהקישור הבא: https://github.com/RacheliDehan/CoinsProject_server
-  להוריד ולהריץ את הclient  מהקישור הבא:https://github.com/RacheliDehan/CoinsProject_client

script to sql:


CREATE DATABASE [CoinsDB]
 
GO
IF (1 = FULLTEXTSERVICEPROPERTY('IsFullTextInstalled'))
begin
EXEC [CoinsDB].[dbo].[sp_fulltext_database] @action = 'enable'
end
GO
ALTER DATABASE [CoinsDB] SET ANSI_NULL_DEFAULT OFF 
GO
ALTER DATABASE [CoinsDB] SET ANSI_NULLS OFF 
GO
ALTER DATABASE [CoinsDB] SET ANSI_PADDING OFF 
GO
ALTER DATABASE [CoinsDB] SET ANSI_WARNINGS OFF 
GO
ALTER DATABASE [CoinsDB] SET ARITHABORT OFF 
GO
ALTER DATABASE [CoinsDB] SET AUTO_CLOSE OFF 
GO
ALTER DATABASE [CoinsDB] SET AUTO_SHRINK OFF 
GO
ALTER DATABASE [CoinsDB] SET AUTO_UPDATE_STATISTICS ON 
GO
ALTER DATABASE [CoinsDB] SET CURSOR_CLOSE_ON_COMMIT OFF 
GO
ALTER DATABASE [CoinsDB] SET CURSOR_DEFAULT  GLOBAL 
GO
ALTER DATABASE [CoinsDB] SET CONCAT_NULL_YIELDS_NULL OFF 
GO
ALTER DATABASE [CoinsDB] SET NUMERIC_ROUNDABORT OFF 
GO
ALTER DATABASE [CoinsDB] SET QUOTED_IDENTIFIER OFF 
GO
ALTER DATABASE [CoinsDB] SET RECURSIVE_TRIGGERS OFF 
GO
ALTER DATABASE [CoinsDB] SET  ENABLE_BROKER 
GO
ALTER DATABASE [CoinsDB] SET AUTO_UPDATE_STATISTICS_ASYNC OFF 
GO
ALTER DATABASE [CoinsDB] SET DATE_CORRELATION_OPTIMIZATION OFF 
GO
ALTER DATABASE [CoinsDB] SET TRUSTWORTHY OFF 
GO
ALTER DATABASE [CoinsDB] SET ALLOW_SNAPSHOT_ISOLATION OFF 
GO
ALTER DATABASE [CoinsDB] SET PARAMETERIZATION SIMPLE 
GO
ALTER DATABASE [CoinsDB] SET READ_COMMITTED_SNAPSHOT OFF 
GO
ALTER DATABASE [CoinsDB] SET HONOR_BROKER_PRIORITY OFF 
GO
ALTER DATABASE [CoinsDB] SET RECOVERY FULL 
GO
ALTER DATABASE [CoinsDB] SET  MULTI_USER 
GO
ALTER DATABASE [CoinsDB] SET PAGE_VERIFY CHECKSUM  
GO
ALTER DATABASE [CoinsDB] SET DB_CHAINING OFF 
GO
ALTER DATABASE [CoinsDB] SET FILESTREAM( NON_TRANSACTED_ACCESS = OFF ) 
GO
ALTER DATABASE [CoinsDB] SET TARGET_RECOVERY_TIME = 0 SECONDS 
GO
ALTER DATABASE [CoinsDB] SET DELAYED_DURABILITY = DISABLED 
GO
EXEC sys.sp_db_vardecimal_storage_format N'Employees', N'ON'
GO
USE [CoinsDB]
GO
/****** Object:  Table [dbo].[tbl_Cities]    Script Date: 06/11/2019 15:00:40 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
USE [CoinsDB]
GO

/****** Object:  Table [dbo].[Coins]    Script Date: 03/07/2023 23:36:10 ******/
IF  EXISTS (SELECT * FROM sys.objects WHERE object_id = OBJECT_ID(N'[dbo].[Coins]') AND type in (N'U'))
DROP TABLE [dbo].[Coins]
GO

/****** Object:  Table [dbo].[Coins]    Script Date: 03/07/2023 23:36:10 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[Coins](
	[CoinId] [int] IDENTITY(1,1) NOT NULL,
	[key] [varchar](max) NULL,
	[currentExchangeRate] [float] NULL,
	[lastUpdate] [datetime] NULL,
	[CoinsId] [int] NULL,
PRIMARY KEY CLUSTERED 
(
	[CoinId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO



