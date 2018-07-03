---
title: 在仅消息传递方案中如何使用 Web Services |Microsoft Docs
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
ms.openlocfilehash: 71d1e38305fd5b798a2fa8dd59fc6341dc806dfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985446"
---
# <a name="how-to-consume-web-services-in-a-messaging-only-scenario"></a>如何在仅进行消息传送的方案中使用 Web Services
SOAP 适配器的新增强之一便是其在仅进行消息传送的方案中使用基于内容的路由发送端口调用 Web Services 的能力。 此功能使得在无需创建业务流程的情况下使用 Web Services 成为可能。 此外，由于消息不再通过业务流程，在使用 Web Services 时它还具有更为出色的性能表现。  
  
 要在仅进行消息传送的方案中使用 Web Services，请执行以下操作：  
  
-   创建代理库和 XML 架构，用于调用 Web 服务  
  
-   配置发送端口和接收位置以使用 Web 服务  
  
### <a name="to-create-a-proxy-library-and-xml-schemas-for-invoking-web-services"></a>为调用 Web Services 创建代理库和 XML 架构  
  
1. 确定 Web Services 的 URL。  
  
2. 打开**空的 BizTalk Server 项目**中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案。 有关如何创建 BizTalk Server 项目的详细信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。  
  
   > [!NOTE]
   >  此演练使用 BizTalk Server 项目来生成 Web Services 使用的代理库和 XML 架构。 此外可以实现相同目的，在.NET Framework 4.0 SDK 中使用 Wsdl.exe 和 Xsd.exe。  
  
3. 在解决方案资源管理器，右键单击 BizTalk Server 项目名称，然后依次**添加服务引用**。  
  
4. 在中**添加服务引用**对话框中，单击**高级**。  
  
5. 在中**服务引用设置**对话框中，单击**添加 Web 引用**中**兼容性**部分。  
  
6. 在中**添加 Web 引用**对话框框中，执行以下操作：  
  
   1.  在中**URL**字段中，键入 Web 服务 URL，然后单击**转**。  
  
   2.  在中**Web 引用名**字段，为命名空间中，键入一个名称，然后单击**添加引用**。  
  
7. Web 引用将显示下**Web 引用**在解决方案资源管理器中的节点。  
  
   > [!TIP]
   >  Web 引用添加到 BizTalk 项目后**添加 Web 引用**当您右键单击项目名称时，才直接可用命令或**引用**或**的Web引用**.  
  
8. 在解决方案资源管理器，右键单击项目名称，然后单击**属性**启动项目设计器。  
  
9. 在项目设计器中，单击**签名**选项卡。  
  
10. 选择**为程序集签名**选项，请单击下拉列表**选择一个强名称密钥文件**，然后单击**浏览**。  
  
11. 浏览并选择程序集密钥文件，然后单击**打开**。  
  
12. 在解决方案资源管理器，右键单击项目名称，然后单击**生成**。  
  
13. 在解决方案资源管理器，右键单击项目名称，然后单击**部署**。  
  
### <a name="to-configure-a-send-port-and-receive-location-for-consuming-a-web-service"></a>为使用 Web Services 配置发送端口和接收位置  
  
1.  在 BizTalk Server 管理控制台中，创建一个发送端口。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 在创建发送端口时，选择 SOAP 作为传输类型或传输协议。  
  
2.  使用以下设置配置 SOAP 发送端口。 有关详细信息，请参阅[如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**以下设置**|选择此选项可指定以下属性。|  
    |**程序集名称**|选择在前面的过程中创建的程序集。 程序集的完全限定的名写入到 SOAP 适配器**AssemblyName**属性。|  
    |**类型名称**|指定包含要调用的 Web 方法的类的名称。 类型名称写入到 SOAP 适配器**TypeName**属性。|  
    |**方法名称**|指定列表框中的方法之一。 Web 方法写入到 Soap 适配器**MethodName**属性。|  
  
    > [!NOTE]
    >  如果要使用基于内容的路由 (CBR)，请配置发送端口的筛选器。 有关详细信息，请参阅[如何为发送端口配置筛选器](../core/how-to-configure-filters-for-a-send-port.md)。  
  
    > [!NOTE]
    >  如果没有订阅者订阅来自所调用 Web Services 的响应消息，将发生路由失败错误。  
  
## <a name="see-also"></a>请参阅  
 [使用 Web 服务](../core/consuming-web-services.md)