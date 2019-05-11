---
title: 扩展的冲突解决程序和适配器提供程序框架 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d5e6f2-b3bc-46e2-b8f7-d7e271d4a8c0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e53c9284ec85e86cbf3a79ca73d6a819049933f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400336"
---
# <a name="extending-the-resolver-and-adapter-provider-framework"></a>扩展的冲突解决程序和适配器提供程序框架
它还可以提供自定义元数据服务和冲突解决程序和适配器提供程序框架的终结点和转换解析和路由，提供支持。 框架可以动态地解析终结点，并设置出站适配器属性。 之后冲突解决程序组件解决了终结点 （例如，使用通用描述、 发现和集成 [UDDI] 若要查找出站 URL），适配器提供程序组件设置的已注册的 Microsoft BizTalk Server 适配器的特定属性。  
  
 有三个主要区域，可以扩展的冲突解决程序和适配器提供程序框架：  
  
-   [创建自定义解析程序](../esb-toolkit/creating-a-custom-resolver.md)  
  
-   [使用 Unity 容器创建自定义解析程序](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)  
  
-   [创建自定义适配器提供程序](../esb-toolkit/creating-a-custom-adapter-provider.md)