---
title: "警告-自定义扩展 XML 但没有自定义 XSLT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.warning.customExtensionXmlButNoCustomXSLT
ms.assetid: 3219c73c-2e58-4fe2-bc6e-2d60348d2415
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b626f8ede3231c04ae74dc0097cbdf524c90522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a>警告-自定义扩展 XML 但没有自定义 XSLT
**错误代码**  
  
 btm1033  
  
 **说明**  
  
 **自定义扩展 XML**而无需重写属性**自定义 XSLT 路径**重写的属性。 如果是故意如此，则可忽略此警告。  
  
 BizTalk 映射器将使用通过编译映射而生成的 XSLT，还将生成扩展 XML 并将其附加到由替代属性指定的自定义扩展 XML 之后。 这一点可能很有用，当映射包含**脚本**使用内联 XSLT 或内联 XSLT 的 functoid 调用外部程序集中进行到一个或多个方法调用的模板。 在这种情况下，用户可以然后指定中的程序集名称映射到前缀**自定义扩展 XML**属性。  
  
 **用户执行任何操作**  
  
 如果指此警告的情况不是有意的或者提供一个兼容值**自定义 XSLT 路径**重写值的属性或删除**自定义扩展 XML**属性。