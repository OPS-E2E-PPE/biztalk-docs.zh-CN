---
title: 排除地图故障 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32e2eb52-6740-4cf5-82ec-3b6d0b784276
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ba1a547b2df8531568959b0b9fa00a600cef21
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021851"
---
# <a name="troubleshooting-maps"></a>排除地图故障
本主题提供的故障排除策略和问题详细信息并将映射的解决方法信息。  
  
## <a name="troubleshooting-strategies"></a>故障排除策略  
  
### <a name="validate-your-map"></a>验证您的映射  
 这听起来可能很明显，但您应始终验证您在其开发过程的不同点的映射。 这将有助于在时更轻松地解决问题，或寻求替代解决方案的开发周期早期确定设计、 逻辑和架构问题。  
  
##### <a name="to-validate-a-biztalk-map"></a>若要验证 BizTalk 映射  
  
1.  在解决方案资源管理器，打开你想要验证的映射。  
  
2.  在解决方案资源管理器，右键单击该映射，然后单击**验证映射**。  
  
3.  在输出窗口中，验证结果。  
  
> [!NOTE]
>  时验证映射，则不检查您的测试实例数据以查看它是否与在架构中定义的任何数据类型冲突。 测试映射或验证实例数据在 BizTalk 编辑器中时，可以检查实例数据。  
  
### <a name="review-the-xslt-generated-for-your-map"></a>查看为您的映射生成的 XSLT  
 通常它可用于检查映射编译器生成的 XSLT。 检查 XSLT 的优势包括：  
  
- 如果使用循环或自定义 functoid 时，将更好地了解如何执行循环和如何调用自定义 functoid。  
  
- 如果你具有复杂的代码图，查看 XSLT 将允许您看到如何映射翻译为转换并可能提供了有关如何了解更好地构造、 替换或简化一个或多个部分。  
  
- 如果使用自定义脚本或其他项目，查看 XSLT 便可以看到脚本、 项目和映射的其他部分的交互方式。  
  
  幸运的是，查看映射的 XSLT 是一个简单的过程。  
  
##### <a name="to-view-the-xslt-generated-by-the-map-compiler"></a>若要查看映射编译器生成的 XSLT  
  
1. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**解决方案资源管理器**选项卡上，右键单击的映射，然后单击**验证映射**。  
  
2. 滚动输出窗口以查找 XSL 文件的 URL。 按住 Ctrl 单击 URL 以查看文件。  
  
   如果你决定手动自定义您的映射，则可以修改映射编译器生成的版本。 更改将不会反映映射器和下一次生成解决方案时将丢失。  
  
### <a name="tune-your-map-for-specific-scenarios-using-mapsource"></a>优化您的映射使用的特定方案\<mapsource\>  
 可以通过修改的属性来修改映射器的某些默认行为**mapsource**直接在映射源 (.btm) 文件中的元素。 目前有三个可以修改的行为：  
  
- **优化值映射 functoid 代码生成**。 您可以修改控制变量与使用时的行为`if`语句。  
  
- **适应大型操作痕迹包含以下架构：**。 你可以在大型映射中使用的内部编译器节点的方式。  
  
- **管理与循环、 条件、 和值映射 functoid 的 for-each 用法**。 您可以控制在何处`xsl:for-each`在目标架构中使用语句。  
  
  有关修改的详细信息**mapsource**，请参阅[管理默认映射器行为使用\<mapsource\>](../core/managing-default-mapper-behavior-using-mapsource.md)。  
  
## <a name="see-also"></a>请参阅  
 [常见疑难问题与解答](../core/general-troubleshooting-questions-and-answers.md)   
 [常见错误](../core/common-errors.md)