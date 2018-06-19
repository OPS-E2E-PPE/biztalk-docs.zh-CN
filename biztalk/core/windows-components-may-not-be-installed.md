---
title: 可能未安装 Windows 组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc78ac0a-ee21-4633-afb3-1357efd29903
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506f9c310a75c9f65564e4feb047157731bafa66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289853"
---
# <a name="windows-components-may-not-be-installed"></a>可能未安装 Windows 组件
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|以下 Windows 组件可能未安装： 应用程序服务器-&gt; Internet 信息服务 (IIS)-&gt;公共文件。|  
  
## <a name="explanation"></a>解释  
 尝试发布时如果在本地计算机上未安装 Internet 信息服务 (IIS)，则会出现此错误。  
  
## <a name="user-action"></a>用户操作  
 对于 Windows 7 和 Windows Vista SP2，请在本地计算机上安装 IIS 并按以下方式配置 IIS：  
  
1.  单击**启动**，单击**控制面板**，然后单击**程序**。  
  
2.  单击**打开或关闭 Windows 功能**。 随即显示 Windows 功能向导。  
  
3.  若要添加 IIS 组件，请选中该组件。  
  
 对于 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 和 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请在本地计算机上安装 IIS 并按以下方式配置 IIS：  
  
1.  单击**启动**，单击**控制面板**，然后单击**管理工具**。  
  
2.  单击**服务器管理器**。 随即显示“服务器管理器”窗口。  
  
3.  单击**添加角色**，添加角色向导将显示。  
  
4.  若要添加，请选择 IIS 组件。