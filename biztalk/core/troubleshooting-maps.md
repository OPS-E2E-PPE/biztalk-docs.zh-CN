---
title: "排除地图故障 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32e2eb52-6740-4cf5-82ec-3b6d0b784276
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bb7b3dc8356172989c215dc13e5fd82e46f4689
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-maps"></a>排除地图故障
本主题提供故障排除策略和问题详细信息和映射的解决方法信息。  
  
## <a name="troubleshooting-strategies"></a>故障排除策略  
  
### <a name="validate-your-map"></a>验证你的代码图  
 这可能看起来很明显，但你应始终验证你在其开发整个的不同点的代码图。 这将帮助在时很容易地修复这些属性或查找替代解决方案开发周期的初期识别设计、 逻辑和架构的问题。  
  
##### <a name="to-validate-a-biztalk-map"></a>若要验证 BizTalk 映射  
  
1.  在解决方案资源管理器，打开你想要验证的映射。  
  
2.  在解决方案资源管理器，请右键单击映射，，然后单击**验证映射**。  
  
3.  在输出窗口中，验证结果。  
  
> [!NOTE]
>  当验证映射时，测试实例数据将不检查以查看它是否与架构中定义的任何数据类型冲突。 测试映射或验证实例数据在 BizTalk 编辑器时，你可以检查实例数据。  
  
### <a name="review-the-xslt-generated-for-your-map"></a>查看为你的代码图生成 XSLT  
 通常它可用于检查由映射编译器生成的 XSLT。 一些检查 XSLT 的优势包括：  
  
-   如果使用循环或自定义 functoid，你将更好地了解如何执行循环如何调用自定义 functoid。  
  
-   如果你具有复杂的代码图，查看 XSLT 将使你可以看到如何映射转换成一个转换和可能意味着赋予您了解如何更好的结构、 替换或简化其中一个或多个部件。  
  
-   如果你使用自定义脚本或其他项目，则查看 XSLT 将可以查看脚本、 项目和映射的其他部分的交互方式。  
  
 幸运的是，查看地图 XSLT 是一个简单的过程。  
  
##### <a name="to-view-the-xslt-generated-by-the-map-compiler"></a>若要查看由映射编译器生成的 XSLT  
  
1.  从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，单击**解决方案资源管理器**选项卡上，右键单击一个代码图，，然后单击**验证映射**。  
  
2.  滚动输出窗口以确定该 XSL 文件的 URL。 按住 Ctrl 单击 URL 以查看文件。  
  
 如果你决定手动自定义你的代码图，你可以修改映射编译器生成的版本。 更改映射器将不会反映，将会丢失在下次生成你的解决方案。  
  
### <a name="tune-your-map-for-specific-scenarios-using-mapsource"></a>优化你使用的特定方案的代码图\<mapsource\>  
 你可以通过修改的属性来修改映射器的某些默认行为**mapsource**直接映射 (.btm) 源文件中的元素。 目前，有三个您可以修改的行为：  
  
-   **优化值映射 functoid 代码生成**。 你可以修改控制变量与一起使用时的行为`if`语句。  
  
-   **容纳较大的空间占用量与架构**。 你可以更改内部编译器节点在大型地图中使用的方式。  
  
-   **为每个使用管理使用情况循环、 条件，和值映射 functoid**。 你可以控制在何处`xsl:for-each`在目标架构内使用语句。  
  
 有关修改**mapsource**，请参阅[管理默认映射器行为使用\<mapsource\>](../core/managing-default-mapper-behavior-using-mapsource.md)。  
  
## <a name="see-also"></a>另请参阅  
 [常规疑难解答问题和解答](../core/general-troubleshooting-questions-and-answers.md)   
 [常见错误](../core/common-errors.md)