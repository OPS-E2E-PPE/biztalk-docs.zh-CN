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
ms.openlocfilehash: 9f5e90c131e3ddb2190ab05597c92a5c2847a9fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387760"
---
# <a name="functoid-input-parameters"></a>Functoid 输入参数
使用 functoid 在映射中的一个重要方面正确配置 functoid 的输入的参数。 虽然输入参数的顺序并不重要的所有 functoid (如**加法**将显示该 functoid 将一个预期从添加的属性相关联)，许多 functoid 必须具有其输入的参数指定正确的顺序。  
  
## <a name="create-input-paramaters"></a>创建输入的参数
 有两种方法可以创建指向 functoid 的参数的输入：  
  
- 通过创建到左侧和右侧显示的网格页的 functoid 的链接。 创建链接的顺序是关联的输入的参数传递到 functoid 的顺序。  
  
- 通过打开**配置\<Functoid\> Functoid**对话框并添加新的输入参数。 此对话框中也非常重要的因为它允许重排 functoid 的输入的参数，以便它们以正确的顺序。 例如，如果不正确的顺序创建指向 functoid 的链接，你可以转到此对话框中，进行必要的更正。 配置 functoid 的输入的参数的分步说明，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。  
  
  必须使用**配置\<Functoid\> Functoid**对话框可以创建常数输入的参数。  
  
  当某个链接或 functoid 使用提供的标签**标签**属性在属性窗口中选择链接或 functoid 时，将在显示该标签**配置\<Functoid\>Functoid**对话框而不是 schema 节点的相应 XPath 或用作输入参数的 functoid 的名称。 使用标签，它将得更轻松地标识参数，并进入正确的顺序。  
  
  有关 functoid 输入参数的正确顺序的权威信息，请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>请参阅  
 [配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)   
 [配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)   
 [配置“表循环”和“表提取程序”Functoid](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)