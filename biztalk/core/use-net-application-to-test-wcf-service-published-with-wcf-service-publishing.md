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
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a>如何创建.NET 应用程序以测试通过 BizTalk WCF 服务发布向导发布的 WCF 服务
若要测试已发布的 WCF 服务，可以创建使用已发布的 WCF 服务的.NET 应用程序。 本主题介绍如何创建.NET 应用程序以测试已发布的 WCF 服务。  
  
> [!NOTE]
>  Visual Studio 帮助集合包含创建使用 WCF 服务的.NET 应用程序的重要演练。 可以使用本演练以测试已发布的 WCF 服务。 有关信息和有关创建 WCF 客户端项目的过程，请参阅"演练：访问 XML Web 服务使用 Visual Basic 或 Visual C#"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助集合中处[ http://go.microsoft.com/fwlink/?LinkId=62263 ](http://go.microsoft.com/fwlink/?LinkId=62263)。  
> 
> [!NOTE]
>  本主题使用的服务模型元数据实用工具工具 (SvcUtil.exe) 来创建 WCF 代理类和应用程序配置文件。 SvcUtil.exe 包含在 Microsoft Windows 软件开发工具包 (SDK) 的 Windows Vista 和.NET Framework 运行时组件。  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a>若要创建一个简单 WCF 代理类和应用程序配置文件  
  
1.  按如下所示打开 CMD Shell： 单击**启动**，依次指向**所有程序**，指向**Microsoft Windows SDK**，然后单击**CMD Shell**。  
  
2.  在 CMD Shell 中，转到目录，你想要放置代理类和应用程序配置文件。  
  
3.  在 CMD Shell 中运行的 ServiceModel Metadata Utility Tool (SvcUtil.exe) 来创建 WCF 代理类和已发布的 WCF 服务的应用程序配置文件，如下所示：  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  此命令行应用程序配置为代理类和 App.config 生成 BizTalkServiceInstance.cs。 有关 Svcutil.exe 的详细信息，请参阅"服务模型元数据实用工具工具 (Svcutil.exe) 在" [ http://go.microsoft.com/fwlink/?LinkId=74696 ](http://go.microsoft.com/fwlink/?LinkId=74696)。  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a>若要编译.NET 应用程序使用已发布的 WCF 服务  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，将 SvcUtil.exe 创建文件、 BizTalkServiceInstance 和 App.config 文件中，添加到你的项目。  
  
2. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，请确保添加对 System.ServiceModel.dll 的引用来编译代理代码。  
  
3. 创建代码以使用生成的代理代码。 下面的代码演示如何使用生成的代理：  
  
   ```  
   DeliveryNotification deliveryNotification= new DeliveryNotification();  
   deliveryNotification.TrackingNumber = "001";  
               Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DeliveryRequestProcess_DeliveryNotificationReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DeliveryRequestProcess_DeliveryNotificationReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
   service.Submit(deliveryNotification);  
   ```  
  
4. 运行.NET 应用程序，以将消息发送到已发布的 WCF 服务。  
  
## <a name="see-also"></a>请参阅  
 [通过 WCF 接收适配器发布 WCF 服务时的注意事项](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)