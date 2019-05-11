---
title: 错误-嵌套的类名冲突 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37edc5012d2298e9516e766743b58f7d5448cf6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388622"
---
# <a name="error---nested-class-name-collision"></a>错误-嵌套的类名冲突
**错误代码**  

 BEC2017  

 **说明**  

 **类型名称**找到此架构的属性是与相同**RootNode TypeName**的其中一个架构中根节点的属性。 C#不允许嵌套的类具有相同的名称;因此这种情况将导致错误。  

 **用户执行任何操作**  

 您必须更改一个或两个相关的属性值，以便避免名称冲突。 请使用以下两种方法之一：  

- 在 Microsoft 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中更改**类型名称**属性设置为唯一的有效值。  

   \- 或 -  

- 选择所指示的根节点，然后在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，更改**RootNode TypeName**属性设置为唯一的有效值。
