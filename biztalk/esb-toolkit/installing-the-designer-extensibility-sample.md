---
title: "安装设计器扩展性示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eba13a4a-1b87-4268-af91-29af3a5bc5ef
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ae913ddbcdd0b87b6ebfc1a4f38790ecdb67bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-designer-extensibility-sample"></a>安装设计器扩展性示例
本部分介绍安装设计器扩展性示例的过程。 你必须安装中的示例[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)和[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)安装和使用此示例之前。  
  
 **若要安装设计器扩展性示例**  
  
1.  在 Windows 资源管理器中打开文件夹 \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后打开名为的 Microsoft Visual Studio 解决方案文件Extenders.Itinerary.OrchestrationSample.sln。  
  
2.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，单击**生成解决方案**上**生成**菜单。  
  
3.  关闭 Visual Studio。  
  
4.  在 Windows 资源管理器中打开文件夹 \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后打开名为的 Visual Studio 解决方案文件Extenders.Resolvers.ResolverSample.sln。  
  
5.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，单击**生成解决方案**上**生成**菜单。  
  
6.  关闭 Visual Studio。  
  
7.  在 Windows 资源管理器，打开路线设计器安装路径下的 \Lib 文件夹。  
  
8.  在前面的步骤中生成的 Visual Studio 解决方案的 \bin\Debug 文件夹中，从复制到的 \Lib 目录的文件 Extenders.Resolvers.ResolverSample.dll 和 Extenders.Itinerary.OrchestrationSample.dll。