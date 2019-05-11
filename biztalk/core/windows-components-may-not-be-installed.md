---
title: 可能未安装 Windows 组件 |Microsoft Docs
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
ms.openlocfilehash: 79e9855a3e9719f1a95801683a7b72da9c5ce86b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240295"
---
# <a name="windows-components-may-not-be-installed"></a>可能未安装 Windows 组件
## <a name="details"></a>详细信息  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| 产品版本 |                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    事件 ID     |                                                                   0                                                                    |
|  事件源   |                                                                   0                                                                    |
|    组件    |                                                                   0                                                                    |
|  符号名称  |                                                                   0                                                                    |
|  消息正文   | 可能未安装以下 Windows 组件：应用程序服务器-&gt; Internet 信息服务 (IIS)-&gt;公共文件。 |

## <a name="explanation"></a>解释  
 尝试发布而无需 Internet 信息服务 (IIS) 安装在本地计算机上时，将发生此错误。  

## <a name="user-action"></a>用户操作  
 对于 Windows 7 和 Windows Vista SP2，安装 IIS 的本地计算机策略和配置 IIS，如下所示：  

1. 单击**启动**，单击**控制面板**，然后单击**程序**。  

2. 单击**打开或关闭打开的 Windows 功能**。 将显示 Windows 功能向导。  

3. 若要添加，请检查 IIS 组件。  

   有关[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]和[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，安装 IIS 的本地计算机策略和配置 IIS，如下所示：  

4. 单击**启动**，单击**控制面板**，然后单击**管理工具**。  

5. 单击**服务器管理器**。 服务器管理器窗口中显示。  

6. 单击**添加角色**，显示添加角色向导。  

7. 若要添加，请选择 IIS 组件。
