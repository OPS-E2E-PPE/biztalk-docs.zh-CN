---
title: 管理资源 |Microsoft Docs
description: 使用 btstask 或 BizTalk 管理适用于程序集、 脚本、 证书、 绑定文件和 BizTalk Server 中的更多
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b478ef2e-1363-4c2c-a4b7-6a582a6b33a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a26a0afc6832dfa4c8401442dc000262dab3aec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380219"
---
# <a name="manage-resources"></a>管理资源

## <a name="overview"></a>概述
在本部分中的主题提供有关如何使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理 BizTalk Server 资源部署到 BizTalk 组后的说明。 资源包括以下类型的项目：  
  
-   BizTalk 程序集  
  
-   预处理和后处理脚本  
  
-   .NET 程序集  
  
-   COM 组件  
  
-   证书  
  
-   特别文件  
  
-   BAM 定义  
  
-   绑定文件  
  
-   虚拟目录  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
> 
> [!NOTE]
>  不要将具有相同的名称，不区分大小写，多个资源添加到 BizTalk Server 组。 不支持将多个具有相同名称的资源添加到 BizTalk Server 组，即使 BizTalk Server 管理数据库存储配置为使用二进制排序规则并区分大小写的 SQL 服务器上。  
  
## <a name="next-steps"></a>后续步骤
  
-   [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)  
  
-   [管理预处理脚本和后期处理脚本](../core/managing-pre-and-post-processing-scripts.md)  
  
-   [管理 .NET 程序集、证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)  
  
-   [刷新资源](../core/how-to-refresh-a-resource.md)