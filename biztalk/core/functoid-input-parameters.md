---
title: Functoid 输入参数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4a93d827a5f58401bb9b8fcdf9727c2a61767e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008094"
---
# <a name="functoid-input-parameters"></a>Functoid 输入参数
在映射中使用 functoid 的关键是正确配置 functoid 的输入参数。 虽然输入参数的顺序并不重要的所有 functoid (如**加法**将显示该 functoid 将一个预期从添加的属性相关联)，许多 functoid 必须具有其输入的参数指定正确的顺序。  
  
## <a name="create-input-paramaters"></a>创建输入的参数
 有两种为 functoid 创建输入参数的方法：  
  
- 通过在显示的网格页中创建指向左侧的 functoid 的链接。 链接的创建顺序即为将关联的输入参数传递给 functoid 的顺序。  
  
- 通过打开**配置\<Functoid\> Functoid**对话框并添加新的输入参数。 由于此对话框允许重排 functoid 的输入参数的顺序以确保顺序正确，因此该对话框也很重要。 例如，如果按错误的顺序创建指向 functoid 的链接，则可以转到此对话框进行必要的更正。 配置 functoid 的输入的参数的分步说明，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。  
  
  必须使用**配置\<Functoid\> Functoid**对话框可以创建常数输入的参数。  
  
  当某个链接或 functoid 使用提供的标签**标签**属性在属性窗口中选择链接或 functoid 时，将在显示该标签**配置\<Functoid\>Functoid**对话框而不是 schema 节点的相应 XPath 或用作输入参数的 functoid 的名称。 使用标签可以更容易地标识参数并将参数按正确顺序排列。  
  
  有关 functoid 输入参数的正确顺序的权威信息，请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>请参阅  
 [配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)   
 [配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)   
 [配置“表循环”和“表提取程序”Functoid](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)