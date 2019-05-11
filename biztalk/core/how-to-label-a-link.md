---
title: 如何标记链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fb81763-8b50-4334-88a8-efad1c5d82d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6bbe74c77cba09ba5098810d8782cde592e55f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336940"
---
# <a name="how-to-label-a-link"></a>如何标记链接
标签是有助于记录 functoid 或映射中的链接的用途。 可以使用**标签**属性对链接进行命名。 您的映射包含大型架构结构和标识的输入和指向 functoid 的输出链接变得困难时，这很有用。  
  
> [!NOTE]
>  有关如何标记和注释 functoid 的信息，请参阅[如何标签和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。  
  
 下图显示链接标签。  
  
 ![为链接添加标签](../core/media/new-labelling-link.gif "New_Labelling_link")  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-add-a-label-to-a-link"></a>若要向链接添加标签  
  
1.  选择要标记的链接。  
  
2.  在中**属性**窗口中，提供新的名称在**标签**字段。  
  
    > [!IMPORTANT]
    >  最大允许的字符数为 256。 如果指定超过 256 个字符的字符串，则接受前 256 个字符，并丢弃剩余部分。  
  
     ![链接标签属性](../core/media/new-to-label-link.gif "New_To_Label_Link")  
  
## <a name="see-also"></a>请参阅  
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)