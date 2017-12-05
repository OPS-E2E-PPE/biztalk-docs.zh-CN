---
title: "步骤 1： 为 UPDATE_EMPLOYEE 创建请求消息存储过程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dd975d9-4b38-46e0-a926-4b325b0d7b5e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e30225b79b14ffc237798ddde6f3fe40fb4aea9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-create-the-request-message-for-updateemployee-stored-procedure"></a><span data-ttu-id="39d98-102">步骤 1： 为 UPDATE_EMPLOYEE 创建请求消息存储过程</span><span class="sxs-lookup"><span data-stu-id="39d98-102">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>
<span data-ttu-id="39d98-103">![2 的第 1 步](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="39d98-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="39d98-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="39d98-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="39d98-105">**目标：**在此步骤中，你可以将 C# 类库项目添加到你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="39d98-105">**Objective:** In this step, you add a C# class library project to your solution.</span></span> <span data-ttu-id="39d98-106">此库创建的内存中请求消息**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="39d98-106">This library creates an in-memory request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="39d98-107">在后续步骤中，业务流程将此消息发送到 SQL Server 来执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="39d98-107">In later steps, the orchestration sends this message to SQL Server to execute the stored procedure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="39d98-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="39d98-108">Prerequisites</span></span>  
 <span data-ttu-id="39d98-109">你必须已完成中的步骤[第 2 课： 接收和筛选器通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="39d98-109">You must have completed the steps in [Lesson 2: Receive and Filter Notifications](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span></span>  
  
### <a name="to-create-a-request-message-for-updateemployee-stored-procedure"></a><span data-ttu-id="39d98-110">若要针对 UPDATE_EMPLOYEE 创建请求的邮件存储过程</span><span class="sxs-lookup"><span data-stu-id="39d98-110">To create a request message for UPDATE_EMPLOYEE stored procedure</span></span>  
  
1.  <span data-ttu-id="39d98-111">将 Visual C# 类库项目添加到你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="39d98-111">Add a Visual C# class library project to your solution.</span></span> <span data-ttu-id="39d98-112">有关项目的名称，键入`UpdateEmployeeMessageCreator`。</span><span class="sxs-lookup"><span data-stu-id="39d98-112">For the name of the project, type `UpdateEmployeeMessageCreator`.</span></span>  
  
2.  <span data-ttu-id="39d98-113">重命名**Class1.cs**到**UpdateEmployeeMessageCreator.cs**。</span><span class="sxs-lookup"><span data-stu-id="39d98-113">Rename **Class1.cs** to **UpdateEmployeeMessageCreator.cs**.</span></span>  
  
3.  <span data-ttu-id="39d98-114">将下面的代码复制到.cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="39d98-114">Copy the following code to the .cs file:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdateEmployeeMessageCreator  
    {  
        public class UpdateEmployeeMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreateEmployeeMessage";  
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
  
     <span data-ttu-id="39d98-115">此代码段应该接收的请求消息**UPDATE_EMPLOYEE**存储存在于 C:\TestLocation\CreateEmployeeMessage 的过程。</span><span class="sxs-lookup"><span data-stu-id="39d98-115">This code snippet expects a request message for the **UPDATE_EMPLOYEE** stored procedure to be present at C:\TestLocation\CreateEmployeeMessage.</span></span> <span data-ttu-id="39d98-116">该代码使用请求消息以在运行时创建的类似的请求消息。</span><span class="sxs-lookup"><span data-stu-id="39d98-116">The code uses the request message to create a similar request message at run time.</span></span>  
  
4.  <span data-ttu-id="39d98-117">向项目添加一个强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="39d98-117">Add a strong-name key file to the project.</span></span> <span data-ttu-id="39d98-118">请参阅[系统必备组件来创建 SQL 应用程序使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="39d98-118">See [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span></span>  
  
    1.  <span data-ttu-id="39d98-119">在解决方案资源管理器，右键单击**UpdateEmployeeMessageCreator**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="39d98-119">In the Solution Explorer, right-click the **UpdateEmployeeMessageCreator** project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="39d98-120">在**属性**窗口中，单击**签名**。</span><span class="sxs-lookup"><span data-stu-id="39d98-120">In the **Property** window, click **Signing**.</span></span>  
  
    3.  <span data-ttu-id="39d98-121">在**签名**选项卡上，选择**对程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="39d98-121">In the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
    4.  <span data-ttu-id="39d98-122">从**选择强名称密钥文件**列表中，单击**\<浏览\>**。</span><span class="sxs-lookup"><span data-stu-id="39d98-122">From the **Choose a strong-name key file** list, click **\<Browse\>**.</span></span>  
  
    5.  <span data-ttu-id="39d98-123">导航到您在其中创建强名称密钥文件的文件夹，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="39d98-123">Navigate to the folder where you created the strong-name key file, and then click **Open**.</span></span>  
  
    6.  <span data-ttu-id="39d98-124">单击**保存**在标准菜单栏上。</span><span class="sxs-lookup"><span data-stu-id="39d98-124">Click **Save** on the Standard menu bar.</span></span> <span data-ttu-id="39d98-125">关闭**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="39d98-125">Close the **Property** window.</span></span>  
  
5.  <span data-ttu-id="39d98-126">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="39d98-126">Build the project.</span></span> <span data-ttu-id="39d98-127">右键单击项目，并依次**生成**。</span><span class="sxs-lookup"><span data-stu-id="39d98-127">Right-click the project, and then click **Build**.</span></span>  
  
6.  <span data-ttu-id="39d98-128">将此项目的引用添加到解决方案中的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="39d98-128">Add a reference of this project to the BizTalk project in the solution.</span></span>  
  
    1.  <span data-ttu-id="39d98-129">在解决方案资源管理器，展开 BizTalk 项目，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="39d98-129">In the Solution Explorer, expand the BizTalk project, right-click **References**, and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="39d98-130">在**添加引用**对话框中，单击**项目**选项卡。</span><span class="sxs-lookup"><span data-stu-id="39d98-130">In the **Add Reference** dialog box, click the **Projects** tab.</span></span>  
  
    3.  <span data-ttu-id="39d98-131">从项目名称的列表，选择**UpdateEmployeeMessageCreator**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39d98-131">From the list of project names, select **UpdateEmployeeMessageCreator**, click **Add**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="39d98-132">生成项目创建的项目的 \bin\Debug 文件夹下的程序集 DLL。</span><span class="sxs-lookup"><span data-stu-id="39d98-132">Building the project creates the assembly DLL under \bin\Debug folder of the project.</span></span> <span data-ttu-id="39d98-133">你必须将此 DLL 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="39d98-133">You must add this DLL to the Global Assembly Cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="39d98-134">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="39d98-134">Start a Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="39d98-135">从命令提示符处，导航到的 \bin\Debug\ 文件夹**UpdateEmployeeMessageCreator**项目。</span><span class="sxs-lookup"><span data-stu-id="39d98-135">From the command prompt, navigate to the \bin\Debug\ folder of the **UpdateEmployeeMessageCreator** project.</span></span>  
  
    3.  <span data-ttu-id="39d98-136">在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="39d98-136">Run the following command on the command prompt:</span></span>  
  
        ```  
        gacutil /i UpdateEmployeeMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="39d98-137">内容回顾</span><span class="sxs-lookup"><span data-stu-id="39d98-137">What did I just do?</span></span>  
 <span data-ttu-id="39d98-138">在此步骤中，你添加 UpdateEmployeeMessageCreator 类库项目的创建在运行时的请求消息。</span><span class="sxs-lookup"><span data-stu-id="39d98-138">In this step, you added an UpdateEmployeeMessageCreator class library project that creates request message at run-time.</span></span> <span data-ttu-id="39d98-139">在 BizTalk 项目中添加此项目的引用，并还添加到 GAC 的程序集 DLL。</span><span class="sxs-lookup"><span data-stu-id="39d98-139">You added the reference to this project in the BizTalk project and also added the assembly DLL to the GAC.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="39d98-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="39d98-140">Next Steps</span></span>  
 <span data-ttu-id="39d98-141">将请求消息发送到 SQL Server 和中所述接收的响应，[步骤 2： 将请求消息发送到 SQL Server 和接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)。</span><span class="sxs-lookup"><span data-stu-id="39d98-141">You send the request message to SQL Server and receive the response, as described in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d98-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39d98-142">See Also</span></span>  
 [<span data-ttu-id="39d98-143">第 3 课：执行存储过程以选择新添加的员工</span><span class="sxs-lookup"><span data-stu-id="39d98-143">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)