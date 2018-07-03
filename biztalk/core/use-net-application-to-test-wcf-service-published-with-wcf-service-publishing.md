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
ms.openlocfilehash: d81b18e4fe2180ed3d4e58bfb7bec5e31c1d6a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996638"
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a>如何创建.NET 应用程序以测试通过 BizTalk WCF 服务发布向导发布的 WCF 服务
若要测试已发布的 WCF 服务，请创建一个使用已发布的 WCF 服务的 .NET 应用程序。 本主题说明如何创建一个 .NET 应用程序以测试发布的 WCF 服务。  
  
> [!NOTE]
>  Visual Studio 帮助集合中包含创建使用 WCF 服务的 .NET 应用程序的重要演练。 您可以使用此演练测试已发布的 WCF 服务。 有关创建 WCF 客户端项目中，有关信息和过程，请参阅"演练:: 访问 XML Web 服务使用 Visual Basic 或 Visual C#"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助集合中处[ http://go.microsoft.com/fwlink/?LinkId=62263 ](http://go.microsoft.com/fwlink/?LinkId=62263)。  
> 
> [!NOTE]
>  本主题使用服务模型元数据实用工具 (SvcUtil.exe) 来创建 WCF 代理类和应用程序配置文件。 SvcUtil.exe 包含在 Windows Vista 和 .NET Framework 运行时组件的 Microsoft Windows 软件开发工具包 (SDK) 中。  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a>创建一个简单的 WCF 代理类和应用程序配置文件  
  
1.  按如下所示打开 CMD Shell： 单击**启动**，依次指向**所有程序**，指向**Microsoft Windows SDK**，然后单击**CMD Shell**。  
  
2.  在 CMD Shell 中，转到要在其中放置代理类和应用程序配置文件的目录。  
  
3.  在 CMD Shell 中，运行服务模型元数据实用工具 (SvcUtil.exe) 为已发布的 WCF 服务创建 WCF 代理类和应用程序配置文件，如下所述：  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  此命令行将生成 BizTalkServiceInstance.cs 作为代理类，并生成 App.config 作为应用程序配置文件。 有关 Svcutil.exe 的详细信息，请参阅"服务模型元数据实用工具工具 (Svcutil.exe) 在" [ http://go.microsoft.com/fwlink/?LinkId=74696 ](http://go.microsoft.com/fwlink/?LinkId=74696)。  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a>编译使用已发布的 WCF 服务的 .NET 应用程序  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 解决方案资源管理器中，将 SvcUtil.exe 创建的文件、BizTalkServiceInstance 和 App.config 添加到您的项目中。  
  
2. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 解决方案资源管理器中，确保添加一个指向 System.ServiceModel.dll 的引用来编译代理代码。  
  
3. 创建代码以使用生成的代理代码。 下列代码例示出如何使用生成的代理：  
  
   ```  
   DeliveryNotification deliveryNotification= new DeliveryNotification();  
   deliveryNotification.TrackingNumber = "001";  
               Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
   service.Submit(deliveryNotification);  
   ```  
  
4. 运行 .NET 应用程序以将消息发送到已发布的 WCF 服务。  
  
## <a name="see-also"></a>请参阅  
 [通过 WCF 接收适配器发布 WCF 服务时的注意事项](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)