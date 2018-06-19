---
title: 如何替换架构 |Microsoft 文档
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
ms.openlocfilehash: df444b8169d75408fe6e412135029ae2b051a6d2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25972627"
---
# <a name="how-to-replace-schemas"></a>如何替换架构
有时候您可能希望替换现有映射中的源架构或目标架构，例如从贸易合作伙伴接收到更新后的架构时。  
  
> [!NOTE]
>  BizTalk 映射器尝试维护被保留架构和被替换架构之间的所有现有链接。  
  
## <a name="replace-a-source-or-destination-schema"></a>将源或目标架构  
  
1.  右键单击源或目标架构树视图，然后选择 **替换架构**。  
  
    > [!NOTE]
    >  此外，还可以在键盘上按 Ctrl+M、Ctrl+S。 映射器键盘快捷键的完整列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
2.  在 **BizTalk 类型选取器** 对话框框中，展开 **架构** 节点在树中，选择适当的架构，然后选择 **确定**。  
  
     ![选择架构](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")  

    > [!TIP] 
    > **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，你可以调整大小类型选取器窗口以查看您的架构的完整名称。
      
     如果只有单个根存在在替换模式中，或已建立了根节点进行替换架构使用 **根引用** 属性 **架构** 节点，在相关的窗格中，打开替换架构并不需要执行步骤 3。  
  
3.  如果在目标架构中，存在多个根节点，并且没有根节点建立目标架构使用**根引用**属性**架构**节点，请在**根节点\<*源/目标*\>架构**对话框中，选择适当的根节点，然后选择**确定**。  
  
     此时，该替换架构将在相关窗格中打开。  
  
    > [!NOTE]
    >  替换架构时，如果未找到相关的记录/字段，则可能会丢失某些链接。 仅当你选择替换架构 **是** 上 **确认**  对话框。  
  
## <a name="see-also"></a>另请参阅  
 [管理项目中的映射](../core/managing-maps-within-projects.md)