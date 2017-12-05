---
title: "部署你的服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, servers
- servers, deploying
ms.assetid: 6036e42b-59b8-4092-addd-288e9c4b91d6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fc3da3798e78e9b5fcf1ce09180c43e10417997
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="deploying-your-servers"></a><span data-ttu-id="f01a3-102">部署你的服务器</span><span class="sxs-lookup"><span data-stu-id="f01a3-102">Deploying Your Servers</span></span>
<span data-ttu-id="f01a3-103">本部分提供有关将每个中的服务器配置的说明你[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="f01a3-103">This section provides instructions for configuring each of the servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span> <span data-ttu-id="f01a3-104">配置网络后你可以通过执行以下步骤部署每个服务器上的软件。</span><span class="sxs-lookup"><span data-stu-id="f01a3-104">After you configure the network you deploy the software on each server by using the following steps.</span></span>  
  
 <span data-ttu-id="f01a3-105">在开始之前服务器部署，请确保你阅读并执行步骤中所述部署准备[为部署做好准备](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="f01a3-105">Before starting server deployment, make sure that you read and perform the deployment preparation steps described in [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span> <span data-ttu-id="f01a3-106">未能遵循上一节中的规范性指南可能导致的未知和不受支持配置的部署 （和后续步骤可能会失败）。</span><span class="sxs-lookup"><span data-stu-id="f01a3-106">Failing to adhere to the prescriptive guidance in the previous section might result in an unknown and unsupported configuration of the deployment (and subsequent steps might fail).</span></span>  
  
 <span data-ttu-id="f01a3-107">有关详细信息，请参阅 BizTalk Server 部署指南。</span><span class="sxs-lookup"><span data-stu-id="f01a3-107">For more information, see the BizTalk Server Deployment Guide.</span></span>  
  
 <span data-ttu-id="f01a3-108">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="f01a3-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="f01a3-109">步骤 1：安装基础平台</span><span class="sxs-lookup"><span data-stu-id="f01a3-109">Step 1: Installing the Base Platform</span></span>](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)  
  
-   [<span data-ttu-id="f01a3-110">步骤 2：在服务器上配置 NLB</span><span class="sxs-lookup"><span data-stu-id="f01a3-110">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)  
  
-   [<span data-ttu-id="f01a3-111">步骤 3：配置域控制器</span><span class="sxs-lookup"><span data-stu-id="f01a3-111">Step 3: Configuring the Domain Controller</span></span>](../../adapters-and-accelerators/accelerator-swift/step-3-configuring-the-domain-controller.md)  
  
-   [<span data-ttu-id="f01a3-112">步骤 4：配置数据库服务器</span><span class="sxs-lookup"><span data-stu-id="f01a3-112">Step 4: Configuring the Database Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-4-configuring-the-database-servers.md)  
  
-   [<span data-ttu-id="f01a3-113">步骤 5：配置 BizTalk 消息服务器</span><span class="sxs-lookup"><span data-stu-id="f01a3-113">Step 5: Configuring the BizTalk Messaging Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-5-configuring-the-biztalk-messaging-servers.md)  
  
-   [<span data-ttu-id="f01a3-114">步骤 6：配置 BizTalk 业务流程服务器</span><span class="sxs-lookup"><span data-stu-id="f01a3-114">Step 6: Configuring the BizTalk Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-6-configuring-the-biztalk-orchestration-servers.md)  
  
-   [<span data-ttu-id="f01a3-115">步骤 7：配置 BizTalk HTTP 前端服务器</span><span class="sxs-lookup"><span data-stu-id="f01a3-115">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-7-configuring-the-biztalk-http-front-end-servers.md)  
  
-   [<span data-ttu-id="f01a3-116">步骤 8：配置后更改</span><span class="sxs-lookup"><span data-stu-id="f01a3-116">Step 8: Post-Configuration Changes</span></span>](../../adapters-and-accelerators/accelerator-swift/step-8-post-configuration-changes.md)