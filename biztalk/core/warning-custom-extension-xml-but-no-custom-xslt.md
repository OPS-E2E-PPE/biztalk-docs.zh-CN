---
title: 警告-自定义扩展 XML 但未自定义 XSLT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customExtensionXmlButNoCustomXSLT
ms.assetid: 3219c73c-2e58-4fe2-bc6e-2d60348d2415
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d94bea29ee6943ee6b084518e4b4ff404377503
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393729"
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a>警告-自定义扩展 XML 但未自定义 XSLT
**错误代码**  
  
 btm1033  
  
 **说明**  
  
 **自定义扩展 XML**而无需重写属性**自定义 XSLT 路径**被重写的属性。 如果这是有意为之，你可以忽略此警告。  
  
 BizTalk 映射器将使用通过编译映射生成的 XSLT 和将还生成扩展 XML 并将其追加到指定的重写的属性的自定义扩展 XML。 当映射包含这很有用**脚本**functoid 使用内联 XSLT 或内联 XSLT 调用模板，可以对一个或多个方法的调用外部程序集中。 在这种情况下，用户可以然后指定在程序集名称映射前缀**自定义扩展 XML**属性。  
  
 **用户执行任何操作**  
  
 如果此警告所指示的情况不是有意的请提供一个兼容值**自定义 XSLT 路径**的替代值的属性或移除**自定义扩展 XML**属性。