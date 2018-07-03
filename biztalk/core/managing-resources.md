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
ms.openlocfilehash: d9aad282dfb444c2947afca3cefc0a96cd806826
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015110"
---
# <a name="manage-resources"></a>管理资源

## <a name="overview"></a>概述
本部分中的主题介绍在将 BizTalk Server 资源部署到 BizTalk 组中之后如何使用 BizTalk Server 管理控制台或 BTSTask 命令行工具管理 BizTalk Server 资源。 资源包括以下几种类型的项目：  
  
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
>  在任何情况下都不要向 BizTalk Server 组中添加具有相同名称的多个资源。 不支持向 BizTalk Server 组中添加具有相同名称的多个资源，即使 BizTalk Server 管理数据库存储在配置成使用二进制排序规则并区分大小写的 SQL Server 上也如此。  
  
## <a name="next-steps"></a>后续步骤
  
-   [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)  
  
-   [管理预处理脚本和后期处理脚本](../core/managing-pre-and-post-processing-scripts.md)  
  
-   [管理 .NET 程序集、证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)  
  
-   [刷新资源](../core/how-to-refresh-a-resource.md)