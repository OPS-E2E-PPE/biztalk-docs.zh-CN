---
title: "步骤 5： 测试解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ce7edd1c1f1f8a063e2787cc2acecb3b57cca2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-test-the-solution"></a><span data-ttu-id="ef9ca-102">步骤 5： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="ef9ca-102">Step 5: Test the Solution</span></span>
<span data-ttu-id="ef9ca-103">此解决方案旨在自动执行的将通知发送到过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，每次新机会的关闭时在 Salesforce 中通过设置作为机会的阶段**关闭获胜**。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-103">This solution aims at automating the process of sending notifications to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], every time a new opportunity is closed in Salesforce by setting the stage of the opportunity as **Closed Won**.</span></span> <span data-ttu-id="ef9ca-104">收到通知后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将查询发送到 Salesforce 以检索与商机，相关的产品详细信息，然后将响应来自 Salesforce 插入名的 SQL Server 数据库表**OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="ef9ca-104">After the notification is received [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a query to Salesforce to retrieve product details related to the opportunity, and then inserts the response from Salesforce into a SQL Server database table called **OrderDetails**.</span></span> <span data-ttu-id="ef9ca-105">因此，若要测试此解决方案，我们将更新的阶段的机会**关闭获胜**以及结果是，必须获取相关的记录在 Orders 数据库中的 OrderDetails 表中插入。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-105">So, to test this solution, we will update the stage of an opportunity to **Closed Won** and as a result, relevant records must get inserted in the OrderDetails table in the Orders database.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="ef9ca-106">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="ef9ca-106">To test the solution</span></span>  
  
1.  <span data-ttu-id="ef9ca-107">使用 Salesforce 开发人员登录凭据登录到 `https://login.salesforce.com/?lt=de`。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-107">Log in to `https://login.salesforce.com/?lt=de`, using the Salesforce developer login credentials.</span></span>  
  
2.  <span data-ttu-id="ef9ca-108">在导航栏中，单击**机会**，然后单击**客户 1 的机会**。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-108">In the navigation bar, click **Opportunities**, and then click **Opportunity with Customer 1**.</span></span> <span data-ttu-id="ef9ca-109">你创建了在这个机会[步骤 2： 设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-109">You had created this opportunity in [Step 2: Set up the Salesforce System](../core/step-2-set-up-the-salesforce-system.md).</span></span>  
  
3.  <span data-ttu-id="ef9ca-110">在**机会详细信息**部分中，记下的关联产品的**产品 （标准）**部分。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-110">In the **Opportunity Detail** section, take a note of the associated products in the **Products (Standard)** section.</span></span> <span data-ttu-id="ef9ca-111">你在此部分中输入的值最终将插入到 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-111">The values you under this section will finally get inserted into the SQL Server database.</span></span> <span data-ttu-id="ef9ca-112">下**机会详细信息**部分中，单击**编辑**按钮和更改的值**阶段**字段**关闭获胜**。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-112">Under the **Opportunity Detail** section click the **Edit** button and change the value of **Stage** field to **Closed Won**.</span></span> <span data-ttu-id="ef9ca-113">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-113">Click **Save**.</span></span>  
  
     <span data-ttu-id="ef9ca-114">![编辑现有机会](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span><span class="sxs-lookup"><span data-stu-id="ef9ca-114">![Edit an existing opportunity](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span></span>  
  
4.  <span data-ttu-id="ef9ca-115">在 SQL Server Management Studio，在上运行查询**OrderDetails**表以选择所有行。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-115">In SQL Server Management Studio, run a query on the **OrderDetails** table to select all rows.</span></span>  
  
     <span data-ttu-id="ef9ca-116">![SQL 查询输出](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span><span class="sxs-lookup"><span data-stu-id="ef9ca-116">![SQL Query output](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span></span>  
  
     <span data-ttu-id="ef9ca-117">请注意，它将列出在你更改了其阶段的机会中列出的产品。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-117">Notice that it lists the products that are listed in the opportunity for which you changed the stage.</span></span>  
  
     <span data-ttu-id="ef9ca-118">![将产品添加到有机会](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="ef9ca-118">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
 <span data-ttu-id="ef9ca-119">你可以看到记录进入**OrderDetails**表对应于在 Salesforce 中创建的一组给定的产品的销售机会。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-119">You can see that the records entered in the **OrderDetails** table correspond to the sales opportunity created in Salesforce for a given set of products.</span></span> <span data-ttu-id="ef9ca-120">你可以通过创建新的机会并将新产品与该机会相关联来重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="ef9ca-120">You can repeat these steps by creating new opportunities and associating new products with the opportunity.</span></span>