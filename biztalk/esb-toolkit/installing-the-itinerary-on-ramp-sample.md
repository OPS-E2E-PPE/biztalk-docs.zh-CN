---
title: "安装路线上负载增加示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebe08b84-dc12-4501-8677-15a32e4795a3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00dd0b820b006d681be6049cab1fd603e029dae4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-itinerary-on-ramp-sample"></a><span data-ttu-id="a3253-102">安装路线上负载增加示例</span><span class="sxs-lookup"><span data-stu-id="a3253-102">Installing the Itinerary On-Ramp Sample</span></span>
<span data-ttu-id="a3253-103">路线入口示例依赖于[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心解决方案、 动态解析示例中和解析程序服务示例。</span><span class="sxs-lookup"><span data-stu-id="a3253-103">The Itinerary On-Ramp sample depends on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core solution, the Dynamic Resolution sample, and the Resolver Service sample.</span></span> <span data-ttu-id="a3253-104">安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心自动将复制和安装此示例为正确的位置所需的核心程序集。</span><span class="sxs-lookup"><span data-stu-id="a3253-104">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the core assemblies required by this sample to the correct locations.</span></span> <span data-ttu-id="a3253-105">安装动态解析示例和解析程序服务示例可确保，Web 服务和业务规则引擎策略路线上负载增加示例使用正确安装和配置。</span><span class="sxs-lookup"><span data-stu-id="a3253-105">Installing the Dynamic Resolution sample and Resolver Service sample ensures that the Web services and Business Rules Engine policies used by the Itinerary On-Ramp Sample are correctly installed and configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3253-106">必须安装[安装动态解析示例](../esb-toolkit/installing-the-dynamic-resolution-sample.md)和[安装解析程序服务示例](../esb-toolkit/installing-the-resolver-service-sample.md)安装此示例之前。</span><span class="sxs-lookup"><span data-stu-id="a3253-106">You must install the [Installing the Dynamic Resolution Sample](../esb-toolkit/installing-the-dynamic-resolution-sample.md) and the [Installing the Resolver Service Sample](../esb-toolkit/installing-the-resolver-service-sample.md) before you install this sample.</span></span>  
>   
>  <span data-ttu-id="a3253-107">ESB 示例应用程序位于名为 GlobalBank.ESB Microsoft BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3253-107">The ESB sample applications reside a Microsoft BizTalk application named GlobalBank.ESB.</span></span> <span data-ttu-id="a3253-108">此外，此示例使用安装在核心 Microsoft.Practices.ESB 应用程序的项目。</span><span class="sxs-lookup"><span data-stu-id="a3253-108">In addition, this sample use artifacts installed in the core Microsoft.Practices.ESB application.</span></span> <span data-ttu-id="a3253-109">在安装路线入口示例之前，必须添加对 GlobalBank.ESB 应用程序 Microsoft.Practices.ESB 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="a3253-109">Before you install the Itinerary On-Ramp sample, you must add a reference to the Microsoft.Practices.ESB application to the GlobalBank.ESB application.</span></span>  
  
 <span data-ttu-id="a3253-110">你可以安装使用附带的安装脚本路线入口示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a3253-110">You can install the Itinerary On-Ramp sample using the install scripts included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="a3253-111">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="a3253-111">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="a3253-112">安装使用安装脚本路线上负载增加示例</span><span class="sxs-lookup"><span data-stu-id="a3253-112">Install the Itinerary On-Ramp Sample Using the Install Scripts</span></span>](../esb-toolkit/install-the-itinerary-on-ramp-sample-using-the-install-scripts.md)  
  
-   [<span data-ttu-id="a3253-113">程序集和项目安装路线上负载增加示例</span><span class="sxs-lookup"><span data-stu-id="a3253-113">Assemblies and Artifacts Installed by the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/assemblies-and-artifacts-installed-by-the-itinerary-on-ramp-sample.md)