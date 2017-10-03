---
title: "如何添加标签和注释 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.functiod.general
ms.assetid: 58ff3a07-cbb6-4817-b301-d2b434ed2ad9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fccdeefa35f9abb5a0c3158dba518d524811c611
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-label-and-comment-a-functoid"></a>如何标签和注释 Functoid
标签和注释对于记录映射中 functoid 或链接的作用非常有用。 你可以使用**标签**属性，以提供 functoid 的名称。 **注释**属性使您能够提供有关 functoid，关于由它所执行的操作通常相关信息的其他信息。  
  
 下图显示了 functoid 的标签和注释。 functoid 从源架构中添加两个输入（Field1 和 Field3），并将结果输出到目标架构中的 Field4。 在此例中，functoid 标签是“Add Field1 and Field3”，注释是“The addition is an output to Field4”。  
  
 ![插入 functoid 标签和注释](../core/media/label.gif "Label_")  
  
 因为 functoid 可能是非常复杂的映射的一部分，所以适当地标记和另外提供相关注释非常重要。 您可以标记 functoid 和链接。 有关如何标记链接的信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)。  
  
 您可以通过以下方法标记和注释 functoid：  
  
-   通过使用**配置\<Functoid > Functoid**对话框。  
  
-   通过使用**属性**窗口。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a>从“配置”对话框标记和注释 functoid  
  
1.  右键单击你希望标签和注释，，然后单击 functoid**配置 Functoid 输入**。  
  
2.  在**配置\<Functoid > Functoid**对话框中，单击**标签和注释**选项卡。  
  
3.  输入以下信息，，然后单击**确定**。  
  
    -   **标签 –**输入新名称。  
  
        > [!IMPORTANT]
        >  最大允许的字符数为 256。 如果指定超过 256 个字符的字符串，则接受前 256 个字符和其余部分将被丢弃。  
  
    -   **注释 –** functoid 输入的备注。  
  
        > [!IMPORTANT]
        >  最大允许的字符数为 1024年。 如果指定超过 1024年个字符的字符串，则接受首先 1024年个字符，并丢弃其余部分。  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a>从“属性”窗口为 functoid 添加标签和注释  
  
1.  选择要添加标记和注释的 functoid。  
  
2.  在**属性**窗口中，输入以下信息，，然后单击**确定**。  
  
    -   **标签 –**输入新名称。  
  
        > [!IMPORTANT]
        >  最大允许的字符数为 256。 如果指定超过 256 个字符的字符串，则接受前 256 个字符和其余部分将被丢弃。  
  
    -   **注释 –** functoid 输入的备注。  
  
        > [!IMPORTANT]
        >  最大允许的字符数为 1024年。 如果指定超过 1024年个字符的字符串，则接受首先 1024年个字符，并丢弃其余部分。  
  
## <a name="see-also"></a>另请参阅  
 [编辑 Functoid 属性和输入的参数](../core/editing-functoid-properties-and-input-parameters.md)