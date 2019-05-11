---
title: ISA 段需要具有最小长度为 108 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57641445-cebb-4219-998d-54038d7ddf19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d511e0a50d610313bbe1c7ce4b3137c55ad0328
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329689"
---
# <a name="isa-segment-needs-to-have-a-minimum-length-of-108"></a>ISA 段需要具有最小长度为 108
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                               NseIsaSuffix1LFDescription                               |
|  消息正文   |          ISA 段需要具有最小长度为 108，实际上是 {0}           |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为交换中的 ISA 段不符合服务架构建立的位数 (X12ServiceSchema 或EdifactServiceSchema 在 BaseArtifacts.dll 中)。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保每个字段 （从为 ISA16 ISA01) 的 ISA 段中具有所需的最小数字位数。 可以通过打开 BizTalk Server 管理控制台; 看到最小位数打开 BizTalk 组节点、 应用程序节点、 BizTalk EDI 应用程序节点，然后架构节点;使用 ISA; 的根节点打开 Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema然后单击架构视图。