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
ms.openlocfilehash: 9459cc2d2d51347e508ac989a9aeb54b9ac1059d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338890"
---
# <a name="how-to-debug-maps"></a>如何调试映射
**调试映射**功能是用于识别和修复复杂的映射问题。 本主题提供调试映射使用内联 XSLT 调试程序的分步说明。  

> [!NOTE]
>  调试映射时**调试映射**功能使用映射文件属性**测试映射输入实例**并**测试映射输出实例**。 因此，在调试映射之前，我们建议您配置输入和输出实例属性映射文件中。  

### <a name="to-debug-a-biztalk-map"></a>若要调试 BizTalk 映射  

1. 在解决方案资源管理器，右键单击你想要测试，然后单击的地图**调试映射**。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 在其编辑器中的 XSLT 格式显示的映射。  

2. 按 F10 或 F11 来调试 XSL 代码。 当在 functoid 调用上，按 F11 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] functoid 代码的 C# 的步骤。 您可以查看本地 Windows 调试器中的 functoid 源代码中使用的变量的值。
