---
title: 还原 Contoso 数据库 |Microsoft Docs
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
ms.openlocfilehash: 4d434d3817a8e00f01e458dd96850b1bff6bb79a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282398"
---
# <a name="restoring-the-contoso-database"></a><span data-ttu-id="3f1f4-102">还原 Contoso 数据库</span><span class="sxs-lookup"><span data-stu-id="3f1f4-102">Restoring the Contoso Database</span></span>
<span data-ttu-id="3f1f4-103">在此步骤中，使用 SQL Server Management Studio 运行 SQL 脚本来还原 Contoso 数据库和其关联的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-103">In this step, you use SQL Server Management Studio to run a SQL script to restore the Contoso database and its associated stored procedures.</span></span> <span data-ttu-id="3f1f4-104">您还填充数据库表用初始数据。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-104">You also populate the database tables with preliminary data.</span></span>  
  
### <a name="to-restore-the-contoso-database"></a><span data-ttu-id="3f1f4-105">还原 Contoso 数据库</span><span class="sxs-lookup"><span data-stu-id="3f1f4-105">To restore the Contoso database</span></span>  
  
1.  <span data-ttu-id="3f1f4-106">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="3f1f4-107">在连接到服务器对话框，在**SQL Server**框中，单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-107">In the Connect to Server dialog box, in the **SQL Server** box, click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3f1f4-108">如果未启动 SQL Server 代理，右键单击它，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-108">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="3f1f4-109">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-109">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="3f1f4-110">在查询窗格中，复制并粘贴到查询窗口中的以下 SQL 脚本：</span><span class="sxs-lookup"><span data-stu-id="3f1f4-110">In the Query pane, copy and paste the following SQL script into the Query window:</span></span>  
  
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
  
5.  <span data-ttu-id="3f1f4-111">单击 **“执行”**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-111">Click **Execute**.</span></span>  
  
### <a name="to-set-permissions-on-the-contoso-database"></a><span data-ttu-id="3f1f4-112">若要设置 Contoso 数据库的权限</span><span class="sxs-lookup"><span data-stu-id="3f1f4-112">To set permissions on the Contoso database</span></span>  
  
1.  <span data-ttu-id="3f1f4-113">在 Microsoft SQL Server Management studio 对象资源管理器，展开**数据库**，展开**Contoso**数据库，，然后展开**安全**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-113">In the Object Explorer of the Microsoft SQL Server Management Studio, expand **Databases**, expand the **Contoso** database, and then expand **Security**.</span></span> <span data-ttu-id="3f1f4-114">右键单击 **“用户”**，然后单击 **“新建用户”**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-114">Right-click **Users**, and then click **New User**.</span></span>  
  
2.  <span data-ttu-id="3f1f4-115">在数据库用户-新对话框中，对于**登录名**，单击省略号。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-115">In the Database User - New dialog box, for **Login name**, click the ellipsis.</span></span>  
  
3.  <span data-ttu-id="3f1f4-116">在选择登录名对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-116">In the Select Login dialog box, click **Browse**.</span></span>  
  
4.  <span data-ttu-id="3f1f4-117">在对象对话框的浏览，选择**BizTalk Application Users**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-117">In the Browse for Objects dialog box, select **BizTalk Application Users**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="3f1f4-118">在选择登录名对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-118">In the Select Login dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="3f1f4-119">在数据库用户中的新建对话框框中，在**数据库角色成员身份**窗格中，选择**db_datareader**并**db_datawriter**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-119">In the Database User - New dialog box, in the **Database role membership** pane, select **db_datareader** and **db_datawriter**.</span></span> <span data-ttu-id="3f1f4-120">有关**用户名**，输入**BizTalk Application Users**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-120">For **User name**, enter **BizTalk Application Users**.</span></span> <span data-ttu-id="3f1f4-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-121">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="3f1f4-122">重复步骤 1 至 6 **BizTalk Isolated Host Users**，选择**db_datareader**并**db_datawriter**为**数据库角色成员身份**，并输入**BizTalk Isolated Host Users**有关**用户名**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-122">Repeat steps 1 through 6 for **BizTalk Isolated Host Users**, selecting **db_datareader** and **db_datawriter** for **Database role membership**, and entering **BizTalk Isolated Host Users** for **User name**.</span></span>  
  
8.  <span data-ttu-id="3f1f4-123">重复步骤 1 至 6 **BizTalk Server Administrators**，选择**db_owner**有关**数据库角色成员身份**，并输入**BizTalk Server管理员**有关**用户名**。</span><span class="sxs-lookup"><span data-stu-id="3f1f4-123">Repeat steps 1 through 6 for **BizTalk Server Administrators**, selecting **db_owner** for **Database role membership**, and entering **BizTalk Server Administrators** for **User name**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f1f4-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f1f4-124">See Also</span></span>  
 [<span data-ttu-id="3f1f4-125">生成和启用证书</span><span class="sxs-lookup"><span data-stu-id="3f1f4-125">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)