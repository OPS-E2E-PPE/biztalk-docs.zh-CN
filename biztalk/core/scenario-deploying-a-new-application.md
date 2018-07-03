---
title: 方案： 部署新的应用程序 |Microsoft Docs
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
ms.openlocfilehash: c706e990154f43f264e3c529a8ee7ce59efcc166
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986230"
---
# <a name="scenario-deploying-a-new-application"></a>方案： 部署新的应用程序
本主题说明了将应用程序部署到一个以前从未部署它的新环境的方案；例如，将已在过渡环境中配置的应用程序部署到生产环境。  
  
 如中所述[应用程序部署过程](../core/the-application-deployment-process.md)，当你想要将应用程序从一个环境移动到另一个原因是，导出到.msi 文件的应用程序。 然后，可在新环境中将 .msi 文件导入 BizTalk 组。 您还应该将该应用程序安装在将运行它的组中的计算机上。 要使该应用程序正常运行，必须将其安装在将运行它的计算机上，并且启动它。  
  
 在下图中，Application1 从 .msi 文件导入 BizTalk Group B。  
  
 ![BizTalk 应用程序部署](../core/media/deployapplication.gif "缓解")  
  
 此过程按下述方式将项目导入各种 BizTalk Server 数据库：  
  
- BizTalk 程序集、.NET 程序集、绑定、绑定文件、BAM 模板、COM 组件、证书和文本文件都将添加到 BizTalk 管理数据库。  
  
- 策略和词汇添加到规则引擎数据库。  
  
- BAM 模板和 BAM 定义文件都添加到 BAM 主导入数据库。  
  
  所有这些项目还要与 BizTalk 管理数据库中的 Application1 相关联。  
  
  应用程序还会从 .msi 文件安装在本地计算机上。 此过程按下述方式安装 .msi 文件中包括的各种项目：  
  
- 虚拟目录（即命名的 VirtualDirectory）在 Internet 信息服务 (IIS) 数据库中创建。  
  
- 证书添加到本地证书存储区。  
  
- 文本文件和 COM 组件复制到本地文件系统。  
  
- BizTalk 程序集和 .NET 程序集添加到全局程序集缓存 (GAC)（如果已为它们选择此部署选项）。  
  
- .NET 程序集和 COM 组件添加到 Windows 注册表（如果已为它们选择该部署选项）。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)