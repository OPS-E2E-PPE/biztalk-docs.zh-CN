---
title: "网络管理服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21469dad-6c64-470a-bd58-8309d789ce6c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 741abaaa3042cb40f7043b25ce041bb84740f26a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="service-network-management"></a><span data-ttu-id="57c7b-102">服务网络管理</span><span class="sxs-lookup"><span data-stu-id="57c7b-102">Service Network Management</span></span>
<span data-ttu-id="57c7b-103">有效的运行时管理需要了解部署到运行时环境的服务。</span><span class="sxs-lookup"><span data-stu-id="57c7b-103">Effective run-time governance requires knowledge of the services deployed into the run-time environment.</span></span> <span data-ttu-id="57c7b-104">实际的接收位置和发送端口在 BizTalk 管理组中，部署，如图 1 中所示，可以发现 AmberPoint SMS。</span><span class="sxs-lookup"><span data-stu-id="57c7b-104">AmberPoint SMS can discover the actual receive locations and send ports deployed within a BizTalk Management Group, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="57c7b-105">![AmberPoint 容器发现](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9 AmberPointContainerDiscovery")</span><span class="sxs-lookup"><span data-stu-id="57c7b-105">![AmberPoint Container Discovery](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9-AmberPointContainerDiscovery")</span></span>  
  
 <span data-ttu-id="57c7b-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="57c7b-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="57c7b-107">**AmberPoint SMS 容器发现屏幕**</span><span class="sxs-lookup"><span data-stu-id="57c7b-107">**The AmberPoint SMS Container Discovery screens**</span></span>  
  
 <span data-ttu-id="57c7b-108">使用已部署的服务的信息，请 AmberPoint SMS 显示的帮助以了解运行时配置和评估运行中的其他服务的依存关系的用户的服务的各种透视图服务网络。</span><span class="sxs-lookup"><span data-stu-id="57c7b-108">Using information on the deployed services, AmberPoint SMS presents various perspectives of the services that help users to understand the run-time configuration and appreciate their dependencies on other services within the running service network.</span></span> <span data-ttu-id="57c7b-109">图 2 显示的服务配置文件和依赖项屏幕。</span><span class="sxs-lookup"><span data-stu-id="57c7b-109">Figure 2 shows the service profile and dependencies screens.</span></span>  
  
 <span data-ttu-id="57c7b-110">![AmberPoint 服务配置文件](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9 AmberPointServiceProfile")</span><span class="sxs-lookup"><span data-stu-id="57c7b-110">![AmberPoint Service Profile](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9-AmberPointServiceProfile")</span></span>  
  
 <span data-ttu-id="57c7b-111">**图 2**</span><span class="sxs-lookup"><span data-stu-id="57c7b-111">**Figure 2**</span></span>  
  
 <span data-ttu-id="57c7b-112">**AmberPoint SMS 服务配置文件和依赖项屏幕**</span><span class="sxs-lookup"><span data-stu-id="57c7b-112">**The AmberPoint SMS service profile and dependencies screens**</span></span>  
  
 <span data-ttu-id="57c7b-113">AmberPoint SMS 可以将发布，如服务发现和运行时元数据转发到现有的通用描述、 发现和集成 (UDDI) 注册表、 自定义配置管理存储库和主系统管理控制台Microsoft Operations Manager (MOM) 2004年和 System Center Operations Manager 2007 (SCOM)。</span><span class="sxs-lookup"><span data-stu-id="57c7b-113">AmberPoint SMS can publish and forward service discoveries and run-time metadata to existing Universal Description, Discovery, and Integration (UDDI) registries, custom configuration management repositories, and master system management consoles, such as Microsoft Operations Manager 2004 (MOM) and System Center Operations Manager 2007 (SCOM).</span></span>