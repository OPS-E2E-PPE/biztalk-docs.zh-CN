---
title: 如何确定 Web 消息部分类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web messages, message types
- Web services, Web messages
- Web messages, parts
ms.assetid: bdd1f604-ec35-41e3-b5a8-1e0ad0193eff
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb191f72612d364d69600f0d6e22505b6196b056
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338616"
---
# <a name="how-to-determine-a-web-message-part-type"></a>如何确定 Web 消息部分类型
您可以确定 Web 消息部分类型是基元.NET 类型还是架构类型通过针对给定的 Web 消息类型属性窗口。  
  
### <a name="to-determine-a-web-message-part-type"></a>若要确定 Web 消息部分类型  
  
1.  与打开，请在业务流程**视图**菜单上，单击**其他 Windows**，然后单击**业务流程视图**。  
  
2.  展开**多部分消息类型**节点，然后展开 Web 消息类型。  
  
3.  选择消息部分。  
  
     最初为 Web 消息部分签名**\<*项目默认命名空间*\>。\<*Web 引用名*\>。引用。\<*架构根*\>** 是架构类型。 **\<*架构根*\>** 类型的一部分是构造 Web 消息部分的 Web 引用架构的根元素。 否则，消息部分签名为基元.NET 类型如**System.String**或**System.Int32**。  
  
## <a name="see-also"></a>请参阅  
 [构造 Web 消息](../core/constructing-web-messages.md)