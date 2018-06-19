---
title: 如何使用 Web Services 在消息传递的仅限方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66873959-5b1b-4d9b-ad19-f083670420b8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ac3e87d54ab7babed8be6b4d81267d22d8ac319
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249421"
---
# <a name="how-to-consume-web-services-in-a-messaging-only-scenario"></a>如何在仅进行消息传送的方案中使用 Web Services
SOAP 适配器的新增强之一便是其在仅进行消息传送的方案中使用基于内容的路由发送端口调用 Web Services 的能力。 此功能使得在无需创建业务流程的情况下使用 Web Services 成为可能。 此外，由于消息不再通过业务流程，在使用 Web Services 时它还具有更为出色的性能表现。  
  
 要在仅进行消息传送的方案中使用 Web Services，请执行以下操作：  
  
-   创建代理库和用于调用 Web 服务的 XML 架构  
  
-   配置发送端口和接收使用 Web 服务的位置  
  
### <a name="to-create-a-proxy-library-and-xml-schemas-for-invoking-web-services"></a>为调用 Web Services 创建代理库和 XML 架构  
  
1.  确定 Web Services 的 URL。  
  
2.  打开**空 BizTalk 服务器项目**中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案。 有关如何创建 BizTalk 服务器项目的详细信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。  
  
    > [!NOTE]
    >  此演练使用 BizTalk Server 项目来生成 Web Services 使用的代理库和 XML 架构。 此外可以实现此目的，在.NET Framework 4.0 SDK 中使用的 Wsdl.exe 和 Xsd.exe。  
  
3.  在解决方案资源管理器，右键单击 BizTalk 服务器项目名称，，然后单击**添加服务引用**。  
  
4.  在**添加服务引用**对话框中，单击**高级**。  
  
5.  在**服务引用设置**对话框中，单击**添加 Web 引用**中**兼容性**部分。  
  
6.  在**添加 Web 引用**对话框框中，执行以下操作：  
  
    1.  在**URL**字段中键入 Web 服务 URL，然后依次**转**。  
  
    2.  在**Web 引用名称**字段，为命名空间中，键入一个名称，然后单击**添加引用**。  
  
7.  Web 引用将出现在**Web 引用**在解决方案资源管理器中的节点。  
  
    > [!TIP]
    >  Web 引用添加到 BizTalk 项目，一旦**添加 Web 引用**右键单击项目名称时，命令时直接可用或**引用**或**Web 引用**.  
  
8.  在解决方案资源管理器，右键单击项目名称，然后单击**属性**以启动项目设计器。  
  
9. 在项目设计器中，单击**签名**选项卡。  
  
10. 选择**对程序集签名**选项上，单击下拉列表**选择强名称密钥文件**，然后单击**浏览**。  
  
11. 浏览并选择的程序集密钥文件，然后单击**打开**。  
  
12. 在解决方案资源管理器，右键单击项目名称，然后单击**生成**。  
  
13. 在解决方案资源管理器，右键单击项目名称，然后单击**部署**。  
  
### <a name="to-configure-a-send-port-and-receive-location-for-consuming-a-web-service"></a>为使用 Web Services 配置发送端口和接收位置  
  
1.  在 BizTalk Server 管理控制台中，创建一个发送端口。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 在创建发送端口时，选择 SOAP 作为传输类型或传输协议。  
  
2.  使用以下设置配置 SOAP 发送端口。 有关详细信息，请参阅[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**以下设置**|选择此选项可指定以下属性。|  
    |**程序集名称**|选择在前面的过程中创建的程序集。 程序集的完全限定的名写入到 SOAP 适配器**AssemblyName**属性。|  
    |**类型名称**|指定包含要调用的 Web 方法的类的名称。 类型名称写入 SOAP 适配器**TypeName**属性。|  
    |**方法名称**|指定列表框中的方法之一。 Web 方法写入 Soap 适配器**MethodName**属性。|  
  
    > [!NOTE]
    >  如果要使用基于内容的路由 (CBR)，请配置发送端口的筛选器。 有关详细信息，请参阅[如何将筛选器配置为发送端口](../core/how-to-configure-filters-for-a-send-port.md)。  
  
    > [!NOTE]
    >  如果没有订阅者订阅来自所调用 Web Services 的响应消息，将发生路由失败错误。  
  
## <a name="see-also"></a>另请参阅  
 [使用 Web 服务](../core/consuming-web-services.md)