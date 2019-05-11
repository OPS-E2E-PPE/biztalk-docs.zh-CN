---
title: 警告-自定义 XSLT 但未自定义扩展 XML |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customXsltButNoCustomExtensionXML
ms.assetid: af008ac2-e9ae-4753-a5ba-bf4dbb711a4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4c44fbe8385717061be1e5d8e81587d6a287b7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393712"
---
# <a name="warning---custom-xslt-but-no-custom-extension-xml"></a>警告-自定义 XSLT 但未自定义扩展 XML
**错误代码**  
  
 btm1034  
  
 **说明**  
  
 **自定义 XSLT 路径**而无需重写属性**自定义扩展 XML**被重写的属性。 如果这是有意为之，你可以忽略此警告。  
  
 BizTalk 映射器将使用指定的 XSLT**自定义 XSLT 路径**属性并生成虚拟的扩展 XML 映射文件。 如果您进行到外部程序集从提供的自定义 XSLT 内调用，则必须指定文件使用**自定义扩展 XML**包含程序集名称映射前缀的属性。  
  
 **用户执行任何操作**  
  
 如果此警告所指示的情况不是有意的请提供一个兼容值**自定义扩展 XML**的替代值的属性或移除**自定义 XSLT 路径**属性。