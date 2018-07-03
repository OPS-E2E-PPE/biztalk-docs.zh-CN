---
title: '步骤 14: 业务流程发布为 Web 服务 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- publishing, orchestrations
- Web services, orchestrations
- message enrichment tutorial, orchestrations
- publishing, Web services
- message enrichment tutorial, Web services
ms.assetid: 8f29a7be-a679-4ca6-a648-35338d9e9e98
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64bcc47364cca427f2fc02a807528e7105a40837
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992078"
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a><span data-ttu-id="54cca-102">步骤 14: 业务流程发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="54cca-102">Step 14: Publish the Orchestration as a Web Service</span></span>
<span data-ttu-id="54cca-103">在此步骤中，使用 BizTalk Web Services 发布向导发布您的业务流程作为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="54cca-103">In this step, you use the BizTalk Web Services Publishing Wizard to publish your orchestration as a Web service.</span></span>  
  
 <span data-ttu-id="54cca-104">在发布之前该业务流程作为 Web 服务，你需要确保 BizTalkServerIsolatedHost 的登录帐户是 BizTalk Isolated Host Users 组的一部分，因此它有权访问 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="54cca-104">Before publishing the orchestration as a Web service, you need to ensure that the logon account for BizTalkServerIsolatedHost is part of the BizTalk Isolated Host Users group, so it has access to the BizTalk databases.</span></span> <span data-ttu-id="54cca-105">这是必要的因为本教程创建的 Web 服务发布向导的 SOAPReceivePort 接收位置的接收处理程序为 BizTalkServerIsolatedHost，不是 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="54cca-105">This is necessary because the receive handler for the SOAPReceivePort receive location that is created by the Web Service Publishing Wizard for this tutorial is BizTalkServerIsolatedHost, not BizTalkServerApplication.</span></span> <span data-ttu-id="54cca-106">接收处理程序是 BizTalkServerIsolatedHost 因为 SOAP 适配器在 IIS 进程，不是 BizTalk 进程下运行。</span><span class="sxs-lookup"><span data-stu-id="54cca-106">The receive handler is BizTalkServerIsolatedHost because the SOAP adapter runs under the IIS process, not the BizTalk process.</span></span>  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a><span data-ttu-id="54cca-107">若要确保访问特权的 SOAPReceivePort 接收位置</span><span class="sxs-lookup"><span data-stu-id="54cca-107">To ensure access privileges for the SOAPReceivePort receive location</span></span>  
  
1.  <span data-ttu-id="54cca-108">在 BizTalk Server 管理控制台中下**主机实例**中**平台设置**节点，右键单击**BizTalkServerIsolatedHost**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="54cca-108">In BizTalk Server Administration Console, under **Host Instances** in the **Platform Settings** node, right-click **BizTalkServerIsolatedHost**, and then click **Properties**.</span></span> <span data-ttu-id="54cca-109">在属性对话框中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="54cca-109">In the Properties dialog box, click **Configure**.</span></span> <span data-ttu-id="54cca-110">请注意**登录**帐户。</span><span class="sxs-lookup"><span data-stu-id="54cca-110">Note the **Logon** account.</span></span>  
  
2.  <span data-ttu-id="54cca-111">在计算机管理对话框中下,**组**中**本地用户和组**节点中，双击**BizTalk Isolated Host Users**。</span><span class="sxs-lookup"><span data-stu-id="54cca-111">In the Computer Management dialog box, under **Groups** in the **Local Users and Groups** node, double-click **BizTalk Isolated Host Users**.</span></span> <span data-ttu-id="54cca-112">如果的登录帐户的**BizTalkServerIsolatedHost**不是的成员**BizTalkServerIsolatedHost**，将其添加到组。</span><span class="sxs-lookup"><span data-stu-id="54cca-112">If the logon account for **BizTalkServerIsolatedHost** is not a member of **BizTalkServerIsolatedHost**, add it to the group.</span></span>  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a><span data-ttu-id="54cca-113">若要运行 BizTalk Web Services 发布向导</span><span class="sxs-lookup"><span data-stu-id="54cca-113">To run the BizTalk Web Services Publishing Wizard</span></span>  
  
