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
ms.openlocfilehash: d9bcebbb138d12514bbd6c6dbac1874e81f438e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382469"
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="979fc-102">架构导入到 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="979fc-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="979fc-103">以下信息介绍如何将架构导入 BizTalk Server 项目。</span><span class="sxs-lookup"><span data-stu-id="979fc-103">The following information describes how to import schemas into a BizTalk Server project.</span></span>  
  
## <a name="importing-schemas"></a><span data-ttu-id="979fc-104">导入架构</span><span class="sxs-lookup"><span data-stu-id="979fc-104">Importing Schemas</span></span>  
  
#### <a name="to-import-schemas"></a><span data-ttu-id="979fc-105">若要导入架构</span><span class="sxs-lookup"><span data-stu-id="979fc-105">To import schemas</span></span>  
  
1. <span data-ttu-id="979fc-106">在解决方案资源管理器，右键单击项目，指向**外**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="979fc-106">In Solution Explorer, right-click the project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
2. <span data-ttu-id="979fc-107">单击**添加适配器**，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="979fc-107">Click **Add adapter**, and then select **Open**.</span></span>  
  
3. <span data-ttu-id="979fc-108">选择适配器<strong>，j.d.Edwards OneWorld XE</strong>。</span><span class="sxs-lookup"><span data-stu-id="979fc-108">Select the adapter<strong>, J.D. Edwards OneWorld XE</strong>.</span></span>  
  
4. <span data-ttu-id="979fc-109">在下拉列表中，选择的端口**SSOSendToJD Edwards OneWorld XE**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="979fc-109">In the drop-down list, select the port **SSOSendToJD Edwards OneWorld XE**, and then click **Next**.</span></span>  
  
    <span data-ttu-id="979fc-110">MyJ.D。</span><span class="sxs-lookup"><span data-stu-id="979fc-110">The myJ.D.</span></span> <span data-ttu-id="979fc-111">Edwards OneWorld XESSO 逻辑系统将显示在浏览器 （使用 SSOSendToJ.D 已创建此逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="979fc-111">Edwards OneWorld XESSO logical system appears in the browser (this logical system was created with the SSOSendToJ.D.</span></span> <span data-ttu-id="979fc-112">Edwards OneWorld XE 端口）。</span><span class="sxs-lookup"><span data-stu-id="979fc-112">Edwards OneWorld XE port).</span></span>  
  
5. <span data-ttu-id="979fc-113">展开**myJ.D。Edwards OneWorld XESSO**。</span><span class="sxs-lookup"><span data-stu-id="979fc-113">Expand **myJ.D. Edwards OneWorld XESSO**.</span></span>  
  
6. <span data-ttu-id="979fc-114">单击箭头图标以将项移动 （或只需将其） 进入**传输**窗口，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="979fc-114">Click the arrow icon to move the item (or simply drag it) into the **Transmit** window, and then click **OK**.</span></span>  
  
    <span data-ttu-id="979fc-115">架构将添加到 SSOSchedule 项目。</span><span class="sxs-lookup"><span data-stu-id="979fc-115">The schemas are added to the SSOSchedule project.</span></span>  
  
7. <span data-ttu-id="979fc-116">在解决方案资源管理器，展开**SSOSchedule 项目**。</span><span class="sxs-lookup"><span data-stu-id="979fc-116">In Solution Explorer, expand **SSOSchedule project**.</span></span>  
  
8. <span data-ttu-id="979fc-117">右键单击**BizTalk orchestration.odx**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="979fc-117">Right-click **BizTalk orchestration.odx**, and then click **Delete**.</span></span>  
  
9. <span data-ttu-id="979fc-118">在解决方案资源管理器中双击**GetList.odx**来检查该业务流程。</span><span class="sxs-lookup"><span data-stu-id="979fc-118">In Solution Explorer, double-click **GetList.odx** to inspect the orchestration.</span></span>  
  
## <a name="orchestration-types---port-types"></a><span data-ttu-id="979fc-119">业务流程类型-端口类型</span><span class="sxs-lookup"><span data-stu-id="979fc-119">Orchestration Types - Port Types</span></span>  
  
-   <span data-ttu-id="979fc-120">**PortTypeIn/中/请求：** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="979fc-120">**PortTypeIn/In/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="979fc-121">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="979fc-121">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="979fc-122">**PortTypeOut/扩展/响应：** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="979fc-122">**PortTypeOut/Out/response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="979fc-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="979fc-123">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
-   <span data-ttu-id="979fc-124">**PortTypeInOut/InOut/请求：** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="979fc-124">**PortTypeInOut/InOut/Request:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="979fc-125">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="979fc-125">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="979fc-126">**PortTypeInOut/InOut/响应：** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="979fc-126">**PortTypeInOut/InOut/Response:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="979fc-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="979fc-127">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="orchestration-variables---messages"></a><span data-ttu-id="979fc-128">Orchestration 变量-消息</span><span class="sxs-lookup"><span data-stu-id="979fc-128">Orchestration Variables - Messages</span></span>  
  
-   <span data-ttu-id="979fc-129">**MessageIn:** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="979fc-129">**MessageIn:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="979fc-130">Edwards OneWorld XEsso_transmitService_3.method</span><span class="sxs-lookup"><span data-stu-id="979fc-130">Edwards OneWorld XEsso_transmitService_3.method</span></span>  
  
-   <span data-ttu-id="979fc-131">**MessageOut:** SSOSchedule.myJ.D。</span><span class="sxs-lookup"><span data-stu-id="979fc-131">**MessageOut:** SSOSchedule.myJ.D.</span></span> <span data-ttu-id="979fc-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span><span class="sxs-lookup"><span data-stu-id="979fc-132">Edwards OneWorld XE sso_transmitService_3.methodResponse</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="979fc-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="979fc-133">See Also</span></span>  
 [<span data-ttu-id="979fc-134">适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="979fc-134">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)