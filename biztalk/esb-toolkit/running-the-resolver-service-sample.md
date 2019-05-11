---
title: 运行解析程序服务示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4bf0b21-6aa0-4524-9e63-93a172845d4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adb7f35671534a3c425e962d4980d452368f79d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242698"
---
# <a name="running-the-resolver-service-sample"></a><span data-ttu-id="17511-102">运行解析程序服务示例</span><span class="sxs-lookup"><span data-stu-id="17511-102">Running the Resolver Service Sample</span></span>
<span data-ttu-id="17511-103">解析程序服务示例演示以下方案：</span><span class="sxs-lookup"><span data-stu-id="17511-103">The Resolver Service sample demonstrates the following scenarios:</span></span>  

- <span data-ttu-id="17511-104">解析服务终结点使用的绑定键的 UDDI3 的 URI</span><span class="sxs-lookup"><span data-stu-id="17511-104">Resolve a service endpoint URI from UDDI3 using a binding key</span></span>  

- <span data-ttu-id="17511-105">解析服务终结点 URI 从 UDDI3 使用分类搜索</span><span class="sxs-lookup"><span data-stu-id="17511-105">Resolve a service endpoint URI from UDDI3 using a categorization search</span></span>  

- <span data-ttu-id="17511-106">解决使用静态的冲突解决程序的转换 （BizTalk 映射类型）</span><span class="sxs-lookup"><span data-stu-id="17511-106">Resolve a transformation (BizTalk Map type) using a STATIC resolver</span></span>  

- <span data-ttu-id="17511-107">解析服务终结点 URI 使用静态的冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="17511-107">Resolve a service endpoint URI using a STATIC resolver</span></span>  

- <span data-ttu-id="17511-108">解析服务终结点 URI 使用 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="17511-108">Resolve a service endpoint URI using an XPath expression</span></span>  

- <span data-ttu-id="17511-109">解决使用静态的旅行计划冲突解决程序路线</span><span class="sxs-lookup"><span data-stu-id="17511-109">Resolve an itinerary using a static ITINERARY resolver</span></span>  

- <span data-ttu-id="17511-110">解决使用路线静态 (Unity) 冲突解决程序路线</span><span class="sxs-lookup"><span data-stu-id="17511-110">Resolve an itinerary using an ITINERARY-STATIC (Unity) resolver</span></span>  

- <span data-ttu-id="17511-111">解决路线使用 BRE （BRI 冲突解决程序）</span><span class="sxs-lookup"><span data-stu-id="17511-111">Resolve an itinerary using BRE (BRI Resolver)</span></span>  

- <span data-ttu-id="17511-112">解决 BRE （BRI 冲突解决程序） 使用消息路线</span><span class="sxs-lookup"><span data-stu-id="17511-112">Resolve an Itinerary using BRE (BRI Resolver) with the Message</span></span>  

- <span data-ttu-id="17511-113">解析服务终结点 URI 使用 BRE</span><span class="sxs-lookup"><span data-stu-id="17511-113">Resolve a service endpoint URI using BRE</span></span>  

- <span data-ttu-id="17511-114">解决使用 BRE 的转换</span><span class="sxs-lookup"><span data-stu-id="17511-114">Resolve a transformation using BRE</span></span>  

  <span data-ttu-id="17511-115">**若要运行使用解析程序服务的 ASMX 实现的所有解决方法方案**</span><span class="sxs-lookup"><span data-stu-id="17511-115">**To run all the resolution scenarios using the ASMX implementation of the Resolver service**</span></span>  

1. <span data-ttu-id="17511-116">如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="17511-116">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  

2. <span data-ttu-id="17511-117">在 Windows 资源管理器，打开 \Source\Samples\ResolverService 文件夹，并双击文件 RunTestClient_ASMX.cmd。</span><span class="sxs-lookup"><span data-stu-id="17511-117">In Windows Explorer, open the \Source\Samples\ResolverService folder, and then double-click the file RunTestClient_ASMX.cmd.</span></span>  

3. <span data-ttu-id="17511-118">打开 \Source\Samples\ResolverService\Output 文件夹，然后打开结果文件，它们分别对应于前面列出的解析请求。</span><span class="sxs-lookup"><span data-stu-id="17511-118">Open the \Source\Samples\ResolverService\Output folder, and then open the result files, which correspond to the resolution requests listed earlier.</span></span>  

   <span data-ttu-id="17511-119">**若要运行使用解析程序服务的 WCF 实现的所有解决方法方案**</span><span class="sxs-lookup"><span data-stu-id="17511-119">**To run all the resolution scenarios using the WCF implementation of the Resolver service**</span></span>  

4. <span data-ttu-id="17511-120">如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="17511-120">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  

5. <span data-ttu-id="17511-121">在 Windows 资源管理器，打开 \Source\Samples\ResolverService 文件夹，并双击文件 RunTestClient_WCF.cmd。</span><span class="sxs-lookup"><span data-stu-id="17511-121">In Windows Explorer, open the \Source\Samples\ResolverService folder, and then double-click the file RunTestClient_WCF.cmd.</span></span>  

6. <span data-ttu-id="17511-122">打开 \Source\Samples\ResolverService\Output 文件夹，然后打开结果文件，它们分别对应于前面列出的解析请求。</span><span class="sxs-lookup"><span data-stu-id="17511-122">Open the \Source\Samples\ResolverService\Output folder, and then open the result files, which correspond to the resolution requests listed earlier.</span></span>
