---
title: 实例生成 |Microsoft Docs
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
ms.openlocfilehash: 4674c8ff852be6ab6bf9b217ad68fe4ac4c14333
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382094"
---
# <a name="instance-generation"></a>实例生成
BizTalk 编辑器将调用**IInstanceGenerator.GenerateInstance**扩展时满足以下条件的方法：  
  
-   扩展使用设置为标准**标准**的属性**架构**节点。  
  
-   上**属性页**与架构相关联的对话框中**生成实例输出类型**属性设置为**本机。**  
  
-   上**属性页**与架构相关联的对话框中**输出实例文件名**属性设置为输出实例将保存到文件的名称。  
  
> [!NOTE]
>  如果**输出实例文件名**属性未设置、 临时文件夹中的默认文件名用于生成的实例消息中，并在输出窗口中提供指向它的链接。  
  
 之前**IInstanceValidator.ValidateInstance**调用方法、 BizTalk 编辑器生成示例 XML 实例消息，然后将其传递和中指定的文件**输出实例文件名**属性或默认文件名，该方法。  
  
 如果出现错误，数组的形式返回错误消息**IValidationInfo**对象，并显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]任务列表窗口。  
  
## <a name="see-also"></a>请参阅  
 [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)