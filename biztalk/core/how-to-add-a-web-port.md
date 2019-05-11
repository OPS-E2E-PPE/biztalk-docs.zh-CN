---
title: 如何添加 Web 端口 |Microsoft Docs
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
ms.openlocfilehash: a67cfd33aeace3b6cfde9f1e0a7e87831d7972ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387342"
---
# <a name="how-to-add-a-web-port"></a>如何添加 Web 端口
在业务流程设计器中的端口图面上添加 Web 端口。 与其他已配置的端口不同的 Web 端口支持混合使用请求 （单向） 和请求/响应 （双向） 操作。 Web 端口中的每个操作表示 Web 方法。 如果 Web 方法包含*输入*并*输出*参数，BizTalk 将创建请求/响应操作。 如果 Web 服务仅包含*输入*参数时，BizTalk 仅创建单向操作。  
  
### <a name="to-add-a-web-port"></a>若要添加 Web 端口  
  
1.  使用打开的业务流程的业务流程设计器中右键单击端口图面，然后选择**新建配置的端口**。  
  
2.  在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
3.  上**端口属性**页上，在**名称**文本框中，键入端口的名称，然后单击**下一步**。  
  
4.  在中**选择端口类型**页上，选择**使用现有端口类型**。  
  
5.  在中**可用端口类型**框中，展开**Web 端口类型**节点，然后选择 Web 端口类型对应于已添加的 Web 服务，然后依次**下一步**。  
  
     下图显示**选择端口类型**对话框。  
  
     ![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")  
  
6.  在中**端口绑定**页上，在**端口绑定**下拉列表框中，选择**立即指定**。 BizTalk 会自动将引用的 Web 服务中的值放在 URI、 传输和接收和发送管道。 BizTalk 使用这些值来部署您的 BizTalk 项目时创建发送端口。  
  
    > [!IMPORTANT]
    >  发送端口的默认身份验证方法是匿名访问。 如果 Web 服务需要不同的身份验证或加密方法，您必须更改配置以提供相应的用户凭据或安全套接字层 (SSL) 来运行 Web 服务。 有关详细信息，请参阅[SOAP Send Adapter](../core/soap-send-adapter.md)和[示例 TMA:HTTP 和 SOAP 适配器](../core/sample-tma-http-and-soap-adapters.md)。  
  
7.  单击**下一步**，然后**完成**以完成向导。  
  
## <a name="see-also"></a>请参阅  
 [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)   
 [创建 Web 端口](../core/creating-web-ports.md)