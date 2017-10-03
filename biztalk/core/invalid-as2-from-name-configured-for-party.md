---
title: "无效的 AS2-从配置为当事方名称 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cde739bd-f6f7-4e4a-8f02-9a99e9d82fc9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c370476eeccc085783c761cefb41a52eead8e208
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-from-name-configured-for-party"></a>为参与方配置的 AS2-From 名称无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|InvalidAS2FromNameConfiguredError|  
|消息正文|无效的 AS2-从配置为当事方名称： {0} 值： {1}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 编码器或解码器无法处理 AS2 消息，因为为标识的参与方配置的 AS2-From 标头不符合 AS2 RFC 4130 中的规范。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保为参与方配置的 AS2-From 标头符合 AS2 RFC 4130 第 6.2 节中的规范，然后重新发送消息。