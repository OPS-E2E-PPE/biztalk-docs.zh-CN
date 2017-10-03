---
title: "无法创建 AS2 EDIINT MIC 表中的条目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1c75d70-e39e-4465-b32b-db646c059c9b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c51cac2861fabaf8fc50269623130c90f3d445b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a>无法在 AS2 EDIINT MIC 表中创建条目
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|AS2MicDataStoreCreateEntryError|  
|消息正文|无法在 AS2 EDIINT MIC 表中创建条目。 这可能是由于在该表中写入了重复的 AS2-From、AS2-To 和 MessageID 组合。  错误： {0}|  
  
## <a name="explanation"></a>解释  
 此错误表明数据库连接出现问题或者数据库表中已存在行密钥。 完整的错误消息应该提供有关插入操作失败的原因的信息。 收到 MDN 后已将表中的条目删除（无论成功还是失败），因此收到 MDN 后应该从不会发生此错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请检查有关插入操作失败的原因的信息的完整的错误消息。 在 SQL 中，在 EDIINT_MIC 表中，确定是否有重复的 AS2-从和 AS2-到 MessageID 组合。 如果出现这种情况，请将它们删除。