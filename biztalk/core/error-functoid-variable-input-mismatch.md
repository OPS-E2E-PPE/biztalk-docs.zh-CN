---
title: 错误-Functoid 可变输入个数不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functoidVariableInputMismatch
ms.assetid: fda3066b-d0de-4f61-b78f-4726f6796e1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99ace732b627e044b569597afb7bae91342c31f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984958"
---
# <a name="error---functoid-variable-input-mismatch"></a>错误-Functoid 可变输入个数不匹配
**错误代码**  

 btm1011  

 **说明**  

 所指示的 functoid 的输入参数个数不正确。 输入参数的个数必须在指定范围内。  

 **用户执行任何操作**  

 采用以下一种或多种方法为指示的 functoid 提供所指示数目的输入参数，特别要注意确保输入参数的顺序正确：  

- 若要创建其他链接，请拖动鼠标以在所指示的 functoid 与源架构中的节点或其他 functoid 的输出之间创建链接，这些 functoid 在映射网格页中位于所指示的 functoid 的左侧。  

- 若要创建其他链接，请选择所指示的 functoid，单击省略号 (**...**) 按钮与相关联**输入参数**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后配置并重新排列输入参数的顺序**配置\<Functoid\> Functoid**对话框。 也可以创建常数输入参数并为它赋值，然后在此对话框中将该参数放置到相对于其他输入参数的正确位置。  

- 要删除现有的链接，每个链接连接到左侧和右侧的所指示的 functoid，右键单击该链接，然后单击**删除**。  

- 若要删除现有的链接，选择所指示的 functoid，单击省略号 (**...**) 按钮与相关联**输入参数**中的属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\> Functoid**对话框中，通过选择并单击的所有输入参数的 delete ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")为每个按钮。 删除常数输入参数时必须使用这种方法。
