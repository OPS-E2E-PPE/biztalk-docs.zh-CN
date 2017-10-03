---
title: "当添加和删除项目时，会发生什么情况 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, deleting
- artifacts, creating
- deleting, artifacts
ms.assetid: 811166ba-3ff4-4224-9d84-a2f4ed31bf4d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 464964714993205ef65d5a67de3399935f79320f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a>当添加和删除项目时，会发生什么情况
本主题介绍将项目添加到应用程序时发生的情况。 您可以通过使用 BizTalk Server 管理控制台或 BTSTask 命令行工具，将基于文件的项目添加到应用程序中。 基于文件的项目包括以下类型：  
  
-   BizTalk 程序集  
  
-   非特定于 BizTalk 的 .NET 程序集  
  
-   绑定 (.xml) 文件  
  
-   COM 组件  
  
-   证书  
  
-   预处理和后处理脚本  
  
-   策略  
  
-   特别文件，如自述文件  
  
-   虚拟目录  
  
-   BAM 项目  
  
> [!NOTE]
>  发送端口、发送端口组、接收位置以及接收端口都不是基于文件的项目，不能添加到应用程序中。 必须在给定应用程序中创建这些项目。 然后，将它们移到其他应用程序中（如果需要）。 业务流程、架构、映射和管道都是作为包含它们的程序集的一部分来部署和托管的。  
  
 将项目添加到应用程序时，该项目将与 BizTalk 管理数据库中的应用程序相关联，并且基于文件的项目数据也将被添加到管理数据库中。 这样，您可以将一个 BizTalk 组中的应用程序和项目轻松传输到其他 BizTalk 组，因为您可以将该 BizTalk 组中项目的应用程序和数据从管理数据库导出到 .msi 文件中，然后将其导入其他 BizTalk 组的管理数据库中。  
  
 将绑定文件添加到应用程序时，可指定要应用绑定的目标部署环境。 与导入绑定文件不同，在添加绑定文件时，并不会应用其绑定。  
  
 向应用程序添加 BizTalk 程序集或 .NET 程序集时，如果指定此选项，则该程序集将会被添加到全局程序集缓存中。  
  
## <a name="see-also"></a>另请参阅  
 [会发生什么情况项目在应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)   
 [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)   
 [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)