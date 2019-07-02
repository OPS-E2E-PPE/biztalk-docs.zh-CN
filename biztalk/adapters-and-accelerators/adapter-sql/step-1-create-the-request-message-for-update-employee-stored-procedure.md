---
title: 第 1 步：创建请求消息为 UPDATE_EMPLOYEE 存储过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dd975d9-4b38-46e0-a926-4b325b0d7b5e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee815884b029e1efecedfcb3a6aea3b5a256e0a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367906"
---
# <a name="step-1-create-the-request-message-for-updateemployee-stored-procedure"></a><span data-ttu-id="ca30b-102">第 1 步：创建请求消息为 UPDATE_EMPLOYEE 存储过程</span><span class="sxs-lookup"><span data-stu-id="ca30b-102">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>
<span data-ttu-id="ca30b-103">![2 的第 1 步](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="ca30b-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="ca30b-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="ca30b-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="ca30b-105">**目标：** 在此步骤中，您将添加C#到你的解决方案的类库项目。</span><span class="sxs-lookup"><span data-stu-id="ca30b-105">**Objective:** In this step, you add a C# class library project to your solution.</span></span> <span data-ttu-id="ca30b-106">此库创建的内存中请求消息**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="ca30b-106">This library creates an in-memory request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="ca30b-107">在后续步骤中，业务流程将此消息发送到 SQL Server 执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="ca30b-107">In later steps, the orchestration sends this message to SQL Server to execute the stored procedure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ca30b-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="ca30b-108">Prerequisites</span></span>  
 <span data-ttu-id="ca30b-109">你必须完成中的步骤[第 2 课：接收和筛选通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="ca30b-109">You must have completed the steps in [Lesson 2: Receive and Filter Notifications](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span></span>  
  
### <a name="to-create-a-request-message-for-updateemployee-stored-procedure"></a><span data-ttu-id="ca30b-110">若要创建请求消息为 UPDATE_EMPLOYEE 存储过程</span><span class="sxs-lookup"><span data-stu-id="ca30b-110">To create a request message for UPDATE_EMPLOYEE stored procedure</span></span>  
  
1.  <span data-ttu-id="ca30b-111">将视觉对象添加C#到你的解决方案的类库项目。</span><span class="sxs-lookup"><span data-stu-id="ca30b-111">Add a Visual C# class library project to your solution.</span></span> <span data-ttu-id="ca30b-112">对于项目的名称，键入`UpdateEmployeeMessageCreator`。</span><span class="sxs-lookup"><span data-stu-id="ca30b-112">For the name of the project, type `UpdateEmployeeMessageCreator`.</span></span>  
  
2.  <span data-ttu-id="ca30b-113">重命名**Class1.cs**到**UpdateEmployeeMessageCreator.cs**。</span><span class="sxs-lookup"><span data-stu-id="ca30b-113">Rename **Class1.cs** to **UpdateEmployeeMessageCreator.cs**.</span></span>  
  
3.  <span data-ttu-id="ca30b-114">将以下代码复制到.cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="ca30b-114">Copy the following code to the .cs file:</span></span>  
  
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
  
     <span data-ttu-id="ca30b-115">此代码片段需要的请求消息**UPDATE_EMPLOYEE**存储过程在 C:\TestLocation\CreateEmployeeMessage。</span><span class="sxs-lookup"><span data-stu-id="ca30b-115">This code snippet expects a request message for the **UPDATE_EMPLOYEE** stored procedure to be present at C:\TestLocation\CreateEmployeeMessage.</span></span> <span data-ttu-id="ca30b-116">代码使用请求消息在运行时创建类似的请求消息。</span><span class="sxs-lookup"><span data-stu-id="ca30b-116">The code uses the request message to create a similar request message at run time.</span></span>  
  
4.  <span data-ttu-id="ca30b-117">向项目添加强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="ca30b-117">Add a strong-name key file to the project.</span></span> <span data-ttu-id="ca30b-118">请参阅[先决条件若要创建 SQL 应用程序使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ca30b-118">See [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span></span>  
  
    1.  <span data-ttu-id="ca30b-119">在解决方案资源管理器，右键单击**UpdateEmployeeMessageCreator**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ca30b-119">In the Solution Explorer, right-click the **UpdateEmployeeMessageCreator** project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="ca30b-120">在中**属性**窗口中，单击**签名**。</span><span class="sxs-lookup"><span data-stu-id="ca30b-120">In the **Property** window, click **Signing**.</span></span>  
  
    3.  <span data-ttu-id="ca30b-121">在中**签名**选项卡上，选择**程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="ca30b-121">In the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
    4.  <span data-ttu-id="ca30b-122">从**选择一个强名称密钥文件**列表中，单击 **\<浏览\>** 。</span><span class="sxs-lookup"><span data-stu-id="ca30b-122">From the **Choose a strong-name key file** list, click **\<Browse\>**.</span></span>  
  
    5.  <span data-ttu-id="ca30b-123">导航到在其中创建强名称密钥文件的文件夹，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="ca30b-123">Navigate to the folder where you created the strong-name key file, and then click **Open**.</span></span>  
  
    6.  <span data-ttu-id="ca30b-124">单击**保存**标准菜单栏上。</span><span class="sxs-lookup"><span data-stu-id="ca30b-124">Click **Save** on the Standard menu bar.</span></span> <span data-ttu-id="ca30b-125">关闭**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="ca30b-125">Close the **Property** window.</span></span>  
  
5.  <span data-ttu-id="ca30b-126">生成项目。</span><span class="sxs-lookup"><span data-stu-id="ca30b-126">Build the project.</span></span> <span data-ttu-id="ca30b-127">右键单击项目，然后依次**生成**。</span><span class="sxs-lookup"><span data-stu-id="ca30b-127">Right-click the project, and then click **Build**.</span></span>  
  
6.  <span data-ttu-id="ca30b-128">将此项目的引用添加到解决方案中的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ca30b-128">Add a reference of this project to the BizTalk project in the solution.</span></span>  
  
    1.  <span data-ttu-id="ca30b-129">在解决方案资源管理器，展开 BizTalk 项目中，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="ca30b-129">In the Solution Explorer, expand the BizTalk project, right-click **References**, and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="ca30b-130">在中**添加引用**对话框中，单击**项目**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ca30b-130">In the **Add Reference** dialog box, click the **Projects** tab.</span></span>  
  
    3.  <span data-ttu-id="ca30b-131">从项目名称的列表中选择**UpdateEmployeeMessageCreator**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca30b-131">From the list of project names, select **UpdateEmployeeMessageCreator**, click **Add**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="ca30b-132">生成项目创建项目的 \bin\Debug 文件夹下的程序集 DLL。</span><span class="sxs-lookup"><span data-stu-id="ca30b-132">Building the project creates the assembly DLL under \bin\Debug folder of the project.</span></span> <span data-ttu-id="ca30b-133">必须将此 DLL 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="ca30b-133">You must add this DLL to the Global Assembly Cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="ca30b-134">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ca30b-134">Start a Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="ca30b-135">从命令提示符处，导航到的 \bin\Debug\ 文件夹**UpdateEmployeeMessageCreator**项目。</span><span class="sxs-lookup"><span data-stu-id="ca30b-135">From the command prompt, navigate to the \bin\Debug\ folder of the **UpdateEmployeeMessageCreator** project.</span></span>  
  
    3.  <span data-ttu-id="ca30b-136">在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ca30b-136">Run the following command on the command prompt:</span></span>  
  
        ```  
        gacutil /i UpdateEmployeeMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="ca30b-137">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="ca30b-137">What did I just do?</span></span>  
 <span data-ttu-id="ca30b-138">在此步骤中，您添加了在运行时创建请求消息的 UpdateEmployeeMessageCreator 类库项目。</span><span class="sxs-lookup"><span data-stu-id="ca30b-138">In this step, you added an UpdateEmployeeMessageCreator class library project that creates request message at run-time.</span></span> <span data-ttu-id="ca30b-139">在 BizTalk 项目中添加对此项目的引用和也添加到 GAC 的程序集 DLL。</span><span class="sxs-lookup"><span data-stu-id="ca30b-139">You added the reference to this project in the BizTalk project and also added the assembly DLL to the GAC.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ca30b-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ca30b-140">Next Steps</span></span>  
 <span data-ttu-id="ca30b-141">将请求消息发送到 SQL Server 并接收响应，如中所述[步骤 2:请求消息发送到 SQL Server 并接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)。</span><span class="sxs-lookup"><span data-stu-id="ca30b-141">You send the request message to SQL Server and receive the response, as described in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca30b-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca30b-142">See Also</span></span>  
 [<span data-ttu-id="ca30b-143">第 3 课：执行存储过程以选择新添加的员工</span><span class="sxs-lookup"><span data-stu-id="ca30b-143">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)