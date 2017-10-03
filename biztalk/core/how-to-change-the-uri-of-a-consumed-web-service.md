---
title: "如何更改使用的 Web 服务的 URI |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, modifying
- Web services, consuming
- consuming [Web services]
- modifying, Web services
ms.assetid: 907de565-8c99-4d34-939f-fd3dba37dd11
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9ae7d7178fc24c5f16b28325fb627045e5273a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a>如何更改已使用的 Web Service 的 URI
部署业务流程之后，BizTalk Server 将为该业务流程引用的每个 Web Services 都配置一个发送端口。 默认情况下，BizTalk 在运行时使用的 Web Services 的 URL 与已导入 Web Services 的 URL 相同。 你可以使用 BizTalk Server 管理控制台更改此 URL。  
  
> [!NOTE]
>  你必须部署您的业务流程才能更改已使用的 Web Services 的 URI。 有关部署您的业务流程的详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台更改已使用的 Web Services 的 URI  
  
1.  在 BizTalk Server 管理控制台中，BizTalk 应用程序，再展开**发送端口**节点。  
  
2.  右键单击使用 SOAP 适配器配置发送端口，请单击**属性**。  
  
3.  如果你没有物理端口，可以创建发送端口和接收位置使用 BizTalk 管理控制台。 有关信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
4.  上**发送属性**对话框中，单击**配置**。  
  
5.  在**SOAP 传输属性**对话框中，在**Web 服务 URL**框中，键入 Web 服务的位置的完整 URL，然后单击**确定**。  
  
    > [!NOTE]
    >  应确保对于你指定的 URL 存在 Web Services。 BizTalk Server 对该 URL 位置不进行验证。  
  
6.  单击确定以退出**发送属性**对话框。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)   
 [如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)   
 [与使用的 Web 服务的 SOAP 标头](../core/soap-headers-with-consumed-web-services.md)   
 [创建 Web 端口](../core/creating-web-ports.md)