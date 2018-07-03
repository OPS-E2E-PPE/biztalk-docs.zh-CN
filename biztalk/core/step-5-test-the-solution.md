---
title: 步骤 5： 测试解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33a51cda93a1c2cdd6f5a70ebd62bf1d9ce05a7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020848"
---
# <a name="step-5-test-the-solution"></a><span data-ttu-id="f16a1-102">步骤 5： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="f16a1-102">Step 5: Test the Solution</span></span>
<span data-ttu-id="f16a1-103">此解决方案的目的是将通知发送到进程的自动化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，每次在 Salesforce 中通过设置为机会的阶段关闭新机会时**已结束-赢得**。</span><span class="sxs-lookup"><span data-stu-id="f16a1-103">This solution aims at automating the process of sending notifications to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], every time a new opportunity is closed in Salesforce by setting the stage of the opportunity as **Closed Won**.</span></span> <span data-ttu-id="f16a1-104">收到通知后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将查询发送到 Salesforce 以检索与机会相关的产品详细信息，然后将来自 Salesforce 的响应插入到名为的 SQL Server 数据库表**OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="f16a1-104">After the notification is received [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a query to Salesforce to retrieve product details related to the opportunity, and then inserts the response from Salesforce into a SQL Server database table called **OrderDetails**.</span></span> <span data-ttu-id="f16a1-105">因此，若要测试此解决方案，我们将更新的机会的阶段**已结束-赢得**和结果，必须在订单数据库中的 OrderDetails 表中插入相关记录。</span><span class="sxs-lookup"><span data-stu-id="f16a1-105">So, to test this solution, we will update the stage of an opportunity to **Closed Won** and as a result, relevant records must get inserted in the OrderDetails table in the Orders database.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="f16a1-106">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="f16a1-106">To test the solution</span></span>  
  
1. <span data-ttu-id="f16a1-107">使用 Salesforce 开发人员登录凭据登录到 `https://login.salesforce.com/?lt=de`。</span><span class="sxs-lookup"><span data-stu-id="f16a1-107">Log in to `https://login.salesforce.com/?lt=de`, using the Salesforce developer login credentials.</span></span>  
  
2. <span data-ttu-id="f16a1-108">在导航栏中，单击**机会**，然后单击**客户 1**。</span><span class="sxs-lookup"><span data-stu-id="f16a1-108">In the navigation bar, click **Opportunities**, and then click **Opportunity with Customer 1**.</span></span> <span data-ttu-id="f16a1-109">已创建在这个机会[步骤 2： 设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。</span><span class="sxs-lookup"><span data-stu-id="f16a1-109">You had created this opportunity in [Step 2: Set up the Salesforce System](../core/step-2-set-up-the-salesforce-system.md).</span></span>  
  
3. <span data-ttu-id="f16a1-110">在中**机会详细信息**部分中，记下中的关联产品**产品 （标准）** 部分。</span><span class="sxs-lookup"><span data-stu-id="f16a1-110">In the **Opportunity Detail** section, take a note of the associated products in the **Products (Standard)** section.</span></span> <span data-ttu-id="f16a1-111">你在此部分中输入的值最终将插入到 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="f16a1-111">The values you under this section will finally get inserted into the SQL Server database.</span></span> <span data-ttu-id="f16a1-112">下**机会详细信息**部分中，单击**编辑**按钮，然后更改的值**阶段**字段**已结束-赢得**。</span><span class="sxs-lookup"><span data-stu-id="f16a1-112">Under the **Opportunity Detail** section click the **Edit** button and change the value of **Stage** field to **Closed Won**.</span></span> <span data-ttu-id="f16a1-113">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="f16a1-113">Click **Save**.</span></span>  
  
    <span data-ttu-id="f16a1-114">![编辑现有机会](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span><span class="sxs-lookup"><span data-stu-id="f16a1-114">![Edit an existing opportunity](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span></span>  
  
4. <span data-ttu-id="f16a1-115">在 SQL Server Management Studio 中，运行查询**OrderDetails**表来选择所有行。</span><span class="sxs-lookup"><span data-stu-id="f16a1-115">In SQL Server Management Studio, run a query on the **OrderDetails** table to select all rows.</span></span>  
  
    <span data-ttu-id="f16a1-116">![SQL 查询输出](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span><span class="sxs-lookup"><span data-stu-id="f16a1-116">![SQL Query output](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span></span>  
  
    <span data-ttu-id="f16a1-117">请注意，它将列出在你更改了其阶段的机会中列出的产品。</span><span class="sxs-lookup"><span data-stu-id="f16a1-117">Notice that it lists the products that are listed in the opportunity for which you changed the stage.</span></span>  
  
    <span data-ttu-id="f16a1-118">![向机会添加产品](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="f16a1-118">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
   <span data-ttu-id="f16a1-119">您可以看到中输入的记录**OrderDetails**表对应于在 Salesforce 中创建的一组给定的产品的销售机会。</span><span class="sxs-lookup"><span data-stu-id="f16a1-119">You can see that the records entered in the **OrderDetails** table correspond to the sales opportunity created in Salesforce for a given set of products.</span></span> <span data-ttu-id="f16a1-120">你可以通过创建新的机会并将新产品与该机会相关联来重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f16a1-120">You can repeat these steps by creating new opportunities and associating new products with the opportunity.</span></span>