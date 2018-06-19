---
title: 还原 Contoso 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, restoring databases
- databases, restoring
ms.assetid: 291178c1-826e-49e0-a1d2-cbffee749659
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77c242fe6477baac53b6a3e1b2fda545a7e4365
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210221"
---
# <a name="restoring-the-contoso-database"></a>Contoso 数据库还原
在此步骤中，将使用 SQL Server Management Studio 运行一个用于恢复 Contoso 数据库及其关联存储过程的 SQL 脚本。 您还将用初始数据来填充数据库表。  
  
### <a name="to-restore-the-contoso-database"></a>还原 Contoso 数据库  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在连接到服务器对话框中，在**SQL Server**框中，单击**连接**。  
  
    > [!NOTE]
    >  如果未启动 SQL Server 代理，右键单击它，并依次**启动**。  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在“查询”窗格中，复制以下 SQL 脚本，然后将其粘贴到“查询”窗口中：  
  
    ```  
    CREATE DATABASE Contoso  
    GO  
    USE Contoso  
    GO  
    CREATE TABLE Products (  
    [ProductID] [varchar] (255) NOT NULL ,  
    [Name] [varchar] (255) NOT NULL ,  
    [Description] [varchar] (800) NULL ,  
    [Price] [money] NULL ,  
    [NumberAvailable] [int] NOT NULL   
    ) ON [PRIMARY]  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901234', 'ADM Line Card','',200.65,820 )  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901235','Analog Line Card','',165.24,769 )  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901236', 'Mapper/MUX','',150.54,948)  
    GO  
    CREATE TABLE StatusCodes (  
    [statusID] [int] NOT NULL ,  
    [statusCode] [nvarchar] (50) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    CREATE PROCEDURE GetInventoryForProductID  
    @ProductID varchar(255),  
    @NumberAvailable INT OUTPUT,  
    @Price MONEY OUTPUT  
    AS  
    SET NOCOUNT ON  
    SELECT @NumberAvailable = NumberAvailable,  
     @Price = Price  
    FROM Products  
    WHERE  ProductID = @ProductID  
    RETURN(0)  
    GO  
    CREATE PROCEDURE SP_GetInventoryForProductID  
    @ProductID varchar(255)  
    AS  
    SET NOCOUNT ON  
    SELECT *  
    FROM Products  
    WHERE ProductID = @ProductID  
    for xml auto  
    RETURN(0)  
    ```  
  
5.  单击 **“执行”**。  
  
### <a name="to-set-permissions-on-the-contoso-database"></a>设置 Contoso 数据库的权限  
  
1.  在 Microsoft SQL Server Management studio 对象资源管理器中，展开**数据库**，展开**Contoso**数据库，，然后展开**安全**。 右键单击 **“用户”**，然后单击 **“新建用户”**。  
  
2.  在数据库用户-新的对话框中，为**登录名**，单击省略号。  
  
3.  在选择登录名对话框中，单击**浏览**。  
  
4.  在中，浏览对象对话框中，选择**BizTalk 应用程序用户**，然后单击**确定**。  
  
5.  在选择登录名对话框中，单击**确定**。  
  
6.  在数据库用户中的新建对话框框中，在**数据库角色成员身份**窗格中，选择**db_datareader**和**db_datawriter**。 有关**用户名**，输入**BizTalk 应用程序用户**。 单击 **“确定”**。  
  
7.  重复步骤 1 至 6 **BizTalk 独立主机用户**，选择**db_datareader**和**db_datawriter**为**数据库角色成员身份**，并输入**BizTalk 独立主机用户**为**用户名**。  
  
8.  重复步骤 1 至 6 **BizTalk Server Administrators**，选择**db_owner**为**数据库角色成员身份**，并输入**BizTalk Server管理员**为**用户名**。  
  
## <a name="see-also"></a>另请参阅  
 [生成并启用证书](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)