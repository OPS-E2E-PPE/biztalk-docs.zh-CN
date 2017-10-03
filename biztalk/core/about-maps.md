---
title: "有关映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper
- maps, file type
- maps, about maps
- BizTalk Mapper, about BizTalk Mapper
- maps
ms.assetid: 512ef2b7-3d01-4fcf-bb38-de68ec608b07
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d15f37dc0ff0112906a449e1b1d84704b21727
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-maps"></a>有关映射
通过 BizTalk 映射器，可以使用链接和 functoid 在输入架构和输出架构之间定义关系。 链接定义了记录或字段的直接数据复制。 链接可以直接连接到另一架构中的项，也可以构成指向 functoid 的连接。 functoid 可以执行更加复杂的数据操作，例如：  
  
-   将源架构中的两个字段的值相加，然后将结果复制到目标架构。  
  
-   将字符转换为 ASCII 格式。  
  
-   返回重复记录中某个字段的平均值，然后将结果复制到目标架构中的字段。  
  
 BizTalk 映射器使用扩展名为 .btm 的文件存储映射。 该文件保存了映射的有关设计信息：表示 functoid 的图标的位置、架构项和 functoid 之间的链接以及有关该映射的其他信息。 在构建或编译映射时，BizTalk 映射器可以将该映射的有关信息转换为相应的可扩展样式表转换 (XSLT) 样式表。  
  
> [!NOTE]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器具有 16 兆字节限制单个项目中的所有字符串的总大小。 虽然编译 BizTalk 项目，编译器将序列化架构、 映射和业务流程创建程序集，并且这会增加可能超出限制的所有字符串的总大小。 若要解决此问题，您可以通过将架构和/或映射放入不同的 Biztalk 项目（通常在同一个解决方案下）以对您的项目进行重新组织，以便使每个项目中的所有字符串的总大小小于 16 MB。  
  
 所创建的映射可以用于转换或翻译数据，这些映射可以特定于单个贸易合作伙伴，也可以用于多个贸易合作伙伴。 本部分中的主题介绍了映射架构中所涉及的概念。 有关地图背景信息，请参阅[映射](../core/maps.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在映射中的链接](../core/links-in-maps.md)  
  
-   [在映射中的 Functoid](../core/functoids-in-maps.md)  
  
-   [映射编译和测试](../core/map-compilation-and-testing.md)