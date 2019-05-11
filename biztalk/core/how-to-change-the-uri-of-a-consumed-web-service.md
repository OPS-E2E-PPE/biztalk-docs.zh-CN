---
title: 如何更改已使用的 Web 服务的 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, modifying
- Web services, consuming
- consuming [Web services]
- modifying, Web services
ms.assetid: 907de565-8c99-4d34-939f-fd3dba37dd11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5fd101ba0553397b6c7144545a9ac557ceada03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342392"
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a>如何更改已使用的 Web Service 的 URI
在部署您的业务流程后，BizTalk Server 将配置该业务流程引用每个 Web 服务的发送端口。 默认情况下，BizTalk Web 服务的 URL 在运行时使用的导入的 Web 服务的相同 URL。 你可以更改此 URL 使用 BizTalk Server 管理控制台。  
  
> [!NOTE]
>  更改使用的 Web 服务的 URI 之前，必须部署您的业务流程。 部署您的业务流程的详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a>若要更改使用 BizTalk Server 管理控制台使用的 Web 服务的 URI  
  
1.  在 BizTalk Server 管理控制台中，展开 BizTalk 应用程序，然后展开**发送端口**节点。  
  
2.  右键单击与 SOAP 适配器配置的发送端口，单击**属性**。  
  
3.  如果没有物理端口，可以创建发送端口和接收位置使用 BizTalk 管理控制台。 有关信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
4.  上**发送属性**对话框中，单击**配置**。  
  
5.  在中**SOAP 传输属性**对话框中**Web 服务 URL**框中，键入 Web 服务的位置的完整 URL，然后单击**确定**。  
  
    > [!NOTE]
    >  您应该确保你指定的 url 存在 Web 服务。 BizTalk Server 不会验证的 URL 位置。  
  
6.  单击确定以退出**发送属性**对话框。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)   
 [如何配置 SOAP 发送端口](../core/how-to-configure-a-soap-send-port.md)   
 [SOAP 标头与已使用的 Web 服务](../core/soap-headers-with-consumed-web-services.md)   
 [创建 Web 端口](../core/creating-web-ports.md)