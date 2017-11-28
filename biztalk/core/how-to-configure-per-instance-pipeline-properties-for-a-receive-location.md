---
title: "如何配置每个实例的管道属性接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- receive locations, configuring
- managing [pipelines], properties
- managing [pipelines], receive locations
- managing [receive locations], pipelines
- managing [pipelines], configuring
- pipelines, receive locations
- pipelines, configuring
- receive locations, pipelines
- managing [receive locations], configuring
ms.assetid: e1ed3b10-2f39-479b-a3e6-22b4b2872192
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e14483c5d17d968fc79126c65506720b501b6da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-receive-location"></a><span data-ttu-id="ce14e-102">如何配置每个实例的管道属性接收位置</span><span class="sxs-lookup"><span data-stu-id="ce14e-102">How to Configure Per-instance Pipeline Properties for a Receive Location</span></span>
<span data-ttu-id="ce14e-103">本主题介绍在将管道部署到 BizTalk 组之后如何使用 BizTalk Server 管理控制台为接收位置配置管道属性。</span><span class="sxs-lookup"><span data-stu-id="ce14e-103">This topic describes how to use the BizTalk Server Administration console to configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="ce14e-104">您所做的更改将只覆盖此接收位置的默认管道属性，因此如果需要，可以为 BizTalk 组中的每个接收位置配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="ce14e-104">Changes that you make overwrite the default pipeline properties for this receive location only, so if you want, you can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ce14e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="ce14e-105">Prerequisites</span></span>  
 <span data-ttu-id="ce14e-106">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ce14e-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ce14e-107">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ce14e-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce14e-108">使用每个实例管道属性设置的值时**DocumentSpecNames**必须在相同的项目中定义管道、 指定的文档架构和管道的 XML 反汇编程序组件中的属性。</span><span class="sxs-lookup"><span data-stu-id="ce14e-108">When using per-instance pipeline properties to set the value for the **DocumentSpecNames** property in the XML disassembler component of a pipeline, the specified document schema and the pipeline must be defined in the same project.</span></span>  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-receive-location"></a><span data-ttu-id="ce14e-109">为接收位置配置基于实例的管道属性</span><span class="sxs-lookup"><span data-stu-id="ce14e-109">To configure per-instance pipeline properties for a receive location</span></span>  
  
1.  <span data-ttu-id="ce14e-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ce14e-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ce14e-111">在控制台树中，展开**BizTalk Server 管理**，展开包含要配置管道属性，请展开的接收位置的 BizTalk 组**应用程序**，，然后展开包含接收位置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce14e-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the receive location for which to configure pipeline properties, expand **Applications**, and then expand the application containing the receive location.</span></span>  
  
3.  <span data-ttu-id="ce14e-112">单击**接收位置**文件夹，右键单击接收位置，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ce14e-112">Click the **Receive Locations** folder, right-click the receive location, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ce14e-113">单击右侧的省略号 （...）**接收管道**框。</span><span class="sxs-lookup"><span data-stu-id="ce14e-113">Click the ellipsis (…) to the right of the **Receive Pipeline** box.</span></span>  
  
5.  <span data-ttu-id="ce14e-114">配置属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ce14e-114">Configure the properties you want, and then click **OK**.</span></span> <span data-ttu-id="ce14e-115">有关详细信息，请单击**帮助**的属性页上。</span><span class="sxs-lookup"><span data-stu-id="ce14e-115">For more information, click **Help** on the properties page.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ce14e-116">请确保输入正确的管道属性的信息。</span><span class="sxs-lookup"><span data-stu-id="ce14e-116">Make sure that you enter correct information for pipelines properties.</span></span> <span data-ttu-id="ce14e-117">如果输入无效值，例如字符串而不是数字，它将生成一个错误。</span><span class="sxs-lookup"><span data-stu-id="ce14e-117">If you enter an invalid value, for example a string rather than a number, it will generate an error.</span></span>  
  
6.  <span data-ttu-id="ce14e-118">如果这是请求-响应接收位置，单击右侧的省略号 （...）**发送管道**框。</span><span class="sxs-lookup"><span data-stu-id="ce14e-118">If this is a request-response receive location, click the ellipsis (…) to the right of the **Send Pipeline** box.</span></span>  
  
7.  <span data-ttu-id="ce14e-119">配置属性，然后单击**确定**两次。</span><span class="sxs-lookup"><span data-stu-id="ce14e-119">Configure the properties you want, and then click **OK** twice.</span></span> <span data-ttu-id="ce14e-120">有关详细信息，请单击**帮助**的属性页上。</span><span class="sxs-lookup"><span data-stu-id="ce14e-120">For more information, click **Help** on the properties page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce14e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce14e-121">See Also</span></span>  
 <span data-ttu-id="ce14e-122">[管理管道](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="ce14e-122">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 <span data-ttu-id="ce14e-123">[创建和配置发送端口](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="ce14e-123">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="ce14e-124">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="ce14e-124">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)