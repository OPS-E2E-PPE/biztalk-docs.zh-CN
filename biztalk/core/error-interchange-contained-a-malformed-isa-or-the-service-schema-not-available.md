---
title: 交换包含格式不正确的 ISA 或服务架构不可用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d285f6-26fb-4a3b-a959-a17623321b20
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce469b25a2ba15c3038ea9079c3f22fc4f8c0c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010710"
---
# <a name="the-interchange-contained-a-malformed-isa-or-the-service-schema-was-not-available"></a>交换包含格式不正确的 ISA 或服务架构不可用
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 产品版本 |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    事件 ID     |                                                         -                                                          |
|  事件源   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI               |
|    组件    |                                                     EDI 引擎                                                     |
|  符号名称  |                                                 MalformedIsaError                                                  |
|  消息正文   | 交换包含格式不正确的 ISA 或服务架构不可用，因此它被完全拒绝 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中的 ISA 或 IEA 段不符合 X12ServiceSchema，或者未部署 X12ServiceSchema（在 BaseArtifacts.dll 中）。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   让交换的发送方更改 ISA 和 IEA 段，以便这些段符合 X12ServiceSchema。  
  
-   确保 BaseArtifacts.dll 包含 X12ServiceSchema 并且已部署。 可以通过打开 BizTalk Server 管理控制台，打开“BizTalk EDI 应用程序”节点，然后“架构”节点并验证是否列出了 X12ServiceSchema 来执行该操作。