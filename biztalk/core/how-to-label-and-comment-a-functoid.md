---
title: 如何标签和注释 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.general
ms.assetid: 58ff3a07-cbb6-4817-b301-d2b434ed2ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db30ca1b7bee06c633245e05808ad521b27e51d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384867"
---
# <a name="how-to-label-and-comment-a-functoid"></a>如何标签和注释 Functoid
标签和注释有助于记录 functoid 或映射中的链接的用途。 可以使用**标签**属性为 functoid 提供一个名称。 **注释**属性使您能够提供有关该 functoid，有关它所执行的操作通常相关信息的其他信息。  
  
 下图显示的标签和注释 functoid 的。 该 functoid 将源架构中添加两个输入 （Field1 和 Field3），并将结果输出到 Field4 目标架构中。 在此示例中，functoid 标签是"Add Field1 and Field3"，注释是"The addition is an output to Field4"。  
  
 ![插入 functoid 标签和注释](../core/media/label.gif "Label_")  
  
 因为 functoid 可能是非常复杂的映射的一部分，很重要，所以适当地标记和另外提供相关注释。 可以标记 functoid 和链接。 有关如何标记链接的信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)。  
  
 可以标记和注释 functoid 按以下方式：  
  
-   通过使用**配置\<Functoid\> Functoid**对话框。  
  
-   通过使用**属性**窗口。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a>添加标记和注释 functoid 从配置对话框  
  
1.  右键单击您要添加标记和注释，然后单击该 functoid**配置 Functoid 输入**。  
  
2.  在中**配置\<Functoid\> Functoid**对话框中，单击**标签和注释**选项卡。  
  
3.  输入以下信息，并单击**确定**。  
  
    -   **标签-** 输入新名称。  
  
        > [!IMPORTANT]
        >  最大允许的字符数为 256。 如果指定超过 256 个字符的字符串，则接受前 256 个字符，并丢弃剩余部分。  
  
    -   **注释-** functoid 输入注释。  
  
        > [!IMPORTANT]
        >  最大允许的字符数为 1024年。 如果指定超过 1024年个字符的字符串，则接受前面 1024 个字符，并丢弃剩余部分。  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a>添加标记和注释 functoid 从属性窗口  
  
1.  选择要添加标记和注释的 functoid。  
  
2.  在中**属性**窗口中，输入以下信息，然后单击**确定**。  
  
    -   **标签-** 输入新名称。  
  
        > [!IMPORTANT]
        >  最大允许的字符数为 256。 如果指定超过 256 个字符的字符串，则接受前 256 个字符，并丢弃剩余部分。  
  
    -   **注释-** functoid 输入注释。  
  
        > [!IMPORTANT]
        >  最大允许的字符数为 1024年。 如果指定超过 1024年个字符的字符串，则接受前面 1024 个字符，并丢弃剩余部分。  
  
## <a name="see-also"></a>请参阅  
 [编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)