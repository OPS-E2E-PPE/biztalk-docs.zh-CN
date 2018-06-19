---
title: 实例生成 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14060dca-5e14-474a-bf2c-4e8bc56e3c61
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bd3d2bc6852ec0c73fbbe4ffc55924a8012ce5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257261"
---
# <a name="instance-generation"></a>生成实例
BizTalk 编辑器时，将调用**IInstanceGenerator.GenerateInstance**满足以下条件时的扩展方法：  
  
-   扩展使用设置为标准**标准**属性**架构**节点。  
  
-   上**属性页**与架构中，关联的对话框**生成实例输出类型**属性设置为**本机。**  
  
-   上**属性页**与架构中，关联的对话框**输出实例文件名**属性设置为输出实例将保存到文件的名称。  
  
> [!NOTE]
>  如果**输出实例文件名**未设置属性、 对于生成的实例消息中，使用临时文件夹中的默认文件名称和在输出窗口中提供的链接。  
  
 之前**IInstanceValidator.ValidateInstance**调用方法时，BizTalk 编辑器生成示例 XML 实例消息，然后将其传递并在指定的文件**输出实例文件名**属性或默认文件名，该方法。  
  
 如果出现错误，数组的形式返回错误消息**IValidationInfo**对象，并显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]任务列表窗口。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)