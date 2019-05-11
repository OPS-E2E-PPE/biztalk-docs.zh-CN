---
title: 开发使用 Siebel 适配器的 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 08/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
- CBR
- Content-Based Routing
ms.assetid: 1a2a9765-305c-44b2-aed7-5437725e4c19
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9302dca6a86cbc149a0fd5aa23acc844ff803ff8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371719"
---
# <a name="develop-biztalk-applications-using-the-siebel-adapter"></a><span data-ttu-id="c0d83-102">开发 BizTalk 应用程序使用 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="c0d83-102">Develop BizTalk applications using the Siebel adapter</span></span>

## <a name="overview"></a><span data-ttu-id="c0d83-103">概述</span><span class="sxs-lookup"><span data-stu-id="c0d83-103">Overview</span></span>
<span data-ttu-id="c0d83-104">开发 BizTalk 应用程序涉及到创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="c0d83-104">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate XML schema.</span></span> <span data-ttu-id="c0d83-105">后生成架构后，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程发送和接收符合所生成的架构的消息。</span><span class="sxs-lookup"><span data-stu-id="c0d83-105">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="c0d83-106">CBR 可以在发送到 Siebel 系统的消息不需要任何密集型处理方案中使用。</span><span class="sxs-lookup"><span data-stu-id="c0d83-106">CBR can be used in scenarios where the messages being sent to a Siebel system do not require any intensive processing.</span></span> <span data-ttu-id="c0d83-107">例如，如果您知道，将在接收端口接收消息仅特定类型的可以将筛选器添加到要将路由到发送端口筛选器表达式匹配的消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="c0d83-107">For example, if you know that the receive port will be receiving messages only of a certain type, you can add a filter to the send port to route the messages matching the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="c0d83-108">BizTalk 业务流程中创建发送和接收端口以发送和接收消息来回[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，后者又将发送到消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c0d83-108">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c0d83-109">本部分提供有关使用 BizTalk 业务流程执行对 Siebel 系统使用的操作信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c0d83-109">This section provides information about using BizTalk orchestrations to perform operations on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="c0d83-110">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]又使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，可以与 WCF 绑定进行交互。</span><span class="sxs-lookup"><span data-stu-id="c0d83-110">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] that can interact with a WCF binding.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="c0d83-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="c0d83-111">Before you begin</span></span>  

* <span data-ttu-id="c0d83-112">若要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请始终将**EnableBizTalkCompatibilityMode**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="c0d83-112">To use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="c0d83-113">有关步骤，请参阅[配置的绑定属性用于 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="c0d83-113">For the steps, see [Configure the binding properties for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span></span>
  
* <span data-ttu-id="c0d83-114">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]随[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理控制台中未自动列出。</span><span class="sxs-lookup"><span data-stu-id="c0d83-114">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is not automatically listed in the BizTalk Server Administration console.</span></span> <span data-ttu-id="c0d83-115">这是因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="c0d83-115">This is because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF custom binding.</span></span> 

* <span data-ttu-id="c0d83-116">若要生成元数据，请使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c0d83-116">To generate metadata, use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span> <span data-ttu-id="c0d83-117">不要使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c0d83-117">Do not use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="c0d83-118">有关使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[获取 Siebel 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="c0d83-118">For instructions on using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], see [Get Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span></span>   

  
## <a name="see-also"></a><span data-ttu-id="c0d83-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0d83-119">See Also</span></span>  
[<span data-ttu-id="c0d83-120">开发 Siebel 应用程序</span><span class="sxs-lookup"><span data-stu-id="c0d83-120">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)