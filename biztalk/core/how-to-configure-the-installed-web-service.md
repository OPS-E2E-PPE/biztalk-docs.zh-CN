---
title: "如何配置已安装的 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, configuring
- deploying, Web services
- Web services, deploying
ms.assetid: 5a281daa-9e1c-47b0-9002-66ea18ed6caf
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f54d5fd99bfa9f5a7440202848c4d43259d0a42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-installed-web-service"></a>如何配置已安装的 Web 服务
安装 Web Services 文件之后，您必须将 BizTalk Server 配置为接收来自 Web Services 的消息。  
  
### <a name="to-configure-the-web-service"></a>配置 Web Services  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后右键单击你想要配置 Web 服务应用程序。  
  
2.  指向**导入**，然后单击**绑定**。  
  
3.  在分发文件夹中，选择 BindingInfo.xml 文件，然后单击**确定**。  
  
4.  启动业务流程并启用接收位置。  
  
## <a name="see-also"></a>另请参阅  
 [如何将绑定导入 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)   
 [部署非 Visual Studio 计算机上的发布的 Web 服务](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)