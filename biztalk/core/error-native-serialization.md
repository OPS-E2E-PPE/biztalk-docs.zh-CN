---
title: 错误-本机序列化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeSerialize
ms.assetid: 48f8d460-83a0-44ce-af9b-086fcad36cb8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80d6d9df379b93a11d4d736161029684ec175cb1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347272"
---
# <a name="error---native-serialization"></a>错误-本机序列化
**错误代码**  
  
 btm1048  
  
 **说明**  
  
 尝试将 XML 输出实例消息转换映射生成到目标架构指定的本机格式时遇到指示的序列化错误。  
  
 **用户执行任何操作**  
  
 在映射中指定的转换或目标架构中，或者对二者同时根据指示的序列化错误，请合适的更正。 可能会有帮助，BizTalk 编辑器中打开目标架构，并使用**验证架构**，**验证实例**，并**生成实例**命令可用右键单击解决方案资源管理器中的架构。