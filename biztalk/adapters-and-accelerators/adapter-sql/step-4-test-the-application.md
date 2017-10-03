---
title: "步骤 4： 测试应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 488b13fa-7a71-4430-bbf5-dbf47ba55562
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 347c2bcf459d7e9ce7b1fb9efc07579be81d989d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-application"></a><span data-ttu-id="8e984-102">步骤 4： 测试应用程序</span><span class="sxs-lookup"><span data-stu-id="8e984-102">Step 4: Test the Application</span></span>
<span data-ttu-id="8e984-103">![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="8e984-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="8e984-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="8e984-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="8e984-105">**目标：**的方法是插入中的记录在此步骤中，测试应用程序**员工**表**ADAPTER_SAMPLES**数据库。</span><span class="sxs-lookup"><span data-stu-id="8e984-105">**Objective:** In this step, you test the application by inserting a record in the **Employee** table of the **ADAPTER_SAMPLES** database.</span></span> <span data-ttu-id="8e984-106">如果应用程序都运行正常，业务流程会接收的更改的通知**员工**表。</span><span class="sxs-lookup"><span data-stu-id="8e984-106">If the application is working properly, the orchestration receives a notification for changes to the **Employee** table.</span></span> <span data-ttu-id="8e984-107">然后，业务流程中提取收到的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="8e984-107">The orchestration then extracts the type of notification received.</span></span> <span data-ttu-id="8e984-108">如果通知为插入操作，业务流程执行**UPDATE_EMPLOYEE**存储过程并接收响应。</span><span class="sxs-lookup"><span data-stu-id="8e984-108">If the notification is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure and receives a response.</span></span> <span data-ttu-id="8e984-109">业务流程提取的值**Employee_ID**和**名称**响应并将其到插入**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="8e984-109">The orchestration extracts the values of **Employee_ID** and **Name** from the response and inserts them into the **Purchase_Order** table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e984-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="8e984-110">Prerequisites</span></span>  
 <span data-ttu-id="8e984-111">在开始之前与此步骤，你必须确保以下方面：</span><span class="sxs-lookup"><span data-stu-id="8e984-111">Before starting with this step, you must ensure the following:</span></span>  
  
-   <span data-ttu-id="8e984-112">要调用的请求消息**UPDATE_EMPLOYEE**存储的过程位于 C:\TestLocation\CreateEmployeeMessage。</span><span class="sxs-lookup"><span data-stu-id="8e984-112">A request message to invoke the **UPDATE_EMPLOYEE** stored procedure is available at C:\TestLocation\CreateEmployeeMessage.</span></span> <span data-ttu-id="8e984-113">请求消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e984-113">The request message looks like the following:</span></span>  
  
    ```  
    <UPDATE_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/dbo" />  
    ```  
  
-   <span data-ttu-id="8e984-114">要调用插入操作的请求消息**Purchase_Order**表位于 C:\TestLocation\CreatePOMessage。</span><span class="sxs-lookup"><span data-stu-id="8e984-114">A request message to invoke the Insert operation on the **Purchase_Order** table is available at C:\TestLocation\CreatePOMessage.</span></span> <span data-ttu-id="8e984-115">请求消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e984-115">The request message looks like the following:</span></span>  
  
    ```  
    <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Purchase_Order">  
      <Rows>  
        <Purchase_Order xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10</Employee_ID><Employee_Name>Employee_Name</Employee_Name>  
        </Purchase_Order>  
      </Rows>  
    </Insert>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8e984-116">值**Employee_ID**和**Employee_Name**字段是占位符。</span><span class="sxs-lookup"><span data-stu-id="8e984-116">The values for the **Employee_ID** and **Employee_Name** fields are placeholders.</span></span> <span data-ttu-id="8e984-117">在运行时业务流程由插入的实际值。</span><span class="sxs-lookup"><span data-stu-id="8e984-117">The actual values are inserted by the orchestration at run-time.</span></span>  
  
-   <span data-ttu-id="8e984-118">你必须已完成[步骤 3： 配置并启动应用程序](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)。</span><span class="sxs-lookup"><span data-stu-id="8e984-118">You must have completed [Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md).</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="8e984-119">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="8e984-119">To test the application</span></span>  
  
1.  <span data-ttu-id="8e984-120">插入中的记录**员工**表。</span><span class="sxs-lookup"><span data-stu-id="8e984-120">Insert a record in the **Employee** table.</span></span> <span data-ttu-id="8e984-121">你可以通过从 SQL Server Management Studio 中运行以下语句来实现。</span><span class="sxs-lookup"><span data-stu-id="8e984-121">You can do so by running the following statement from SQL Server Management Studio.</span></span>  
  
    ```  
    INSERT INTO [ADAPTER_SAMPLES].[dbo].[Employee] ([Name] ,[Designation] ,[Salary])  
    VALUES('John Smith' ,'Manager' ,500000)  
    ```  
  
2.  <span data-ttu-id="8e984-122">检查**员工**数据库表中的。</span><span class="sxs-lookup"><span data-stu-id="8e984-122">Check the **Employee** table in the database.</span></span> <span data-ttu-id="8e984-123">你将注意到，通过添加新的记录**状态**列是"0"。</span><span class="sxs-lookup"><span data-stu-id="8e984-123">You will notice that the new record is added by the **Status** column is “0.”</span></span>  
  
3.  <span data-ttu-id="8e984-124">保留刷新**员工**表记录。</span><span class="sxs-lookup"><span data-stu-id="8e984-124">Keep refreshing the **Employee** table records.</span></span> <span data-ttu-id="8e984-125">你将注意到，**状态**新记录的列现在设置为"1。</span><span class="sxs-lookup"><span data-stu-id="8e984-125">You will notice that the **Status** column for the new record is now set to “1.”</span></span>  
  
4.  <span data-ttu-id="8e984-126">检查**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="8e984-126">Check the **Purchase_Order** table.</span></span> <span data-ttu-id="8e984-127">你将注意到，将记录具有相同的员工姓名和指派应用时，提供在 Insert 语句中，添加到表。</span><span class="sxs-lookup"><span data-stu-id="8e984-127">You will notice that a record with the same employee name and designation, as you provided in the Insert statement, is added to the table.</span></span>  
  
5.  <span data-ttu-id="8e984-128">如果你提供你的电子邮件别名中的 SMTP 端口配置，您也会收到一封电子邮件与插入操作的响应消息。</span><span class="sxs-lookup"><span data-stu-id="8e984-128">If you provided your e-mail alias in the SMTP port configuration, you will also receive an e-mail with the response message for the Insert operation.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="8e984-129">内容回顾</span><span class="sxs-lookup"><span data-stu-id="8e984-129">What did I just do?</span></span>  
 <span data-ttu-id="8e984-130">测试 SampleApplication 应用程序的方法是插入中的记录**员工**表。</span><span class="sxs-lookup"><span data-stu-id="8e984-130">Tested the SampleApplication application by inserting a record in the **Employee** table.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8e984-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8e984-131">Next Steps</span></span>  
 <span data-ttu-id="8e984-132">如果测试成功，祝贺您！</span><span class="sxs-lookup"><span data-stu-id="8e984-132">If the test worked, congratulations!</span></span> <span data-ttu-id="8e984-133">已完成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]教程。</span><span class="sxs-lookup"><span data-stu-id="8e984-133">You have completed the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tutorial.</span></span>  
  
 <span data-ttu-id="8e984-134">如果测试失败，请认真检查您所做的工作以确保您已添加所有必需的对象并已正确设置其属性。</span><span class="sxs-lookup"><span data-stu-id="8e984-134">If the test did not work, carefully check your work to make sure that you added all of the necessary objects and set their properties correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e984-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e984-135">See Also</span></span>  
 <span data-ttu-id="8e984-136">[步骤 3： 配置并启动应用程序](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="8e984-136">[Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span></span>  
 [<span data-ttu-id="8e984-137">第 5 课： 部署解决方案</span><span class="sxs-lookup"><span data-stu-id="8e984-137">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)