1. <span data-ttu-id="54cca-114">在解决方案资源管理器的 Visual Studio 中，单击**解决方案 BTAHL7V22Common**。</span><span class="sxs-lookup"><span data-stu-id="54cca-114">In Solution Explorer of Visual Studio, click **Solution 'BTAHL7V22Common'**.</span></span> <span data-ttu-id="54cca-115">上**工具**菜单上，单击**BizTalk Web Services 发布向导**。</span><span class="sxs-lookup"><span data-stu-id="54cca-115">On the **Tools** menu, click **BizTalk Web Services Publishing Wizard**.</span></span>  
  
2. <span data-ttu-id="54cca-116">在中**BizTalk Web Services 发布向导**，然后在**欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="54cca-116">In the **BizTalk Web Services Publishing Wizard**, on the **Welcome** page, click **Next**.</span></span>  
  
3. <span data-ttu-id="54cca-117">上**创建 Web 服务**页上，选择**BizTalk 业务流程发布为 web services**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="54cca-117">On the **Create Web Service** page, select **Publish BizTalk orchestrations as web services**, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="54cca-118">上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)** 字段中，浏览到或键入 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**，单击**BTAHL7 Project.dll**，单击**打开**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="54cca-118">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\*.dll)** field, browse to or type **\<*drive*\>:\Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**, click **BTAHL7 Project.dll**, click **Open**, and then click **Next**.</span></span>  
  
5. <span data-ttu-id="54cca-119">上**业务流程和端口**页上，确保所有节点已选中，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="54cca-119">On the **Orchestrations and Ports** page, ensure that all nodes are selected, and then click **Next**.</span></span>  
  
6. <span data-ttu-id="54cca-120">上**Web 服务属性**页上，对于**web 服务的目标命名空间**，类型**http://localhost**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="54cca-120">On the **Web Service Properties** page, for **Target namespace of web service**, type **http://localhost**, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="54cca-121">上**Web 服务项目**页上，选择**允许匿名访问 web 服务**并**创建 BizTalk 接收位置在以下应用程序中**。</span><span class="sxs-lookup"><span data-stu-id="54cca-121">On the **Web Service Project** page, select **Allow anonymous access to web service** and **Create BizTalk receive locations in the following application**.</span></span> <span data-ttu-id="54cca-122">选择**BizTalk Application 1**应用程序。</span><span class="sxs-lookup"><span data-stu-id="54cca-122">Select **BizTalk Application 1** for the application.</span></span> <span data-ttu-id="54cca-123">保留默认值**位置**字段。</span><span class="sxs-lookup"><span data-stu-id="54cca-123">Keep the default in the **Location** field.</span></span> <span data-ttu-id="54cca-124">单击**下一步**以接受默认项目位置。</span><span class="sxs-lookup"><span data-stu-id="54cca-124">Click **Next** to accept the default project location.</span></span>  
  
8. <span data-ttu-id="54cca-125">上**Web Services 项目摘要**页上，单击**创建**生成 ASP.NET Web 服务项目。</span><span class="sxs-lookup"><span data-stu-id="54cca-125">On the **Web Service Project Summary** page, click **Create** to generate the ASP.NET Web Service project.</span></span>  
  
9. <span data-ttu-id="54cca-126">单击 **“完成”** 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="54cca-126">Click **Finish** to close the wizard.</span></span>  
  
10. <span data-ttu-id="54cca-127">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="54cca-127">Open the BizTalk Server Administration Console.</span></span> <span data-ttu-id="54cca-128">在控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk Application 1**.</span><span class="sxs-lookup"><span data-stu-id="54cca-128">In the console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
11. <span data-ttu-id="54cca-129">单击**接收位置**，右键单击**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**，然后单击**属性**.</span><span class="sxs-lookup"><span data-stu-id="54cca-129">Click **Receive Locations**, right-click **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, and then click **Properties**.</span></span>  
  
12. <span data-ttu-id="54cca-130">在接收位置属性对话框中，单击**接收管道**，选择**Microsoft.BizTalk.DefaultPipelines.XMLReceive**从下拉列表中，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="54cca-130">In the Receive Location Properties dialog box, click **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLReceive** from the drop-down list, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="54cca-131">右键单击**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="54cca-131">Right-click **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, and then click **Enable**.</span></span>  
  
    <span data-ttu-id="54cca-132">请继续执行[步骤 15： 配置发送和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="54cca-132">Proceed to [Step 15: Configure the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54cca-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="54cca-133">See Also</span></span>  
 [<span data-ttu-id="54cca-134">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="54cca-134">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)