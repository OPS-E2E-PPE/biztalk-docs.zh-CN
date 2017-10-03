---
title: "错误-输入到累积 Functoid 从不同的父记录 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.inputsToCumulativeFromDiffParents
ms.assetid: a2dcfe6f-0cd4-41ed-a69f-e510a74760a9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3c919001e05ca99383ffce72c8d450f6d04624b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---inputs-to-cumulative-functoid-from-different-parent-records"></a>错误-累积 Functoid 输入从不同的父记录
**错误代码**  
  
 btm1032  
  
 **说明**  
  
 用于指示**的累积**functoid，第二个输入的参数 （累计作用域） 是比充当第一个输入参数 （累积的节点） 的节点的源架构的其他部分。  
  
 **用户执行任何操作**  
  
 确保同时输入到指示的参数**的累积**functoid 共享相同的父记录，或者你提供第二个输入的参数 （累计作用域） 具有常量的输入的参数。