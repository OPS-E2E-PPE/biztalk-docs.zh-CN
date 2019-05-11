---
title: MapHelper 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c552c066-835f-4515-939f-dd465a7a5ed0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1442fbf7185a9be8cae598d1d5f2fee48f751ba2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399720"
---
# <a name="the-maphelper-class"></a>MapHelper 类
使用**MapHelper**类不使用转换 Web 服务直接执行的转换。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装程序安装并注册该程序集**Microsof.Practices.ESB.Transform.dll**与**MapHelper**全局程序集缓存中的类。  
  
 **MapHelper**类公开两个公共方法：  
  
-   **TransformMessage**。 包含要转换的消息字符串和包含部署在 BizTalk 映射的完全限定的名称的字符串，则将使用此方法作为参数。 该方法返回一个包含转换后的文档的字符串。  
  
-   **TransformMessageStream**。 包含要转换的消息的流和包含部署在 BizTalk 映射的完全限定的名称的字符串，则将使用此方法作为参数。 该方法返回一个字符串，包含已转换的文档。