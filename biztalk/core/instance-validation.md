---
title: "实例验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f906f2e9-2bf9-448b-927f-dd2d7d9b2272
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3db1903030bbde96f2587ac14b5d168345b31823
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="instance-validation"></a>实例验证
BizTalk 编辑器时，将调用**IInstanceValidator.ValidateInstance**满足以下条件时的扩展方法：  
  
-   扩展使用设置为标准**标准**属性**架构**节点。  
  
-   上**属性页**与架构中，关联的对话框**生成实例输出类型**属性设置为**本机。**  
  
-   上**属性页**与架构中，关联的对话框**输入实例 Filename**属性设置为包含要验证的实例消息的文件的名称。  
  
 中指定的文件**输入实例 Filename**属性传递作为参数传递给**IInstanceValidator.ValidateInstance**方法。  
  
 如果出现错误，数组的形式返回错误消息**IValidationInfo**对象，并显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]任务列表窗口。  
  
> [!NOTE]
>  如果架构包含模式语句，并且文件传递到**ValidateInstance**方法生成通过使用相应**生成实例**命令时，可能无法通过实例消息验证。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)