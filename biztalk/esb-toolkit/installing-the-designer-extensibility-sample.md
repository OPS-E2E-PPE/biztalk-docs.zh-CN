---
title: 安装设计器扩展性示例 |Microsoft 文档
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
ms.openlocfilehash: ea0cd71c22fdd614d2e49c996939b785ecadf8bd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007974"
---
# <a name="installing-the-designer-extensibility-sample"></a><span data-ttu-id="8d545-102">安装设计器扩展性示例</span><span class="sxs-lookup"><span data-stu-id="8d545-102">Installing the Designer Extensibility Sample</span></span>
<span data-ttu-id="8d545-103">本部分介绍安装设计器扩展性示例的过程。</span><span class="sxs-lookup"><span data-stu-id="8d545-103">This section describes the process for installing the Designer Extensibility sample.</span></span> <span data-ttu-id="8d545-104">你必须安装中的示例[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)和[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)安装和使用此示例之前。</span><span class="sxs-lookup"><span data-stu-id="8d545-104">You must install the samples in [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md) before you install and use this sample.</span></span>  
  
 <span data-ttu-id="8d545-105">**若要安装设计器扩展性示例**</span><span class="sxs-lookup"><span data-stu-id="8d545-105">**To install the Designer Extensibility sample**</span></span>  
  
1.  <span data-ttu-id="8d545-106">在 Windows 资源管理器中打开文件夹 \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后打开名为的 Microsoft Visual Studio 解决方案文件Extenders.Itinerary.OrchestrationSample.sln。</span><span class="sxs-lookup"><span data-stu-id="8d545-106">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Itinerary.OrchestrationSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Microsoft Visual Studio solution file named Extenders.Itinerary.OrchestrationSample.sln.</span></span>  
  
2.  <span data-ttu-id="8d545-107">在 Visual Studio 中，单击**生成解决方案**上**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="8d545-107">In Visual Studio, click **Build Solution** on the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="8d545-108">关闭 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="8d545-108">Close Visual Studio.</span></span>  
  
4.  <span data-ttu-id="8d545-109">在 Windows 资源管理器中打开文件夹 \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后打开名为的 Visual Studio 解决方案文件Extenders.Resolvers.ResolverSample.sln。</span><span class="sxs-lookup"><span data-stu-id="8d545-109">In Windows Explorer, open the folder \Source\Samples\Designer Extensibility Samples\Extenders.Resolvers.ResolverSample, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named Extenders.Resolvers.ResolverSample.sln.</span></span>  
  
5.  <span data-ttu-id="8d545-110">在 Visual Studio 中，单击**生成解决方案**上**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="8d545-110">In Visual Studio, click **Build Solution** on the **Build** menu.</span></span>  
  
6.  <span data-ttu-id="8d545-111">关闭 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="8d545-111">Close Visual Studio.</span></span>  
  
7.  <span data-ttu-id="8d545-112">在 Windows 资源管理器，打开路线设计器安装路径下的 \Lib 文件夹。</span><span class="sxs-lookup"><span data-stu-id="8d545-112">In Windows Explorer, open the \Lib folder under the Itinerary Designer install path.</span></span>  
  
8.  <span data-ttu-id="8d545-113">在前面的步骤中生成的 Visual Studio 解决方案的 \bin\Debug 文件夹中，从复制到的 \Lib 目录的文件 Extenders.Resolvers.ResolverSample.dll 和 Extenders.Itinerary.OrchestrationSample.dll。</span><span class="sxs-lookup"><span data-stu-id="8d545-113">From the \bin\Debug folders of the Visual Studio solutions built in the preceding steps, copy the files Extenders.Resolvers.ResolverSample.dll and Extenders.Itinerary.OrchestrationSample.dll to the \Lib directory.</span></span>