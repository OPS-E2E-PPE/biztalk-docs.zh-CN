---
title: 错误-根节点类名无效 |Microsoft Docs
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
ms.openlocfilehash: dca403fe7b99bf42f326485e6bd1788911d0dc32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388478"
---
# <a name="error---root-node-class-name-not-valid"></a>错误-根节点类名无效
**错误代码**  
  
 BEC2012  
  
 **说明**  
  
 **RootNode TypeName**之一的此架构中的根节点的属性无效。 因为的值**RootNode TypeName**属性使用的自动生成名称为C#类名必须是有效C#标识符且不能为保留的 BizTalk 关键字。  
  
 **用户执行任何操作**  
  
 选择所指示的根节点，然后在 Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，更改**RootNode TypeName**属性是一个有效的值C#标识符并不是保留的 BizTalk 关键字。