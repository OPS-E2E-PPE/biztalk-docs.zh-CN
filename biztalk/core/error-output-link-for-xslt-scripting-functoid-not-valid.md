---
title: 错误-XSLT 脚本 Functoid 不是有效的输出链接 |Microsoft Docs
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
ms.openlocfilehash: 1348fd9cab436ca3ddbd0991acd5861283d933b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388506"
---
# <a name="error---output-link-for-xslt-scripting-functoid-not-valid"></a>错误-XSLT 脚本 Functoid 不是有效的输出链接
**错误代码**  
  
 btm1075  
  
 **说明**  
  
 输出链接的相关**脚本**functoid 配置为使用内联 XSLT 或 XSLT 调用模板无效。 此类的输出**脚本**functoid 必须连接到目标架构中的节点直接 （而非另一个 functoid，例如）。  
  
 **用户执行任何操作**  
  
 确保从相关连接输出链接**脚本**functoid 直接到目标架构中的节点。