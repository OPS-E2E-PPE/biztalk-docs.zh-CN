---
title: 架构导入到 BizTalk Server Projects1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70eff140259cd7cf815e8e05125f9ade78bf5493
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982358"
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="ec144-102">架构导入到 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="ec144-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="ec144-103">以下信息介绍如何将架构导入到 BizTalk Server 项目中。</span><span class="sxs-lookup"><span data-stu-id="ec144-103">The following information describes how to import schemas into a BizTalk Server project.</span></span>  
  
## <a name="importing-schemas"></a><span data-ttu-id="ec144-104">导入架构</span><span class="sxs-lookup"><span data-stu-id="ec144-104">Importing Schemas</span></span>  
  
#### <a name="to-import-schemas"></a><span data-ttu-id="ec144-105">若要导入架构</span><span class="sxs-lookup"><span data-stu-id="ec144-105">To import schemas</span></span>  
  
1. <span data-ttu-id="ec144-106">在解决方案资源管理器，右键单击项目，指向**外**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="ec144-106">In Solution Explorer, right-click the project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
2. <span data-ttu-id="ec144-107">单击**添加适配器**，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="ec144-107">Click **Add adapter**, and then select **Open**.</span></span>  
  
3. <span data-ttu-id="ec144-108">选择适配器<strong>，j.d.Edwards OneWorld XE</strong>。</span><span class="sxs-lookup"><span data-stu-id="ec144-108">Select the adapter<strong>, J.D. Edwards OneWorld XE</strong>.</span></span>  
  
4. <span data-ttu-id="ec144-109">在下拉列表中，选择的端口**SSOSendToJD Edwards OneWorld XE**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ec144-109">In the drop-down list, select the port **SSOSendToJD Edwards OneWorld XE**, and then click **Next**.</span></span>  
  
    <span data-ttu-id="ec144-110">MyJ.D。</span><span class="sxs-lookup"><span data-stu-id="ec144-110">The myJ.D.</span></span> <span data-ttu-id="ec144-111">Edwards OneWorld XESSO 逻辑系统将显示在浏览器 （使用 SSOSendToJ.D 已创建此逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="ec144-111">Edwards OneWorld XESSO logical system appears in the browser (this logical system was created with the SSOSendToJ.D.</span></span> <span data-ttu-id="ec144-112">Edwards OneWorld XE 端口）。</span><span class="sxs-lookup"><span data-stu-id="ec144-112">Edwards OneWorld XE port).</span></span>  
  
5. <span data-ttu-id="ec144-113">展开**myJ.D。Edwards OneWorld XESSO**。</span><span class="sxs-lookup"><span data-stu-id="ec144-113">Expand **myJ.D. Edwards OneWorld XESSO**.</span></span>  
  
6. <span data-ttu-id="ec144-114">单击箭头图标以将项移动 （或只需将其） 进入**传输**窗口，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ec144-114">Click the arrow icon to move the item (or simply drag it) into the **Transmit** window, and then click **OK**.</span></span>  
  
    <span data-ttu-id="ec144-115">架构将添加到 SSOSchedule 项目。</span><span class="sxs-lookup"><span data-stu-id="ec144-115">The schemas are added to the SSOSchedule project.</span></span>  
  
7. <span data-ttu-id="ec144-116">在解决方案资源管理器，展开**SSOSchedule 项目**。</span><span class="sxs-lookup"><span data-stu-id="ec144-116">In Solution Explorer, expand **SSOSchedule project**.</span></span>  
  
8. <span data-ttu-id="ec144-117">右键单击**BizTalk orchestration.odx**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="ec144-117">Right-click **BizTalk orchestration.odx**, and then click **Delete**.</span></span>  
  
9. <span data-ttu-id="ec144-118">在解决方案资源管理器中双击**GetList.odx**来检查该业务流程。</span><span class="sxs-lookup"><span data-stu-id="ec144-118">In Solution Explorer, double-click **GetList.odx** to inspect the orchestration.</span></span>  
  
## <a name="orchestration-types---port-types"></a><span data-ttu-id="ec144-119">业务流程类型 - 端口类型</span><span class="sxs-lookup"><span data-stu-id="ec144-119">Orchestration Types - Port Types</span></span>  
  
-   <span data-ttu-id="ec144-120">**PortTypeIn/中/请求：** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="ec144-120">**PortTypeIn/In/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="ec144-121">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="ec144-121">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="ec144-122">**PortTypeOut/扩展/响应：** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="ec144-122">**PortTypeOut/Out/response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="ec144-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="ec144-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
-   <span data-ttu-id="ec144-124">**PortTypeInOut/InOut/请求：** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="ec144-124">**PortTypeInOut/InOut/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="ec144-125">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="ec144-125">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="ec144-126">**PortTypeInOut/InOut/响应：** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="ec144-126">**PortTypeInOut/InOut/Response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="ec144-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="ec144-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="orchestration-variables---messages"></a><span data-ttu-id="ec144-128">Orchestration 变量 - 消息</span><span class="sxs-lookup"><span data-stu-id="ec144-128">Orchestration Variables - Messages</span></span>  
  
-   <span data-ttu-id="ec144-129">**MessageIn:** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="ec144-129">**MessageIn:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="ec144-130">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="ec144-130">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="ec144-131">**MessageOut:** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="ec144-131">**MessageOut:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="ec144-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="ec144-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec144-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec144-133">See Also</span></span>  
 [<span data-ttu-id="ec144-134">适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="ec144-134">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)