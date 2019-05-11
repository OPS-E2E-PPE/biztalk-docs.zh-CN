---
title: 如何配置已安装的 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, configuring
- deploying, Web services
- Web services, deploying
ms.assetid: 5a281daa-9e1c-47b0-9002-66ea18ed6caf
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 096e21d2d7449e27f407bf7b286174c9ecb9cc34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340806"
---
# <a name="how-to-configure-the-installed-web-service"></a>如何配置已安装的 Web 服务
安装 Web 服务文件后，必须配置 BizTalk Server 以便接收来自 Web 服务的消息。  
  
### <a name="to-configure-the-web-service"></a>若要配置 Web 服务  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后右键单击你想要配置 Web 服务的应用程序。  
  
2.  指向**导入**，然后单击**绑定**。  
  
3.  在分发文件夹中，选择 BindingInfo.xml 文件，然后单击**确定**。  
  
4.  启动业务流程并启用接收位置。  
  
## <a name="see-also"></a>请参阅  
 [如何将绑定导入 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)   
 [在无 Visual Studio 的计算机上部署已发布 Web 服务](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)