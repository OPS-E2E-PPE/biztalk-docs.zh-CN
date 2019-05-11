---
title: 有关地图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper
- maps, file type
- maps, about maps
- BizTalk Mapper, about BizTalk Mapper
- maps
ms.assetid: 512ef2b7-3d01-4fcf-bb38-de68ec608b07
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b7a2e7f89e927b4759ea814f341684195273e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362339"
---
# <a name="about-maps"></a>有关地图
使用 BizTalk 映射器，通过使用链接和 functoid 定义输入和输出架构之间的关系。 链接定义记录或字段的直接数据的复制。 链接可以直接连接到其他架构中的项或也可以构成指向 functoid 的连接。 Functoid 可以执行更复杂的数据操作，如：  
  
- 在源架构并将结果复制到目标架构中添加两个字段的值。  
  
- 将字符转换为 ASCII 格式。  
  
- 在重复记录并将结果复制到目标架构中的字段中返回字段的平均值。  
  
  BizTalk 映射器将映射存储在扩展名为.btm 的文件中。 该文件将保存该映射的有关设计信息 — 的图标表示 functoid、 架构项和 functoid 之间的链接的位置和该映射的有关其他信息。 当生成或编译映射时，BizTalk 映射器将相应的可扩展语言样式表转换 (XSLT) 样式表转换为该映射的有关信息。  
  
> [!NOTE]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器中的单个项目的所有字符串的总大小具有 16 兆字节的限制。 而编译 BizTalk 项目，编译器将序列化架构、 映射和业务流程创建程序集，而这会增大可能会超出此限制的所有字符串的总大小。 若要解决此问题，您可以通过重新组织你的项目将架构和/或映射放入不同的 Biztalk 项目 （通常情况下，相同的解决方案） 下,，每个项目中的所有字符串的总大小小于 16 MB。  
  
 您创建的映射可以转换或翻译数据，并且它们可以是特定于单个贸易合作伙伴也可以用于多个贸易合作伙伴。 在本部分中的主题提供针对映射架构中所涉及的概念的介绍。 有关地图的背景信息，请参阅[映射](../core/maps.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [映射中的链接](../core/links-in-maps.md)  
  
-   [映射中的 Functoid](../core/functoids-in-maps.md)  
  
-   [映射编译和测试](../core/map-compilation-and-testing.md)