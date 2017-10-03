---
title: "Functoid 输入参数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97919e3afcb6277f33aa65e6e8e6370aecb23844
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="functoid-input-parameters"></a>Functoid 输入参数
在映射中使用 functoid 的关键是正确配置 functoid 的输入参数。 输入参数的顺序并不重要的所有 functoid 时 (如**添加**functoid，后者将显示相同将从添加预期的属性相关联)，许多 functoid 必须具有其输入的参数按正确顺序指定。  
  
## <a name="create-input-paramaters"></a>创建输入的参数
 有两种为 functoid 创建输入参数的方法：  
  
-   通过在显示的网格页中创建指向左侧的 functoid 的链接。 链接的创建顺序即为将关联的输入参数传递给 functoid 的顺序。  
  
-   通过打开**配置\<Functoid > Functoid**对话框，并添加新输入参数。 由于此对话框允许重排 functoid 的输入参数的顺序以确保顺序正确，因此该对话框也很重要。 例如，如果按错误的顺序创建指向 functoid 的链接，则可以转到此对话框进行必要的更正。 有关配置 functoid 的输入的参数的分步说明，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。  
  
 必须使用**配置\<Functoid > Functoid**对话框创建是常量的输入的参数。  
  
 为链接或 functoid 使用提供标签时**标签**该标签将显示在选择链接或 functoid 时的属性窗口中的属性，**配置\<Functoid > Functoid**对话框而不是一个架构节点中，相应 XPath 或 functoid 用作输入参数的名称。 使用标签可以更容易地标识参数并将参数按正确顺序排列。  
  
 有关 functoid 输入参数的正确顺序的权威信息，请参阅**Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
 [配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)   
 [配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)   
 [配置表循环和表提取程序 Functoid](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)