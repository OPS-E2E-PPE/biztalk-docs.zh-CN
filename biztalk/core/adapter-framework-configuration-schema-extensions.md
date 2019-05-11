---
title: 适配器框架配置架构扩展 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27c9727f-5f97-41ee-a0b8-45d90427b0af
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac88ce098f546bf97fcb2d3897f71f4e6429966f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361489"
---
# <a name="adapter-framework-configuration-schema-extensions"></a>适配器框架配置架构扩展
BizTalk 适配器框架支持动态生成基于 XSD 定义的用户界面。 该适配器还提供必需的 XSD 和适配器框架将创建允许用户输入值的属性页。  
  
 若要创建自定义用户界面，适配器框架提供若干扩展。 若要使用这些扩展，必须导入适配器框架架构 (BizTalkAdapterFramework.xsd)。 通过导入架构，可以访问并使用该适配器配置架构中的修饰和专用的类型。  
  
 使用修饰标记和在本部分中所述的内置类型自定义适配器的属性网格。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [启用适配器框架配置架构扩展](../core/enabling-adapter-framework-configuration-extensions.md)  
  
-   [适配器框架配置架构修饰标记](../core/adapter-framework-configuration-schema-decoration-tags.md)  
  
-   [适配器的自定义配置架构示例](../core/examples-of-custom-configuration-schemas-for-adapters.md)