---
title: 错误-累计 Functoid 为输入来自不同父记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputsToCumulativeFromDiffParents
ms.assetid: a2dcfe6f-0cd4-41ed-a69f-e510a74760a9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01e55e1d4bf09ecdb086ec99fde44008cf85829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388786"
---
# <a name="error---inputs-to-cumulative-functoid-from-different-parent-records"></a>错误-累计 Functoid 输入来自不同父记录
**错误代码**  
  
 btm1032  
  
 **说明**  
  
 为所指示**累计**functoid，第二个输入的参数 （累计作用域） 是与节点作为第一个输入参数 （要累计的节点） 的源架构的其他部分。  
  
 **用户执行任何操作**  
  
 确保两个输入参数所指示**累计**functoid 共享同一个父级记录，或您提供第二个输入的参数 （累计作用域） 具有常数输入的参数。