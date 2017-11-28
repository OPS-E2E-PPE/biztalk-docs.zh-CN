---
title: "如何创建.NET 应用程序测试 WCF 服务与 BizTalk WCF 服务发布向导发布 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services, .NET applications
- WCF services, WCF Service Publishing Wizard
- creating, .NET applications [WCF services]
- WCF Service Publishing Wizard
ms.assetid: 17e39db2-8471-4f6f-a7f1-833023cdbc39
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb46847361127a915d06ee74eaed549caf40258a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a><span data-ttu-id="fd264-102">如何创建.NET 应用程序来测试与 BizTalk WCF 服务发布向导发布的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="fd264-102">How to Create a .NET Application to Test a WCF Service Published with the BizTalk WCF Service Publishing Wizard</span></span>
<span data-ttu-id="fd264-103">若要测试已发布的 WCF 服务，请创建一个使用已发布的 WCF 服务的 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd264-103">To test your published WCF service, you can create a .NET application that consumes your published WCF service.</span></span> <span data-ttu-id="fd264-104">本主题说明如何创建一个 .NET 应用程序以测试发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="fd264-104">This topic describes how to create a .NET application to test a published WCF service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd264-105">Visual Studio 帮助集合中包含创建使用 WCF 服务的 .NET 应用程序的重要演练。</span><span class="sxs-lookup"><span data-stu-id="fd264-105">The Visual Studio Help Collection contains a valuable walkthrough for creating a .NET application that consumes WCF services.</span></span> <span data-ttu-id="fd264-106">您可以使用此演练测试已发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="fd264-106">You can use the walkthrough to test your published WCF service.</span></span> <span data-ttu-id="fd264-107">信息和过程有关创建 WCF 客户端项目中，请参阅"演练:: 访问 XML Web 服务使用 Visual Basic 或 Visual C#"中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]在帮助集合[http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263)。</span><span class="sxs-lookup"><span data-stu-id="fd264-107">For information and procedures about creating a WCF client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd264-108">本主题使用服务模型元数据实用工具 (SvcUtil.exe) 来创建 WCF 代理类和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="fd264-108">This topic uses the Service Model Metadata Utility tool (SvcUtil.exe) to create the WCF proxy classes and application configuration file.</span></span> <span data-ttu-id="fd264-109">SvcUtil.exe 包含在 Windows Vista 和 .NET Framework 运行时组件的 Microsoft Windows 软件开发工具包 (SDK) 中。</span><span class="sxs-lookup"><span data-stu-id="fd264-109">SvcUtil.exe is included in the Microsoft Windows Software Development Kit (SDK) of Windows Vista and .NET Framework Runtime Components.</span></span>  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a><span data-ttu-id="fd264-110">创建一个简单的 WCF 代理类和应用程序配置文件</span><span class="sxs-lookup"><span data-stu-id="fd264-110">To create a simple WCF proxy class and application configuration file</span></span>  
  
1.  <span data-ttu-id="fd264-111">打开 CMD Shell，如下所示： 单击**启动**，指向**所有程序**，指向**Microsoft Windows SDK**，然后单击**CMD Shell**。</span><span class="sxs-lookup"><span data-stu-id="fd264-111">Open CMD Shell as follows: click **Start**, point to **All Programs**, point to **Microsoft Windows SDK**, and then click **CMD Shell**.</span></span>  
  
2.  <span data-ttu-id="fd264-112">在 CMD Shell 中，转到要在其中放置代理类和应用程序配置文件的目录。</span><span class="sxs-lookup"><span data-stu-id="fd264-112">In CMD Shell, go to the directory where you want to place the proxy class and application configuration file.</span></span>  
  
3.  <span data-ttu-id="fd264-113">在 CMD Shell 中，运行服务模型元数据实用工具 (SvcUtil.exe) 为已发布的 WCF 服务创建 WCF 代理类和应用程序配置文件，如下所述：</span><span class="sxs-lookup"><span data-stu-id="fd264-113">In CMD Shell, run the ServiceModel Metadata Utility Tool (SvcUtil.exe) to create the WCF proxy class and application configuration file for the published WCF service as follows:</span></span>  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fd264-114">此命令行将生成 BizTalkServiceInstance.cs 作为代理类，并生成 App.config 作为应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="fd264-114">This command line generates BizTalkServiceInstance.cs for the proxy class and App.config for the application configuration.</span></span> <span data-ttu-id="fd264-115">Svcutil.exe 有关的详细信息，请参阅"服务模型元数据实用工具 (Svcutil.exe)"在[http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696)。</span><span class="sxs-lookup"><span data-stu-id="fd264-115">For more information about Svcutil.exe, see "Service Model Metadata Utility Tool (Svcutil.exe)" at [http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696).</span></span>  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a><span data-ttu-id="fd264-116">编译使用已发布的 WCF 服务的 .NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="fd264-116">To compile your .NET application that consumes the published WCF service</span></span>  
  
1.  <span data-ttu-id="fd264-117">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 解决方案资源管理器中，将 SvcUtil.exe 创建的文件、BizTalkServiceInstance 和 App.config 添加到您的项目中。</span><span class="sxs-lookup"><span data-stu-id="fd264-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, add the files that SvcUtil.exe creates, BizTalkServiceInstance and App.config, to your project.</span></span>  
  
2.  <span data-ttu-id="fd264-118">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 解决方案资源管理器中，确保添加一个指向 System.ServiceModel.dll 的引用来编译代理代码。</span><span class="sxs-lookup"><span data-stu-id="fd264-118">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, make sure to add a reference to the System.ServiceModel.dll to compile the proxy code.</span></span>  
  
3.  <span data-ttu-id="fd264-119">创建代码以使用生成的代理代码。</span><span class="sxs-lookup"><span data-stu-id="fd264-119">Create the code to use the generated proxy code.</span></span> <span data-ttu-id="fd264-120">下列代码例示出如何使用生成的代理：</span><span class="sxs-lookup"><span data-stu-id="fd264-120">The following code shows how to use the generated proxy:</span></span>  
  
    ```  
    DeliveryNotification deliveryNotification= new DeliveryNotification();  
    deliveryNotification.TrackingNumber = "001";  
                Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
    service.Submit(deliveryNotification);  
    ```  
  
4.  <span data-ttu-id="fd264-121">运行 .NET 应用程序以将消息发送到已发布的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="fd264-121">Run your .NET application to send messages to the published WCF service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd264-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd264-122">See Also</span></span>  
 [<span data-ttu-id="fd264-123">发布使用 WCF 的 WCF 服务时的注意事项接收适配器</span><span class="sxs-lookup"><span data-stu-id="fd264-123">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)