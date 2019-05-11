---
title: 方案：部署两个版本的应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, multiple assemblies
- assemblies, multiple assemblies
- receive locations, examples
- assemblies, deploying
- assemblies, examples
ms.assetid: 3e79a7df-bf77-4a0b-86ec-359fcf3489b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f41365ef18d1d2612236ac1b745008ad90a5c60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308201"
---
# <a name="scenario-deploying-two-versions-of-an-application"></a><span data-ttu-id="17d57-102">方案：部署应用程序的两个版本</span><span class="sxs-lookup"><span data-stu-id="17d57-102">Scenario: Deploying Two Versions of an Application</span></span>
<span data-ttu-id="17d57-103">本主题介绍在 BizTalk 组中部署某应用程序的两个版本的方案，以便它们可以同时运行。</span><span class="sxs-lookup"><span data-stu-id="17d57-103">This topic describes the scenario of deploying two versions of an application within a BizTalk group, so that they can both run simultaneously.</span></span> <span data-ttu-id="17d57-104">在本方案中，您需要部署该应用程序的主要新版本。</span><span class="sxs-lookup"><span data-stu-id="17d57-104">In this scenario, you need to deploy a major new version of the application.</span></span> <span data-ttu-id="17d57-105">这要求合作伙伴改变他们与系统的交互，这是因为架构或协议发生了变化 – 变化主要来自新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="17d57-105">It requires partners to change their interaction with the system due to either schema or protocol change - essentially a new application.</span></span> <span data-ttu-id="17d57-106">此系统的转变已经过测试，但不是在全面的生产系统规模下测试的。</span><span class="sxs-lookup"><span data-stu-id="17d57-106">The changeover to this system has been tested but not under the scale of a full production system.</span></span> <span data-ttu-id="17d57-107">您希望最初在 20% 的合作伙伴的范围内试用新系统，而后逐渐将试用百分比扩大到所有合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="17d57-107">You want to pilot the new system with 20 percent of the partners, and gradually increase that percentage until all the partners are using it.</span></span>  
  
 <span data-ttu-id="17d57-108">由于这两个应用程序在两个不同的接收位置接收消息，您必须指示那些应该使用新版应用程序的合作伙伴将消息发送到新的 URL，以便通过新版本来处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="17d57-108">Because the two applications receive messages on two different receive locations, you must ask those partners that should use the new version of the application to send messages to the new URL, so that they will be processed by the new version.</span></span>  
  
 <span data-ttu-id="17d57-109">下图显示了典型的并行应用程序部署方案。</span><span class="sxs-lookup"><span data-stu-id="17d57-109">The following diagram shows a typical side-by-side application deployment.</span></span>  
  
 <span data-ttu-id="17d57-110">![部署在一起的两个程序集版本](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")</span><span class="sxs-lookup"><span data-stu-id="17d57-110">![Two Assembly Versions Deployed Together](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d57-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="17d57-111">See Also</span></span>  
 [<span data-ttu-id="17d57-112">应用程序部署和管理方案</span><span class="sxs-lookup"><span data-stu-id="17d57-112">Application Deployment and Management Scenarios</span></span>](../core/application-deployment-and-management-scenarios.md)