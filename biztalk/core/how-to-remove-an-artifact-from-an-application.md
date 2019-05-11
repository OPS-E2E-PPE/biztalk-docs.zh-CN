---
title: 如何从应用程序中删除项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, deleting
- applications, modifying
- applications, artifacts
- modifying, applications
- deleting, artifacts
ms.assetid: c528be0b-0b1a-4c5f-acd2-7355da91a253
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c9c891b297ceb336d14f8964dd71d71b4fe28af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384312"
---
# <a name="how-to-remove-an-artifact-from-an-application"></a>如何从应用程序中删除项目
移除或删除项目将其从删除 BizTalk Server 数据库，以便它不会再出现在管理控制台或 BTSTask ListApp 命令生成的应用程序的项目列表中。 如果它存在于这些位置中，它不会从 Windows 注册表、 全局程序集缓存 (GAC)、 虚拟目录或文件系统中，删除该项目。 在发送端口的情况下发送端口组、 接收端口，以及完全接收位置，只存在于 BizTalk 管理数据库，此操作删除该项目。 有关背景信息，请参阅[什么发生时项目将被添加并将其删除](../core/what-happens-when-artifacts-are-added-and-removed.md)  
  
 移除或删除项目可以具有不同的应用程序，具体取决于项目类型的运行情况的影响。 有关详细信息和移除或删除特定类型的项目的说明，请参阅相应的主题中，按如下所示：  
  
-   [如何从应用程序中删除业务流程](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [如何删除发送端口](../core/how-to-delete-a-send-port.md)  
  
-   [如何删除发送端口组](../core/how-to-delete-a-send-port-group.md)  
  
-   [如何删除接收端口](../core/how-to-delete-a-receive-port.md)  
  
-   [如何删除接收位置](../core/how-to-delete-a-receive-location.md)  
  
-   [如何从应用程序和 BizTalk 组中删除策略](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [如何从应用程序中删除架构](../core/how-to-remove-a-schema-from-an-application.md)  
  
-   [如何从应用程序中删除映射](../core/how-to-remove-a-map-from-an-application.md)  
  
-   [如何从应用程序删除 BizTalk 程序集](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)  
  
-   [如何从应用程序删除预处理或后处理脚本](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)  
  
-   [如何从应用程序中删除.NET 程序集、 证书或其他资源项目](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [RemoveResource 命令](../core/removeresource-command.md)