---
title: "如何配置发送端口的每个实例管道属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- managing [pipelines], properties
- configuring, send ports
- configuring, pipelines
- managing [pipelines], configuring
- managing [send ports], pipelines
- managing [send ports], configuring
- send ports, pipelines
- pipelines, configuring
ms.assetid: c58faa9e-0dfb-458b-8f1b-d3c91bce0436
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfb9927dca890a7f84baf372c4fa250a8ced17c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="340da-102">如何为发送端口配置基于实例的管道属性</span><span class="sxs-lookup"><span data-stu-id="340da-102">How to Configure Per-Instance Pipeline Properties for a Send Port</span></span>
<span data-ttu-id="340da-103">本主题介绍如何使用 BizTalk Server 管理控制台来配置发送端口的管道属性，管道已部署到 BizTalk 组后。</span><span class="sxs-lookup"><span data-stu-id="340da-103">This topic describes how to use the BizTalk Server Administration console to configure pipeline properties for a send port after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="340da-104">您所做更改覆盖默认管道仅，此发送端口属性，这样如果你想，可以将每个发送端口的不同管道属性配置 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="340da-104">Changes that you make overwrite the default pipeline properties for this send port only, so if you want, you can configure different pipeline properties for each send port in the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="340da-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="340da-105">Prerequisites</span></span>  
 <span data-ttu-id="340da-106">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="340da-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="340da-107">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="340da-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="340da-108">使用每个实例管道属性设置的值时**DocumentSpecNames**必须在相同的项目中定义管道、 指定的文档架构和管道的 XML 反汇编程序组件中的属性。</span><span class="sxs-lookup"><span data-stu-id="340da-108">When using per-instance pipeline properties to set the value for the **DocumentSpecNames** property in the XML disassembler component of a pipeline, the specified document schema and the pipeline must be defined in the same project.</span></span>  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="340da-109">若要配置每个实例管道发送端口属性</span><span class="sxs-lookup"><span data-stu-id="340da-109">To configure per-instance pipeline properties for a send port</span></span>  
  
1.  <span data-ttu-id="340da-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="340da-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="340da-111">在控制台树中，展开**BizTalk Server 管理**，展开包含你想要配置管道属性中，展开发送端口的 BizTalk 组**应用程序**，，然后展开包含发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="340da-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the send port for which you want to configure pipeline properties, expand **Applications**, and then expand the application containing the send port.</span></span>  
  
3.  <span data-ttu-id="340da-112">单击**发送端口**文件夹，右键单击发送端口，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="340da-112">Click the **Send Ports** folder, right-click the send port, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="340da-113">单击省略号 (**...**) 的右侧的按钮**发送管道**框。</span><span class="sxs-lookup"><span data-stu-id="340da-113">Click the ellipsis (**…**) button to the right of the **Send Pipeline** box.</span></span>  
  
5.  <span data-ttu-id="340da-114">配置属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="340da-114">Configure the properties you want, and then click **OK**.</span></span> <span data-ttu-id="340da-115">单击**帮助**详细信息的属性页上。</span><span class="sxs-lookup"><span data-stu-id="340da-115">Click **Help** on the properties page for more information.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="340da-116">请确保输入正确的管道属性的信息。</span><span class="sxs-lookup"><span data-stu-id="340da-116">Make sure that you enter correct information for pipelines properties.</span></span> <span data-ttu-id="340da-117">如果输入无效值，例如字符串而不是数字，它将生成一个错误。</span><span class="sxs-lookup"><span data-stu-id="340da-117">If you enter an invalid value, for example a string rather than a number, it will generate an error.</span></span>  
  
6.  <span data-ttu-id="340da-118">如果这是请求-响应发送端口，单击省略号 (**...**) 的右侧的按钮**接收管道**框。</span><span class="sxs-lookup"><span data-stu-id="340da-118">If this is a solicit-response send port, click the ellipsis (**…**) button to the right of the **Receive Pipeline** box.</span></span>  
  
7.  <span data-ttu-id="340da-119">配置属性，然后单击**确定**两次。</span><span class="sxs-lookup"><span data-stu-id="340da-119">Configure the properties you want, and then click **OK** twice.</span></span> <span data-ttu-id="340da-120">单击**帮助**详细信息的属性页上。</span><span class="sxs-lookup"><span data-stu-id="340da-120">Click **Help** on the properties page for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340da-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="340da-121">See Also</span></span>  
 <span data-ttu-id="340da-122">[管理管道](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="340da-122">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 <span data-ttu-id="340da-123">[创建和配置发送端口](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="340da-123">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="340da-124">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="340da-124">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)