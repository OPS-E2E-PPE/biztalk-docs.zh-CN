---
title: 错误-常规生成 XML 实例 |Microsoft Docs
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
ms.openlocfilehash: 79a24f4143e2619809071d3b414c9a122c8121b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348255"
---
# <a name="error---generic-generate-xml-instance"></a>错误-常规生成 XML 实例
**错误代码**  
  
 btm1038  
  
 **说明**  
  
 BizTalk 映射器无法生成该映射的源架构的 XML 实例消息文件。 这表明，没有源架构与映射关联的问题。  
  
 **用户执行任何操作**  
  
 使用 BizTalk 编辑器打开源架构与映射相关联，然后开始调查是否有问题的源架构。 此外，**验证架构**并**生成实例**命令中，右键单击解决方案资源管理器中的架构后即可可用于找出架构错误。