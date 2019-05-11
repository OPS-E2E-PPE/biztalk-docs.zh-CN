---
title: 方案：部署新的应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, applications
- applications, deploying
- deploying [applications], examples
- applications, examples
- examples, deploying
ms.assetid: 6d34a626-9fd4-4c33-a067-b66333eec01f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 932f8e8692b3f0d2061550bebbc7faf7a8175b2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308569"
---
# <a name="scenario-deploying-a-new-application"></a>方案：部署新的应用程序
本主题介绍的方案的应用程序部署到新环境，它具有之前未部署;例如，部署已在过渡环境到生产环境中配置的应用程序。  
  
 如中所述[应用程序部署过程](../core/the-application-deployment-process.md)，当你想要将应用程序从一个环境移动到另一个原因是，导出到.msi 文件的应用程序。 然后将.msi 文件导入新的环境中的 BizTalk 组。 此外将运行该应用程序的组中的计算机上安装应用程序。 它可以开始工作之前，必须将运行它，并还启动该应用程序的每台计算机上安装应用程序。  
  
 在下图中，Application1 从导入的.msi 文件到 BizTalk Group b。  
  
 ![BizTalk 应用程序部署](../core/media/deployapplication.gif "缓解")  
  
 这将导入项目到各种 BizTalk Server 数据库，如下所示：  
  
- BizTalk 程序集、.NET 程序集、 绑定、 绑定文件、 BAM 模板、 COM 组件、 证书和文本文件都添加到 BizTalk 管理数据库。  
  
- 策略和词汇添加到规则引擎数据库中。  
  
- BAM 模板和 BAM 定义文件将添加到 BAM 主导入数据库。  
  
  所有这些项目也是 BizTalk 管理数据库中与应用程序 1 相关联。  
  
  此外从.msi 文件在本地计算机上安装应用程序。 这将安装包含在.msi 文件中，按如下所示的各种项目：  
  
- 在 Internet 信息服务 (IIS) 元数据库中创建名为 VirtualDirectory，虚拟目录。  
  
- 将证书添加到本地证书存储中。  
  
- 文本文件和 COM 组件复制到本地文件系统中。  
  
- BizTalk 程序集和.NET 程序集添加到全局程序集缓存 (GAC) 中，如果已为它们选择此部署选项。  
  
- .NET 程序集和 COM 组件添加到 Windows 注册表中，如果已为它们选择该部署选项。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)