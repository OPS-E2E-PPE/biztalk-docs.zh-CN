---
title: 错误-XSLT 脚本 Functoid 不是有效的输出链接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.outputLinkForXsltNotValid
ms.assetid: cdf8e779-6cf6-4d9c-8655-f8b406498fb7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd597a3953db76087086c7ea9038e9fa1fd87eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---output-link-for-xslt-scripting-functoid-not-valid"></a>错误-XSLT 脚本 Functoid 不是有效的输出链接
**错误代码**  
  
 btm1075  
  
 **说明**  
  
 相关的输出链接**脚本**functoid 配置为使用内联 XSLT 或 XSLT 调用模板无效。 此类的输出**脚本**functoid 必须连接直接到目标架构中的节点 （而非另一个 functoid，例如）。  
  
 **用户执行任何操作**  
  
 确保从相关连接输出链接**脚本**functoid 直接到目标架构中的节点。