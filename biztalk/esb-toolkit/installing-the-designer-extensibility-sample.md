---
title: 安装设计器扩展性示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eba13a4a-1b87-4268-af91-29af3a5bc5ef
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad1a88c7f497d236a8e11456cfbc48de45494e1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295121"
---
# <a name="installing-the-designer-extensibility-sample"></a>安装设计器扩展性示例
本部分介绍安装设计器扩展性示例的过程。 必须安装中的示例[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)并[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)安装和使用此示例之前。  

 **若要安装设计器扩展性示例**  

1. 在 Windows 资源管理器中打开文件夹 \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，并打开名为 Microsoft Visual Studio 解决方案文件Extenders.Itinerary.OrchestrationSample.sln。  

2. 在 Visual Studio 中，单击**生成解决方案**上**生成**菜单。  

3. 关闭 Visual Studio。  

4. 在 Windows 资源管理器中打开文件夹 \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，并打开名为 Visual Studio 解决方案文件Extenders.Resolvers.ResolverSample.sln。  

5. 在 Visual Studio 中，单击**生成解决方案**上**生成**菜单。  

6. 关闭 Visual Studio。  

7. 在 Windows 资源管理器中，打开路线设计器安装路径下的 \Lib 文件夹。  

8. 从前面步骤中生成的 Visual Studio 解决方案的 \bin\Debug 文件夹，Extenders.Resolvers.ResolverSample.dll 和 Extenders.Itinerary.OrchestrationSample.dll 的文件复制到的 \Lib 目录。
