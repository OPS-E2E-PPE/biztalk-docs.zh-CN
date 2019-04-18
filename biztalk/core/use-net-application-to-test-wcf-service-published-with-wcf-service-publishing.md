---
title: 如何创建.NET 应用程序以测试 WCF 服务使用 BizTalk WCF 服务发布向导发布 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, .NET applications
- WCF services, WCF Service Publishing Wizard
- creating, .NET applications [WCF services]
- WCF Service Publishing Wizard
ms.assetid: 17e39db2-8471-4f6f-a7f1-833023cdbc39
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d390b54a79ca883b53ff5088638ba2804fa2640
ms.sourcegitcommit: 85e827c42f193e44ca8b5b8d78d6f8b8ac686f1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58867551"
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a><span data-ttu-id="2e9e6-102">如何创建.NET 应用程序以测试通过 BizTalk WCF 服务发布向导发布的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="2e9e6-102">How to Create a .NET Application to Test a WCF Service Published with the BizTalk WCF Service Publishing Wizard</span></span>
<span data-ttu-id="2e9e6-103">若要测试已发布的 WCF 服务，可以创建使用已发布的 WCF 服务的.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-103">To test your published WCF service, you can create a .NET application that consumes your published WCF service.</span></span> <span data-ttu-id="2e9e6-104">本主题介绍如何创建.NET 应用程序以测试已发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-104">This topic describes how to create a .NET application to test a published WCF service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e9e6-105">Visual Studio 帮助集合包含创建使用 WCF 服务的.NET 应用程序的重要演练。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-105">The Visual Studio Help Collection contains a valuable walkthrough for creating a .NET application that consumes WCF services.</span></span> <span data-ttu-id="2e9e6-106">可以使用本演练以测试已发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-106">You can use the walkthrough to test your published WCF service.</span></span> <span data-ttu-id="2e9e6-107">有关信息和有关创建 WCF 客户端项目的过程，请参阅"演练：访问 XML Web 服务使用 Visual Basic 或 Visual C#"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助集合中处[ http://go.microsoft.com/fwlink/?LinkId=62263 ](http://go.microsoft.com/fwlink/?LinkId=62263)。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-107">For information and procedures about creating a WCF client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="2e9e6-108">本主题使用的服务模型元数据实用工具工具 (SvcUtil.exe) 来创建 WCF 代理类和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-108">This topic uses the Service Model Metadata Utility tool (SvcUtil.exe) to create the WCF proxy classes and application configuration file.</span></span> <span data-ttu-id="2e9e6-109">SvcUtil.exe 包含在 Microsoft Windows 软件开发工具包 (SDK) 的 Windows Vista 和.NET Framework 运行时组件。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-109">SvcUtil.exe is included in the Microsoft Windows Software Development Kit (SDK) of Windows Vista and .NET Framework Runtime Components.</span></span>  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a><span data-ttu-id="2e9e6-110">若要创建一个简单 WCF 代理类和应用程序配置文件</span><span class="sxs-lookup"><span data-stu-id="2e9e6-110">To create a simple WCF proxy class and application configuration file</span></span>  
  
1.  <span data-ttu-id="2e9e6-111">按如下所示打开 CMD Shell： 单击**启动**，依次指向**所有程序**，指向**Microsoft Windows SDK**，然后单击**CMD Shell**。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-111">Open CMD Shell as follows: click **Start**, point to **All Programs**, point to **Microsoft Windows SDK**, and then click **CMD Shell**.</span></span>  
  
2.  <span data-ttu-id="2e9e6-112">在 CMD Shell 中，转到目录，你想要放置代理类和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-112">In CMD Shell, go to the directory where you want to place the proxy class and application configuration file.</span></span>  
  
3.  <span data-ttu-id="2e9e6-113">在 CMD Shell 中运行的 ServiceModel Metadata Utility Tool (SvcUtil.exe) 来创建 WCF 代理类和已发布的 WCF 服务的应用程序配置文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2e9e6-113">In CMD Shell, run the ServiceModel Metadata Utility Tool (SvcUtil.exe) to create the WCF proxy class and application configuration file for the published WCF service as follows:</span></span>  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="2e9e6-114">此命令行应用程序配置为代理类和 App.config 生成 BizTalkServiceInstance.cs。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-114">This command line generates BizTalkServiceInstance.cs for the proxy class and App.config for the application configuration.</span></span> <span data-ttu-id="2e9e6-115">有关 Svcutil.exe 的详细信息，请参阅"服务模型元数据实用工具工具 (Svcutil.exe) 在" [ http://go.microsoft.com/fwlink/?LinkId=74696 ](http://go.microsoft.com/fwlink/?LinkId=74696)。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-115">For more information about Svcutil.exe, see "Service Model Metadata Utility Tool (Svcutil.exe)" at [http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696).</span></span>  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a><span data-ttu-id="2e9e6-116">若要编译.NET 应用程序使用已发布的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="2e9e6-116">To compile your .NET application that consumes the published WCF service</span></span>  
  
1. <span data-ttu-id="2e9e6-117">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，将 SvcUtil.exe 创建文件、 BizTalkServiceInstance 和 App.config 文件中，添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, add the files that SvcUtil.exe creates, BizTalkServiceInstance and App.config, to your project.</span></span>  
  
2. <span data-ttu-id="2e9e6-118">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，请确保添加对 System.ServiceModel.dll 的引用来编译代理代码。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-118">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, make sure to add a reference to the System.ServiceModel.dll to compile the proxy code.</span></span>  
  
3. <span data-ttu-id="2e9e6-119">创建代码以使用生成的代理代码。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-119">Create the code to use the generated proxy code.</span></span> <span data-ttu-id="2e9e6-120">下面的代码演示如何使用生成的代理：</span><span class="sxs-lookup"><span data-stu-id="2e9e6-120">The following code shows how to use the generated proxy:</span></span>  
  
   ```  
   DeliveryNotification deliveryNotification= new DeliveryNotification();  
   deliveryNotification.TrackingNumber = "001";  
               Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DeliveryRequestProcess_DeliveryNotificationReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DeliveryRequestProcess_DeliveryNotificationReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
   service.Submit(deliveryNotification);  
   ```  
  
4. <span data-ttu-id="2e9e6-121">运行.NET 应用程序，以将消息发送到已发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="2e9e6-121">Run your .NET application to send messages to the published WCF service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9e6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e9e6-122">See Also</span></span>  
 [<span data-ttu-id="2e9e6-123">通过 WCF 接收适配器发布 WCF 服务时的注意事项</span><span class="sxs-lookup"><span data-stu-id="2e9e6-123">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)