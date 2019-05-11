---
title: 如何替换架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 104e60d3-1303-4e56-b13a-c10ab14ba383
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d71c2c4231d3de506e3efc472281cac31f2b4b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334930"
---
# <a name="how-to-replace-schemas"></a>如何替换架构
可能存在你想要替换现有映射，例如当您从贸易合作伙伴收到更新的架构中的源或目标架构。  
  
> [!NOTE]
>  BizTalk 映射器尝试维护保留的架构与替换的架构之间的所有现有链接。  
  
## <a name="replace-a-source-or-destination-schema"></a>替换为源或目标架构  
  
1. 右键单击源或目标架构树视图，然后选择**替换为架构**。  
  
   > [!NOTE]
   >  或者，您还可以按 CTRL + M、 CTRL + S 键盘。 有关映射器键盘快捷方式的完整列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
2. 在中**BizTalk 类型选取器**对话框框中，展开**架构**节点在树中，选择相应的架构，并选择**确定**。  
  
    ![选择架构](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")  

   > [!TIP]
   > **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，可以调整大小类型选取器窗口以查看您的架构的完整名称。
      
    如果仅替换架构中存在单个根或根节点已经为替换架构使用建立**根引用**的属性**架构**节点，会打开该替换架构在相关窗格中，您不需要执行步骤 3。  
  
3. 如果目标架构中存在多个根节点，并且已使用目标架构建立任何根节点**根引用**的属性**架构**节点，请在**根节点\<*源/目标*\>架构**对话框中，选择相应的根节点，然后选择**确定**。  
  
    该替换架构将在相关窗格中打开。  
  
   > [!NOTE]
   >  替换架构时，如果未找到相关的记录字段，某些链接可能会丢失。 只能在选择时，才替换架构**是**上**确认**对话框。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的映射](../core/managing-maps-within-projects.md)