---
title: 不支持的功能组版本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715e6585-a07a-4060-a15b-0c9603fbef19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ce3ff1cfb525b98e646c31180aa6668d3173cb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997710"
---
# <a name="functional-group-version-not-supported"></a>不支持功能组版本
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                        X12FaGroupVersionNotSupportedDescription                        |
|  消息正文   |                         不支持功能组版本                         |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 BizTalk Server 不支持功能组的段 GS08 中的版本号。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 BizTalk Server 支持交换的所有功能中段 GS08 的每个实例中的版本号，然后重新发送交换。 请注意，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 产品帮助的“EDI 文档架构支持”主题中列出了 BizTalk Server 致辞后的标准版本。