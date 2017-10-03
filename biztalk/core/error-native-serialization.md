---
title: "错误-本机序列化 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.nativeSerialize
ms.assetid: 48f8d460-83a0-44ce-af9b-086fcad36cb8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0d4a842a3f9a10703fb47bf21edb01ab92bd93c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---native-serialization"></a>错误-本机序列化
**错误代码**  
  
 btm1048  
  
 **说明**  
  
 尝试将映射所生成的 XML 输出实例消息转换为目标架构所指定的本地格式时，出现如消息中所指示的序列化错误。  
  
 **用户执行任何操作**  
  
 根据所指示的序列化错误，适当修改映射中指定的转换或目标架构，或者对二者同时进行修改。 它可能有助于 BizTalk 编辑器中打开目标架构以及使用**验证架构**，**验证实例**，和**生成实例**命令可用右键单击解决方案资源管理器中的架构。