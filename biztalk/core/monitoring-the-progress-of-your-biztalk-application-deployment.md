---
title: 监视 BizTalk 应用程序部署的进度 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, deploying
- applications, monitoring
- deploying [applications], monitoring
- monitoring, applications
ms.assetid: a69a8288-0203-440f-9805-52786525e193
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07beea810ff64c807685b8170009d5204ede1af7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001150"
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a>监视 BizTalk 应用程序部署的进度
您可以用两种方式 BizTalk 应用程序部署的进度：  
  
- **BizTalk 安装日志**： 您可以参阅 BizTalk Server 生成的安装日志。 安装日志文件位于 %SystemDrive%\Documents and 设置\\<*当前用户*\>\Application Data\Microsoft\BizTalk server\deployment。  
  
- **本地事件日志**： 你可以跟踪的本地事件日志中的安装进度。 因此，您可以在每个服务器基础上跟踪自定义安装操作。  
  
- **Windows 安装程序日志**: Microsoft Windows 安装程序创建自定义操作的操作记录在本地计算机上的日志文件。 您可以使用 msiexec 命令的 /log 选项指定此日志文件。 有关详细信息，请参阅 Windows Installer 的文档。  
  
> [!IMPORTANT]
>  部署或取消部署属性架构可能会暴露敏感数据，进而在跟踪中暴露敏感信息。 只要部署或取消部署包含属性架构的程序集，事件查看器就会在 Windows 应用程序事件日志中记录该事件。 您应该在事件日志中检查这些消息，以确保所有程序集部署活动均符合您的敏感数据策略。 (部署为事件日志中生成的消息:"用户"{1}"已部署程序集"{0}"包含属性架构"。 取消部署为事件日志中生成的消息:"用户"{1}"已取消部署程序集"{0}"包含属性架构"。)  
  
## <a name="see-also"></a>请参阅  
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)