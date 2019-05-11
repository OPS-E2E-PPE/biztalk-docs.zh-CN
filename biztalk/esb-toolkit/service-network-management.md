---
title: 服务网络管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21469dad-6c64-470a-bd58-8309d789ce6c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4280438758e3f2626cf2e0ec68c1e30f51d0bde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268899"
---
# <a name="service-network-management"></a><span data-ttu-id="cec19-102">服务网络管理</span><span class="sxs-lookup"><span data-stu-id="cec19-102">Service Network Management</span></span>
<span data-ttu-id="cec19-103">有效的运行时管理需要了解在运行时环境中部署的服务。</span><span class="sxs-lookup"><span data-stu-id="cec19-103">Effective run-time governance requires knowledge of the services deployed into the run-time environment.</span></span> <span data-ttu-id="cec19-104">AmberPoint SMS 可以发现的实际的接收位置和发送端口在 BizTalk 管理组中，部署，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="cec19-104">AmberPoint SMS can discover the actual receive locations and send ports deployed within a BizTalk Management Group, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="cec19-105">![AmberPoint 容器发现](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9-AmberPointContainerDiscovery")</span><span class="sxs-lookup"><span data-stu-id="cec19-105">![AmberPoint Container Discovery](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9-AmberPointContainerDiscovery")</span></span>  
  
 <span data-ttu-id="cec19-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="cec19-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="cec19-107">**AmberPoint 容器发现 SMS 屏幕**</span><span class="sxs-lookup"><span data-stu-id="cec19-107">**The AmberPoint SMS Container Discovery screens**</span></span>  
  
 <span data-ttu-id="cec19-108">使用已部署的服务的信息，AmberPoint SMS 提供了各种不同的观点，帮助用户了解运行时配置和评估中运行的其他服务及其依赖的服务的服务网络。</span><span class="sxs-lookup"><span data-stu-id="cec19-108">Using information on the deployed services, AmberPoint SMS presents various perspectives of the services that help users to understand the run-time configuration and appreciate their dependencies on other services within the running service network.</span></span> <span data-ttu-id="cec19-109">图 2 显示了服务配置文件和依赖项屏幕。</span><span class="sxs-lookup"><span data-stu-id="cec19-109">Figure 2 shows the service profile and dependencies screens.</span></span>  
  
 <span data-ttu-id="cec19-110">![AmberPoint 服务配置文件](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9-AmberPointServiceProfile")</span><span class="sxs-lookup"><span data-stu-id="cec19-110">![AmberPoint Service Profile](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9-AmberPointServiceProfile")</span></span>  
  
 <span data-ttu-id="cec19-111">**图 2**</span><span class="sxs-lookup"><span data-stu-id="cec19-111">**Figure 2**</span></span>  
  
 <span data-ttu-id="cec19-112">**AmberPoint SMS 服务配置文件和依赖项屏幕**</span><span class="sxs-lookup"><span data-stu-id="cec19-112">**The AmberPoint SMS service profile and dependencies screens**</span></span>  
  
 <span data-ttu-id="cec19-113">AmberPoint SMS 可以将发布，如将服务发现和运行时元数据转发到现有的通用描述、 发现和集成 (UDDI) 注册表、 自定义配置管理存储库和 master 系统管理控制台Microsoft Operations Manager (MOM) 2004年和 System Center Operations Manager 2007 (SCOM)。</span><span class="sxs-lookup"><span data-stu-id="cec19-113">AmberPoint SMS can publish and forward service discoveries and run-time metadata to existing Universal Description, Discovery, and Integration (UDDI) registries, custom configuration management repositories, and master system management consoles, such as Microsoft Operations Manager 2004 (MOM) and System Center Operations Manager 2007 (SCOM).</span></span>