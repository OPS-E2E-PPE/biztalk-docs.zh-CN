---
title: 错误-泛型生成 XML 实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericGenerateXmlInstance
ms.assetid: f2b42589-fd44-45d6-86e6-c2502820beee
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c859cfc775e74ab817e66dbb8b896f51458f0301
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241229"
---
# <a name="error---generic-generate-xml-instance"></a>错误-泛型生成 XML 实例
**错误代码**  
  
 btm1038  
  
 **说明**  
  
 BizTalk 映射器不能为该映射的源架构生成 XML 实例消息文件。 这表明与该映射相关联的源架构有问题。  
  
 **用户执行任何操作**  
  
 使用 BizTalk 编辑器打开与该映射相关联的源架构，并查明源架构是否有问题。 此外，**验证架构**和**生成实例**右键单击解决方案资源管理器中的架构时可用命令可用于查找架构错误。