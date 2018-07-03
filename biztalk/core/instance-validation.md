---
title: 实例验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906f2e9-2bf9-448b-927f-dd2d7d9b2272
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f4e4901d11bda5fb6633c00dd72899ee1b72db4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012870"
---
# <a name="instance-validation"></a>实例验证
BizTalk 编辑器将调用**IInstanceValidator.ValidateInstance**扩展时满足以下条件的方法：  
  
- 扩展使用设置为标准**标准**的属性**架构**节点。  
  
- 上**属性页**与架构相关联的对话框中**生成实例输出类型**属性设置为**本机。**  
  
- 上**属性页**与架构相关联的对话框中**输入实例文件名**属性设置为包含要验证的实例消息的文件的名称。  
  
  中指定的文件**输入实例文件名**属性作为参数传递给**IInstanceValidator.ValidateInstance**方法。  
  
  如果出现错误，数组的形式返回错误消息**IValidationInfo**对象，并显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]任务列表窗口。  
  
> [!NOTE]
>  如果架构包含模式语句，该文件传递给**ValidateInstance**方法使用相应生成**生成实例**命令时，可能无法通过在实例消息验证。  
  
## <a name="see-also"></a>请参阅  
 [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)