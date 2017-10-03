---
title: "不作为架构找不到序列化消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37897c04-650d-4695-846d-b8ba61365647
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b887d4a07d7a461278d3858289882a9ce441e9e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-cannot-be-serialized-as-the-schema-could-not-be-located"></a>消息无法序列化，因为无法定位架构
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|MessageSerializationFailureDueToMissingSchema|  
|消息正文|无法序列化消息，因为找不到架构 {0}。 架构未部署或者部署了多个副本。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法序列化传出的交换，因为该管道无法确定用于序列化交换所需的架构。 未部署架构或者部署了架构的多个副本。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
1.  如果尚未部署与交换关联的架构，请打开 Visual Studio，将架构添加到 BizTalk 项目，然后生成并部署项目。  
  
2.  如果已部署架构的多个副本，请打开 Visual Studio，除了保留一个与交换关联的架构的副本之外，取消部署所有其他副本。