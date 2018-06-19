---
title: 如何添加 Web 端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web ports, creating
- creating, Web ports
ms.assetid: da94d98e-10ca-437a-ba34-7aa6efc68f3d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e9853755788aa29d3ca7506829dcd6bdfed53d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248005"
---
# <a name="how-to-add-a-web-port"></a>如何添加 Web 端口
你可以在业务流程设计器的端口图面上添加 Web 端口。 与其他已配置端口不同，Web 端口支持混合使用请求（单向）和请求/响应（双向）操作。 Web 端口中的每个操作都表示一个 Web 方法。 如果 Web 方法包含*输入*和*输出*参数，BizTalk 创建请求/响应操作。 如果 Web 服务仅包含*输入*参数时，BizTalk 仅创建单向操作。  
  
### <a name="to-add-a-web-port"></a>添加 Web 端口  
  
1.  业务流程设计器中，与打开的业务流程中右键单击端口图面，，然后选择**新配置端口**。  
  
2.  在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
3.  上**端口属性**页上，在**名称**文本框中，键入端口的名称，然后单击**下一步**。  
  
4.  在**选择端口类型**页上，选择**使用现有的端口类型**。  
  
5.  在**可用端口类型**框中，展开**Web 端口类型**节点，然后选择 Web 端口对应于添加 Web 服务的类型，然后单击**下一步**。  
  
     下图显示**选择端口类型**对话框。  
  
     ![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")  
  
6.  在**端口绑定**页上，在**端口绑定**下拉列表框中，选择**现在指定**。 BizTalk 将引用的 Web Services 的值自动放置到 URI、传输以及接收和发送管道中。 当部署 BizTalk 项目时，BizTalk 使用这些值创建发送端口。  
  
    > [!IMPORTANT]
    >  发送端口的默认身份验证方法是匿名访问。 如果 Web Services 需要不同身份验证或加密方法，则必须更改配置，才能提供正确的用户凭据或安全套接字层 (SSL) 以运行 Web Services。 有关详细信息，请参阅[SOAP 发送适配器](../core/soap-send-adapter.md)和[示例 TMA: HTTP 和 SOAP 适配器](../core/sample-tma-http-and-soap-adapters.md)。  
  
7.  单击**下一步**，，然后**完成**以完成向导。  
  
## <a name="see-also"></a>另请参阅  
 [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)   
 [创建 Web 端口](../core/creating-web-ports.md)