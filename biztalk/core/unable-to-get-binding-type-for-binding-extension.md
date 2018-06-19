---
title: 无法获取绑定类型绑定扩展 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b649f69b7503f345f212aa5f014ce7b256148d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973763"
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a>无法获取绑定扩展的绑定类型
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法获取绑定类型绑定扩展"{0}"。 如果 machine.config 已更新你的应用程序打开时，重新启动你的应用程序，以拾取更改。 验证 machine.config 中已注册绑定扩展|  
  
## <a name="explanation"></a>解释  
 WCF 自定义或 WCF CustomIsolated 传输的自定义绑定扩展是未正确配置。  
  
## <a name="user-action"></a>用户操作  
 要解决此错误，请执行以下一项或多项操作：  
  
-   确保**machine.config 文件**中 **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config**具有\< **bindingExtensions** \>正确配置的元素。  
  
-   在 Windows 资源管理器，转到 **%WinDir%\Assembly**，并确保正确安装的程序集实现的自定义绑定扩展。  
  
-   对于 WCF-Custom 适配器，在 BizTalk 管理控制台中，重新启动运行 WCF 传输的主机实例。  
  
-   对于 WCF-CustomIsolated 适配器，在 IIS 管理控制台中，重新启动托管 WCF 传输的应用程序池。  
  
-   打开并关闭 BizTalk 管理控制台（如果已打开）  
  
 有关详细信息，请参阅以下资源：  
  
-   [如何启用与 WCF 适配器 WCF 扩展点](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)