---
title: 如何创建在无映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520ec44f-5aca-4271-8835-b8e784214061
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8d1ce3c42e1c776014036de7a832e8fd74b1be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340040"
---
# <a name="how-to-create-a-map-without-maps"></a>如何创建在无映射
如果您一直使用将实例消息的 XSLT 代码，您可以使用该代码直接而不是创建映射。  
  
 使用 XSLT 代码时，需要创建空映射并设置其**自定义 XSLT 路径**网格属性。 如果 XSLT 代码使用外部.NET 程序集，还需要创建自定义扩展 XML 文件。 自定义扩展 XML 文件的结构有关的信息，请参阅**自定义扩展 XML （网格属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a>使用自定义 XSLT 代码代替映射  
  
1.  在项目中创建空的 BizTalk 映射并设置源和目标架构。  
  
     有关创建映射和设置架构的信息，请参阅[创建映射](../core/creating-maps.md)。  
  
2.  在网格视图中，单击映射器网格。  
  
     属性窗口显示**网格**属性。  
  
3.  在属性窗口中，选择**自定义 XSLT 路径**然后单击省略号 (**...**) 按钮。  
  
4.  在中**开放**对话框中，导航到该文件，单击**打开**。  
  
     **自定义 XSLT 路径**属性设置。  
  
> [!NOTE]
>  BizTalk 映射器仅支持 XSLT 1.0。 不支持在 BizTalk 映射器中使用 XSLT 2.0。  
  
## <a name="see-also"></a>请参阅  
 [有关地图](../core/about-maps.md)   
 [使用内联 XSLT 和 XSLT 调用模板编写脚本](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [自定义 XSLT](../core/custom-xslt.md)   