---
title: "如何从应用程序中删除项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, deleting
- applications, modifying
- applications, artifacts
- modifying, applications
- deleting, artifacts
ms.assetid: c528be0b-0b1a-4c5f-acd2-7355da91a253
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25d57c41311cef12a33685dcc4c8aacd85290b7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-an-artifact-from-an-application"></a>如何从应用程序中移除项目
从 BizTalk Server 数据库移除或删除项目，使之不再显示在管理控制台中或由 BTSTask ListApp 命令生成的应用程序的项目列表中。 此操作不会从 Windows 注册表、全局程序集缓存 (GAC)、虚拟目录或文件系统中移除项目（如果项目存在于这些位置中）。 如果是只存在于 BizTalk 管理数据库中的发送端口、发送端口组、接收端口和接收位置，此操作将完全删除项目。 有关背景信息，请参阅[什么发生时项目将添加和已删除](../core/what-happens-when-artifacts-are-added-and-removed.md)  
  
 根据项目类型，移除或删除项目对应用程序的运行有不同的影响。 有关移除或删除特定类型的项目的详细信息和说明，请参阅如下所述的适当主题：  
  
-   [如何从应用程序删除业务流程](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [如何删除发送端口](../core/how-to-delete-a-send-port.md)  
  
-   [如何删除发送端口组](../core/how-to-delete-a-send-port-group.md)  
  
-   [如何删除接收端口](../core/how-to-delete-a-receive-port.md)  
  
-   [如何删除接收位置](../core/how-to-delete-a-receive-location.md)  
  
-   [如何从应用程序和 BizTalk 组中删除策略](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [如何从应用程序中删除架构](../core/how-to-remove-a-schema-from-an-application.md)  
  
-   [如何从应用程序中删除地图](../core/how-to-remove-a-map-from-an-application.md)  
  
-   [如何从应用程序删除 BizTalk 程序集](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)  
  
-   [如何从应用程序删除预或后续处理脚本](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)  
  
-   [如何删除从应用程序的.NET 程序集、 证书或其他资源项目](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)  
  
## <a name="see-also"></a>另请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [RemoveResource 命令](../core/removeresource-command.md)