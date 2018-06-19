---
title: 如何作为数据源使用的.NET 程序集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: 14dbec48-acc9-4c3c-bd7f-737dabf29543
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa56370cf894d0d18a36320ca97c4d028fee487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256629"
---
# <a name="how-to-use-a-net-assembly-as-a-data-source"></a>如何将 .NET 程序集用作数据源
您可以指定 .NET 程序集作为数据源。 随后可以从该程序集，选择一个类或类成员，并将其拖到词汇定义或规则。  
  
### <a name="to-specify-a-net-assembly-as-a-data-source"></a>指定 .NET 程序集作为数据源  
  
1.  在事实浏览器窗口中，单击 **.NET 类**选项卡。  
  
2.  右键单击**模块**节点。  
  
3.  从可用程序集中选择 .NET 程序集。  
  
    > [!NOTE]
    >  可用程序集必须位于全局程序集缓存 (GAC) 中。 业务规则编辑器加载.NET 程序集的.NET 程序集在浏览时**事实数据资源管理器**窗口中或在 **.NET 类或类成员定义**页**词汇定义**窗口。  如果您在 GAC 中更新该程序集，则关闭业务规则编辑器然后重新启动它，以便加载已更新的 .NET 程序集。 业务规则编辑器并不自动刷新该程序集。  
  
     ![事实和定义树浏览器的屏幕截图。] (../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")