---
title: "如何创建没有地图图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 520ec44f-5aca-4271-8835-b8e784214061
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81be2591c1d8f20f5b8dd01cf01c03e8daed9c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-map-without-maps"></a>如何创建没有映射图
如果具有已用于转换实例消息的 XSLT 代码，则可以直接使用该代码，而不用创建映射。  
  
 使用 XSLT 代码需要创建一个空的映射，并设置其**自定义 XSLT 路径**网格属性。 如果 XSLT 代码使用外部.NET 程序集，你还需要创建一个自定义扩展的 XML 文件。 有关自定义扩展的 XML 文件的结构的信息，请参阅**自定义扩展 XML （网格属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a>使用自定义 XSLT 代码，以地图取代  
  
1.  在项目中创建空 BizTalk 映射，并设置源架构和目标架构。  
  
     有关创建代码图和设置架构的信息，请参阅[创建地图](../core/creating-maps.md)。  
  
2.  在网格视图中，单击映射器网格。  
  
     属性窗口中显示**网格**属性。  
  
3.  在属性窗口中，选择**自定义 XSLT 路径**单击省略号 (**...**) 按钮。  
  
4.  在**打开**对话框框中，导航到该文件并单击**打开**。  
  
     **自定义 XSLT 路径**属性设置。  
  
> [!NOTE]
>  BizTalk 映射器仅支持 XSLT 1.0。 不支持在 BizTalk 映射器中使用 XSLT 2.0。  
  
## <a name="see-also"></a>另请参阅  
 [有关映射](../core/about-maps.md)   
 [脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [自定义 XSLT](../core/custom-xslt.md)   