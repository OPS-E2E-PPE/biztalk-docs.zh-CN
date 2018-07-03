---
title: 如何调试映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ee1e26-fced-4126-b48a-71007043424d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f30d26b7c722ea4e4896bc7d19130e41eec5c719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989718"
---
# <a name="how-to-debug-maps"></a>如何调试映射
**调试映射**功能是用于识别和修复复杂的映射问题。 本主题提供了使用内联 XSLT 调试程序调试映射的分步说明。  

> [!NOTE]
>  调试映射时**调试映射**功能使用映射文件属性**测试映射输入实例**并**测试映射输出实例**。 因此，在调试映射之前，我们建议您在映射文件中配置输入和输出实例属性。  

### <a name="to-debug-a-biztalk-map"></a>调试 BizTalk 映射  

1. 在解决方案资源管理器，右键单击你想要测试，然后单击的地图**调试映射**。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 在其编辑器中的 XSLT 格式显示的映射。  

2. 按 F10 或 F11 来调试 XSL 代码。 按 functoid 调用上的 F11 时，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 会开始处理 functoid 的 C# 代码。 您可以在本地 Windows 调试器中查看用在 functoid 源代码中的变量的值。
