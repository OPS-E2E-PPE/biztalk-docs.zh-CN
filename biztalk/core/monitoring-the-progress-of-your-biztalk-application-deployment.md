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
ms.openlocfilehash: 39f45fe2456286c4fb05c86f7b18b2d4c48a8665
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394402"
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a>监视 BizTalk 应用程序部署的进度
你可以监视 BizTalk 应用程序部署在两个方面的进度：  
  
- **BizTalk 安装日志**:可以参考 BizTalk Server 生成的安装日志。 安装日志文件位于 %SystemDrive%\Documents and 设置\\<*当前用户*\>\Application Data\Microsoft\BizTalk server\deployment。  
  
- **本地事件日志**:您可以跟踪本地事件日志中的安装的进度。 因此，你可以基于每个服务器跟踪自定义安装操作。  
  
- **Windows 安装程序日志**:Microsoft Windows 安装程序会创建记录的自定义操作的操作在本地计算机上的日志文件。 可以使用 msiexec 命令的 /log 选项指定此日志文件。 有关详细信息，请参阅 Windows 安装程序的文档。  
  
> [!IMPORTANT]
>  部署或取消部署属性架构可能暴露敏感数据，并随后暴露在跟踪的敏感信息。 每当部署或已取消部署包含属性架构的程序集时，事件查看器记录的事件在 Windows 应用程序事件日志中。 应检查这些消息，以确保所有程序集部署活动均符合你的策略的任何敏感数据在事件日志。 (部署为事件日志中生成的消息："用户"{1}"已部署程序集"{0}"包含属性架构"。 取消部署事件日志中生成的消息为："用户"{1}"已取消部署程序集"{0}"包含属性架构"。)  
  
## <a name="see-also"></a>请参阅  
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)