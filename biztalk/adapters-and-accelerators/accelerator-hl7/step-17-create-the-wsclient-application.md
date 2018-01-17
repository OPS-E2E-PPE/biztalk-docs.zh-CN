---
title: "步骤 17： 创建 WSClient 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WSClient application
- message enrichment tutorial, WSClient application
- creating, WSClient application
ms.assetid: 2849cd4c-30d0-47ab-8161-fab379d5a548
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54eff7c2a455d9f1129bb40d83c002bac92841bd
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="step-17-create-the-wsclient-application"></a><span data-ttu-id="3e1c4-102">步骤 17： 创建 WSClient 应用程序</span><span class="sxs-lookup"><span data-stu-id="3e1c4-102">Step 17: Create the WSClient Application</span></span>
<span data-ttu-id="3e1c4-103">WSClient.exe （Web 服务客户端） 是编写的控制台应用程序[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]，演示了如何将数据发送到作为 Web 服务与先前步骤中发布的业务流程。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-103">WSClient.exe (Web service client) is a console application written in [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] that illustrates how to send data to the orchestration that you published as a Web service in the previous steps.</span></span> <span data-ttu-id="3e1c4-104">WSClient 应用程序接受四个输入参数顺序： 患者的名字、 中间名分别姓氏和身份证号。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-104">The WSClient application accepts four input parameters in order: patient first name, middle name, last name, and social security number, respectively.</span></span> <span data-ttu-id="3e1c4-105">若要将患者信息发送到你的 Web 服务，请使用以下命令行语法：</span><span class="sxs-lookup"><span data-stu-id="3e1c4-105">To send patient information to your Web service, use the following command line syntax:</span></span>  
  
```  
wsclient john henry smith 123456789  
```  
  
### <a name="to-create-the-wsclient-application"></a><span data-ttu-id="3e1c4-106">若要创建 WSClient 应用程序</span><span class="sxs-lookup"><span data-stu-id="3e1c4-106">To create the WSClient application</span></span>  
  
1.  <span data-ttu-id="3e1c4-107">在解决方案资源管理器，右键单击**解决方案 BTAHL7V22Common**，单击**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-107">In Solution Explorer, right-click **Solution 'BTAHL7V22Common'**, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="3e1c4-108">在**添加新项目**对话框中，在**项目类型**窗格中，单击**Visual C#**并在**模板**窗格中，单击**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-108">In the **Add New Project** dialog box, in the **Project Types** pane, click **Visual C#** and in the **Templates** pane, click **Console Application**.</span></span>  
  
3.  <span data-ttu-id="3e1c4-109">在**名称**字段中，键入**WSClient**。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-109">In the **Name** field, type **WSClient**.</span></span> <span data-ttu-id="3e1c4-110">在**位置**字段中，浏览到 **\<*驱动器*\>: \Tutorial**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-110">In the **Location** field, browse to **\<*drive*\>:\Tutorial**, and then click **OK**.</span></span> <span data-ttu-id="3e1c4-111">解决方案资源管理器将 WSClient 添加到树中，并且 Program.cs 文件中会出现。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-111">Solution Explorer adds WSClient to the tree, and the Program.cs file appears.</span></span>  
  
4.  <span data-ttu-id="3e1c4-112">在解决方案资源管理器，右键单击**WSClient**，然后单击**添加 Web 引用**。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-112">In Solution Explorer, right-click **WSClient**, and then click **Add Web Reference**.</span></span>  
  
5.  <span data-ttu-id="3e1c4-113">在添加 Web 引用对话框中，单击**本地计算机上的 Web 服务**。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-113">In the Add Web Reference dialog box, click **Web services on the local machine**.</span></span> <span data-ttu-id="3e1c4-114">本地计算机可用的 Web 服务，搜索，然后将其显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-114">The local computer searches for available Web services, and then displays them in a list.</span></span>  
  
6.  <span data-ttu-id="3e1c4-115">在本地计算机上的 Web 服务的列表中，单击**BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**，单击**Operation_1**，然后单击**添加引用**.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-115">In the list of Web Services on the Local Machine, click **BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, click **Operation_1**, and then click **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="3e1c4-116">双击 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-116">Double-click Program.cs.</span></span>  
  
8.  <span data-ttu-id="3e1c4-117">复制下面的代码，然后将其粘贴到 Program.cs 窗口：</span><span class="sxs-lookup"><span data-stu-id="3e1c4-117">Copy the following code and then paste it into the Program.cs window:</span></span>  
  
    ```  
    using System;  
  
    namespace WSClient  
    {  
       class Class1  
       {  
          [STAThread]  
          static void Main(string[] args)  
          {  
             try   
             {  
                localhost.DoorbellRoot req=new WSClient.localhost.DoorbellRoot();  
                req.FirstName=args[0];  
                req.MiddleName=args[1];  
                req.LastName=args[2];  
                req.SSN=args[3];  
                localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort sp=new WSClient.localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort();  
                sp.Operation_1(req);  
             }  
             catch (Exception ex)  
             {  
                Console.WriteLine(ex.Message);  
             }  
          }  
       }  
    }  
    ```  
  
9. <span data-ttu-id="3e1c4-118">在解决方案资源管理器，右键单击**WSClient**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-118">In Solution Explorer, right-click **WSClient**, and then click **Build**.</span></span> <span data-ttu-id="3e1c4-119">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-119">Ensure that a success message appears in the output window.</span></span> <span data-ttu-id="3e1c4-120">如果不显示任何成功消息，解决**WSClient**。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-120">If no success message appears, troubleshoot **WSClient**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="3e1c4-121">将可执行文件为 WSClient.exe，一个副本放到\<*驱动器*\>: \Tutorial\WSClient\bin\Debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-121"> places a copy of the executable, WSClient.exe, into the \<*drive*\>:\Tutorial\WSClient\bin\Debug folder.</span></span>  
  
 <span data-ttu-id="3e1c4-122">继续执行[步骤 18： 测试你的新消息扩充解决方案](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="3e1c4-122">Proceed to [Step 18: Test Your New Message Enrichment Solution](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e1c4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e1c4-123">See Also</span></span>  
 [<span data-ttu-id="3e1c4-124">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="3e1c4-124">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)