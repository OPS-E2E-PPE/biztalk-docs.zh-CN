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
ms.openlocfilehash: ed171944d3d9e9dbb0de5b4c030ddc1af21ae8a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389086"
---
# <a name="error---functoid-variable-input-mismatch"></a>错误-Functoid 可变输入个数不匹配
**错误代码**  

 btm1011  

 **说明**  

 所指示的 functoid 没有正确指定的输入参数的数。 输入参数的数目必须在指定范围内。  

 **用户执行任何操作**  

 使用一个或多个以下方法提供的输入参数所指示的 functoid，特别要注意输入参数的正确顺序所指示的数目：  

- 若要创建其他链接，拖动以在源架构或位于所指示的 functoid 在映射网格页左侧其他 functoid 的输出中创建所指示的 functoid 和节点之间的链接。  

- 若要创建其他链接，请选择所指示的 functoid，单击省略号 (**...**) 按钮与相关联**输入参数**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后配置并重新排列输入参数的顺序**配置\<Functoid\> Functoid**对话框。 可以创建、 获得值，并放在正确的顺序相对于此对话框中的其他输入参数常数输入的参数。  

- 要删除现有的链接，每个链接连接到左侧和右侧的所指示的 functoid，右键单击该链接，然后单击**删除**。  

- 若要删除现有的链接，选择所指示的 functoid，单击省略号 (**...**) 按钮与相关联**输入参数**中的属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\> Functoid**对话框中，通过选择并单击的所有输入参数的 delete ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")为每个按钮。 必须使用此方法来删除常数输入的参数。
