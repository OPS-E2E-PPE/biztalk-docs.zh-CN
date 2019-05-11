---
title: 安装路线接入点示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebe08b84-dc12-4501-8677-15a32e4795a3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74bef54370f076d3777f825c89ab828f0f2413d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258437"
---
# <a name="installing-the-itinerary-on-ramp-sample"></a><span data-ttu-id="58b43-102">安装路线接入点示例</span><span class="sxs-lookup"><span data-stu-id="58b43-102">Installing the Itinerary On-Ramp Sample</span></span>
<span data-ttu-id="58b43-103">路线接入点示例依赖于[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心解决方案、 动态解析示例和解析程序服务示例。</span><span class="sxs-lookup"><span data-stu-id="58b43-103">The Itinerary On-Ramp sample depends on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core solution, the Dynamic Resolution sample, and the Resolver Service sample.</span></span> <span data-ttu-id="58b43-104">安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]core 自动复制和安装本示例为正确的位置所需的核心程序集。</span><span class="sxs-lookup"><span data-stu-id="58b43-104">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the core assemblies required by this sample to the correct locations.</span></span> <span data-ttu-id="58b43-105">安装动态解析示例和解析程序服务示例可确保 Web 服务和所使用的路线接入点示例业务规则引擎策略正确安装和配置。</span><span class="sxs-lookup"><span data-stu-id="58b43-105">Installing the Dynamic Resolution sample and Resolver Service sample ensures that the Web services and Business Rules Engine policies used by the Itinerary On-Ramp Sample are correctly installed and configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58b43-106">必须安装[安装动态解析示例](../esb-toolkit/installing-the-dynamic-resolution-sample.md)并[安装解析程序服务示例](../esb-toolkit/installing-the-resolver-service-sample.md)安装此示例之前。</span><span class="sxs-lookup"><span data-stu-id="58b43-106">You must install the [Installing the Dynamic Resolution Sample](../esb-toolkit/installing-the-dynamic-resolution-sample.md) and the [Installing the Resolver Service Sample](../esb-toolkit/installing-the-resolver-service-sample.md) before you install this sample.</span></span>  
>   
>  <span data-ttu-id="58b43-107">ESB 示例应用程序位于名为 GlobalBank.ESB 的 Microsoft BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="58b43-107">The ESB sample applications reside a Microsoft BizTalk application named GlobalBank.ESB.</span></span> <span data-ttu-id="58b43-108">此外，此示例使用在核心 Microsoft.Practices.ESB 应用程序中安装的项目。</span><span class="sxs-lookup"><span data-stu-id="58b43-108">In addition, this sample use artifacts installed in the core Microsoft.Practices.ESB application.</span></span> <span data-ttu-id="58b43-109">安装路线接入点示例之前，必须添加到 GlobalBank.ESB 应用程序 Microsoft.Practices.ESB 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="58b43-109">Before you install the Itinerary On-Ramp sample, you must add a reference to the Microsoft.Practices.ESB application to the GlobalBank.ESB application.</span></span>  
  
 <span data-ttu-id="58b43-110">你可以安装路线接入点示例使用安装脚本中包含[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="58b43-110">You can install the Itinerary On-Ramp sample using the install scripts included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="58b43-111">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="58b43-111">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="58b43-112">使用安装脚本安装路线接入点示例</span><span class="sxs-lookup"><span data-stu-id="58b43-112">Install the Itinerary On-Ramp Sample Using the Install Scripts</span></span>](../esb-toolkit/install-the-itinerary-on-ramp-sample-using-the-install-scripts.md)  
  
-   [<span data-ttu-id="58b43-113">路线接入点示例安装的程序集和项目</span><span class="sxs-lookup"><span data-stu-id="58b43-113">Assemblies and Artifacts Installed by the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/assemblies-and-artifacts-installed-by-the-itinerary-on-ramp-sample.md)