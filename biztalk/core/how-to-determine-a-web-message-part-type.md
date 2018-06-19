---
title: 如何确定 Web 消息部件类型 |Microsoft 文档
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
ms.openlocfilehash: 6102e39eb38e919c68405ae18bebde0b46c0b053
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25970539"
---
# <a name="how-to-determine-a-web-message-part-type"></a>如何确定 Web 消息部分类型
你可以使用给定 Web 消息类型的“属性”窗口确定 Web 消息部分类型是基元 .NET 类型还是架构类型。  
  
### <a name="to-determine-a-web-message-part-type"></a>确定 Web 消息部分类型  
  
1.  与打开，请在业务流程 **视图** 菜单上，单击 **其他窗口**,，然后单击 **业务流程视图**。  
  
2.  展开 **多部分消息类型** 节点，然后展开 Web 消息类型。  
  
3.  选择消息部分。  
  
     开始为 Web 消息一部分签名 **\<*项目默认命名空间*\>。\<*Web 引用名称*\>。引用。\<*架构根*\>** 是架构类型。  **\<*架构根*\>** 类型的一部分是构造 Web 消息部分的 Web 引用架构的根元素。 否则，消息一部分签名都是基元的.NET 类型如**System.String**或**System.Int32**。  
  
## <a name="see-also"></a>另请参阅  
 [构造 Web 消息](../core/constructing-web-messages.md)