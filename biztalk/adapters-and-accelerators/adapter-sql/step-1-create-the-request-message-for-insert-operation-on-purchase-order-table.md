---
title: "步骤 1： 为 Purchase_Order 表上插入操作创建的请求消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fde018d8-9d9a-42ea-8ee9-e3632450b9d7
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d27a186cffc86a79f0a40f73cc6a0c1791c3b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-the-request-message-for-insert-operation-on-purchaseorder-table"></a><span data-ttu-id="0c584-102">步骤 1： 为 Purchase_Order 表上插入操作创建的请求消息</span><span class="sxs-lookup"><span data-stu-id="0c584-102">Step 1: Create the Request Message for Insert Operation on Purchase_Order Table</span></span>
<span data-ttu-id="0c584-103">![步骤 1 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="0c584-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="0c584-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="0c584-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="0c584-105">**目标：**在此步骤中，你可以将 C# 类库项目添加到你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="0c584-105">**Objective:** In this step, you add a C# class library project to your solution.</span></span> <span data-ttu-id="0c584-106">此库上创建插入操作的一个内存中请求消息**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="0c584-106">This library creates an in-memory request message for the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="0c584-107">在后续步骤中，业务流程将此邮件发送到 SQL Server 以在表中插入记录。</span><span class="sxs-lookup"><span data-stu-id="0c584-107">In later steps, the orchestration sends this message to SQL Server to insert records in the table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0c584-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="0c584-108">Prerequisites</span></span>  
 <span data-ttu-id="0c584-109">你必须已完成中的步骤[第 3 课： 执行存储过程向选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)。</span><span class="sxs-lookup"><span data-stu-id="0c584-109">You must have completed the steps in [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span></span>  
  
### <a name="to-create-a-request-message-for-insert-operation"></a><span data-ttu-id="0c584-110">若要创建插入操作的请求消息</span><span class="sxs-lookup"><span data-stu-id="0c584-110">To create a request message for Insert operation</span></span>  
  
1.  <span data-ttu-id="0c584-111">将 Visual C# 类库项目添加到你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="0c584-111">Add a Visual C# class library project to your solution.</span></span> <span data-ttu-id="0c584-112">有关项目的名称，键入`UpdatePOMessageCreator`。</span><span class="sxs-lookup"><span data-stu-id="0c584-112">For the name of the project, type `UpdatePOMessageCreator`.</span></span>  
  
2.  <span data-ttu-id="0c584-113">重命名**Class1.cs**到**UpdatePOMessageCreator.cs**。</span><span class="sxs-lookup"><span data-stu-id="0c584-113">Rename **Class1.cs** to **UpdatePOMessageCreator.cs**.</span></span>  
  
3.  <span data-ttu-id="0c584-114">将下面的代码复制到.cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="0c584-114">Copy the following code to the .cs file:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdatePOMessageCreator  
    {  
        public class UpdatePOMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreatePOMessage";  
                try  
                {  
                    ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                    Console.WriteLine("EXCEPTION: " + ex.ToString());  
                    throw ex;  
                }  
  
                //Create Message From XML  
                Message = new XmlDocument();  
  
                Message.PreserveWhitespace = true;  
  
                Message.Load(ResponseDoc);  
  
                return Message;  
            }  
        }  
    }  
  
    ```  
  
     <span data-ttu-id="0c584-115">此代码段上需要插入操作的请求消息**Purchase_Order**表存在于 C:\TestLocation\CreatePOMessage。</span><span class="sxs-lookup"><span data-stu-id="0c584-115">This code snippet expects a request message for the Insert operation on the **Purchase_Order** table to be present at C:\TestLocation\CreatePOMessage.</span></span> <span data-ttu-id="0c584-116">该代码使用请求消息以在运行时创建的类似的请求消息。</span><span class="sxs-lookup"><span data-stu-id="0c584-116">The code uses the request message to create a similar request message at run time.</span></span>  
  
4.  <span data-ttu-id="0c584-117">向项目添加一个强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="0c584-117">Add a strong-name key file to the project.</span></span> <span data-ttu-id="0c584-118">有关创建强名称密钥文件的说明，请参阅[系统必备组件来创建 SQL 应用程序使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0c584-118">For instructions on creating a strong-name key file, see [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span></span>  
  
    1.  <span data-ttu-id="0c584-119">在解决方案资源管理器，右键单击**UpdatePOMessageCreator**项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0c584-119">In the Solution Explorer, right-click the **UpdatePOMessageCreator** project and click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="0c584-120">在**属性**窗口中，单击**签名**。</span><span class="sxs-lookup"><span data-stu-id="0c584-120">In the **Property** window, click **Signing**.</span></span>  
  
    3.  <span data-ttu-id="0c584-121">在**签名**选项卡上，选择**对程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="0c584-121">In the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
    4.  <span data-ttu-id="0c584-122">从**选择强名称密钥文件**列表中，单击**\<浏览 >**。</span><span class="sxs-lookup"><span data-stu-id="0c584-122">From the **Choose a strong-name key file** list, click **\<Browse>**.</span></span>  
  
    5.  <span data-ttu-id="0c584-123">导航到您在其中创建强名称密钥文件的文件夹，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="0c584-123">Navigate to the folder where you created the strong-name key file, and then click **Open**.</span></span>  
  
    6.  <span data-ttu-id="0c584-124">单击**保存**上**标准**菜单栏。</span><span class="sxs-lookup"><span data-stu-id="0c584-124">Click **Save** on the **Standard** menu bar.</span></span> <span data-ttu-id="0c584-125">关闭**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="0c584-125">Close the **Property** window.</span></span>  
  
5.  <span data-ttu-id="0c584-126">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="0c584-126">Build the project.</span></span> <span data-ttu-id="0c584-127">右键单击项目并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="0c584-127">Right-click the project and click **Build**.</span></span>  
  
6.  <span data-ttu-id="0c584-128">将此项目的引用添加到解决方案中的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="0c584-128">Add a reference of this project to the BizTalk project in the solution.</span></span>  
  
    1.  <span data-ttu-id="0c584-129">在解决方案资源管理器，展开 BizTalk 项目，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="0c584-129">In the Solution Explorer, expand the BizTalk project, right-click **References**, and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="0c584-130">在**添加引用**对话框中，单击**项目**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0c584-130">In the **Add Reference** dialog box, click the **Projects** tab.</span></span>  
  
    3.  <span data-ttu-id="0c584-131">从项目名称的列表，选择**UpdatePOMessageCreator**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0c584-131">From the list of project names, select **UpdatePOMessageCreator**, click **Add**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0c584-132">生成项目创建的项目的 \bin\Debug 文件夹下的程序集 DLL。</span><span class="sxs-lookup"><span data-stu-id="0c584-132">Building the project creates the assembly DLL under \bin\Debug folder of the project.</span></span> <span data-ttu-id="0c584-133">你必须将此 DLL 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="0c584-133">You must add this DLL to the Global Assembly Cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="0c584-134">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="0c584-134">Start a Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="0c584-135">从命令提示符处，导航到的 \bin\Debug\ 文件夹**UpdatePOMessageCreator**项目。</span><span class="sxs-lookup"><span data-stu-id="0c584-135">From the command prompt, navigate to the \bin\Debug\ folder of the **UpdatePOMessageCreator** project.</span></span>  
  
    3.  <span data-ttu-id="0c584-136">在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0c584-136">Run the following command on the command prompt:</span></span>  
  
        ```  
        gacutil /i UpdatePOMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="0c584-137">内容回顾</span><span class="sxs-lookup"><span data-stu-id="0c584-137">What did I just do?</span></span>  
 <span data-ttu-id="0c584-138">在此步骤中，你添加 UpdatePOMessageCreator 类库项目的创建在运行时的请求消息。</span><span class="sxs-lookup"><span data-stu-id="0c584-138">In this step, you added an UpdatePOMessageCreator class library project that creates request message at run-time.</span></span> <span data-ttu-id="0c584-139">在 BizTalk 项目中添加此项目的引用，并还添加到 GAC 的程序集 DLL。</span><span class="sxs-lookup"><span data-stu-id="0c584-139">You added the reference to this project in the BizTalk project and also added the assembly DLL to the GAC.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0c584-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0c584-140">Next Steps</span></span>  
 <span data-ttu-id="0c584-141">在映射到 Insert 操作的请求消息的 UPDATE_EMPLOYEE 存储过程的响应消息**Purchaser_Order**表。</span><span class="sxs-lookup"><span data-stu-id="0c584-141">You map the response message for the UPDATE_EMPLOYEE stored procedure to the request message for the Insert operation on **Purchaser_Order** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c584-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c584-142">See Also</span></span>  
 <span data-ttu-id="0c584-143">[步骤 2： 映射要插入操作的请求消息的 UPDATE_EMPLOYEE 响应消息](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span><span class="sxs-lookup"><span data-stu-id="0c584-143">[Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span></span>  
 [<span data-ttu-id="0c584-144">第 4 课： 执行插入操作上采购订单表</span><span class="sxs-lookup"><span data-stu-id="0c584-144">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)