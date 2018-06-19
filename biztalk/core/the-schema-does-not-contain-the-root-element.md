---
title: 架构不包含根元素 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efc33f2b-9e14-4d2e-8c8a-32b7696f80ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c485ce27fc3a1932d7de47557080712e46b654e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279301"
---
# <a name="the-schema-does-not-contain-the-root-element"></a>架构不包含根元素
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|SchemaCode102ENullRootElement|  
|消息正文|架构不包含根元素 {0}|  
  
## <a name="explanation"></a>解释  
 接收管道无法处理传入的消息或发送管道无法处理传出消息，因为用来验证消息的架构不包含根元素，该值指示此错误/警告/信息事件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，取消部署的文档架构，将根元素添加到架构，然后重新部署架构。