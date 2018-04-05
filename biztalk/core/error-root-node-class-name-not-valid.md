---
title: 错误-根节点类名无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootNodeClassNameNotValid
ms.assetid: 48b4f7e4-8c20-4e94-86be-1425ea62f8c5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff170609ef37b1d7f2b00a4d4ca3952b89eef9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---root-node-class-name-not-valid"></a>错误-根节点类名称无效
**错误代码**  
  
 BEC2012  
  
 **说明**  
  
 **RootNode TypeName**之一的此架构中的根节点的属性无效。 因为的值**RootNode TypeName**属性将用作自动生成的 C# 类名称的名称，它必须是有效的 C# 标识符，并且不能是保留的 BizTalk 关键字。  
  
 **用户执行任何操作**  
  
 选择指定的根节点，然后在 Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，更改**RootNode TypeName**属性的值是有效的 C# 标识符而不是保留的 BizTalk 关键字。