---
title: 映射组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper, output
- maps, file type
- maps, file contents
- BizTalk Mapper, file type
- maps, components
ms.assetid: be438d21-80a8-49d8-bd08-d85618ab23de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1590ad1450453602b4dd5f25b2d52a4364787af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996766"
---
# <a name="map-components"></a>映射组件
映射的大多数组件存储在映射文件（扩展名为 .btm）中。 该文件中存储的项包括：  
  
- 对源架构和目标架构的引用  
  
- 链接，包括链接属性  
  
- Functoid 及其属性，例如输入参数  
  
- 其他属性，例如与网格和映射本身关联的属性  
  
  虽然 BizTalk 映射器将 .btm 文件中的映射编译为可扩展样式表语言转换 (XSLT) 文件，但 XSLT 并不是该文件的一部分。 只有在编译项目或验证映射时，BizTalk 映射器才会为映射生成 XSLT。 BizTalk 映射器将 XSLT 打包为项目程序集的一部分。  
  
## <a name="see-also"></a>请参阅  
 [映射](../core/maps.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)