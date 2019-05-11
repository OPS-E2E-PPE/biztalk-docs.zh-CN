---
title: 添加和删除项目时，会发生什么情况 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, deleting
- artifacts, creating
- deleting, artifacts
ms.assetid: 811166ba-3ff4-4224-9d84-a2f4ed31bf4d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbda3968ec4337ccf3b00bf1b1698d73c9232c47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401079"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a>添加和删除项目时，会发生什么情况
本主题介绍当将项目添加到应用程序时，会发生什么情况。 通过使用 BizTalk Server 管理控制台或 BTSTask 命令行工具，可以向应用程序添加基于文件的项目。 基于文件的项目包括以下类型：  
  
-   BizTalk 程序集  
  
-   不是特定于 BizTalk 的.NET 程序集  
  
-   绑定 (.xml) 文件  
  
-   COM 组件  
  
-   证书  
  
-   预处理和后处理脚本  
  
-   策略  
  
-   特别文件，如自述文件  
  
-   虚拟目录  
  
-   BAM 项目  
  
> [!NOTE]
>  发送端口、 发送端口组、 接收位置和接收端口都不是基于文件的项目，不能添加到应用程序。 必须创建一个给定的应用程序中的这些项目。 你可以然后将它们移动到不同的应用程序，如果你想。 业务流程、 架构、 映射和管道是所有部署和管理包含它们的程序集的一部分。  
  
 当将项目添加到应用程序时的项目是与 BizTalk 管理数据库中的应用程序相关联和基于文件的项目的数据添加到管理数据库。 因此，您可以轻松地传输应用程序和项目从一个 BizTalk 组到另一个，因为您可以将应用程序和其项目的数据导出到.msi 文件从管理数据库，然后将其导入的管理数据库中不同的 BizTalk 组。  
  
 当向应用程序添加绑定文件时，可以指定在其中你想要应用绑定的目标部署环境。 与导入绑定文件，不同时添加绑定文件，则不应用其绑定。  
  
 当向应用程序添加 BizTalk 程序集或.NET 程序集时，该程序集添加到全局程序集缓存，如果指定此选项。  
  
## <a name="see-also"></a>请参阅  
 [对项目采取的应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)   
 [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)   
 [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)