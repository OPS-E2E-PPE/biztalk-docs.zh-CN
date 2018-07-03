---
title: 如何配置每个实例为发送端口的管道属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d1d49f0c6f54341c14cb14c38cc0de7fefaa9a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990998"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="a5f31-102">如何为发送端口配置基于实例的管道属性</span><span class="sxs-lookup"><span data-stu-id="a5f31-102">How to Configure Per-Instance Pipeline Properties for a Send Port</span></span>
<span data-ttu-id="a5f31-103">本主题介绍如何使用 BizTalk Server 管理控制台后管道部署到 BizTalk 组配置为发送端口的管道属性。</span><span class="sxs-lookup"><span data-stu-id="a5f31-103">This topic describes how to use the BizTalk Server Administration console to configure pipeline properties for a send port after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="a5f31-104">所做的更改覆盖默认管道，此发送端口属性，因此如果希望，可以将不同的管道属性的每个发送端口配置 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="a5f31-104">Changes that you make overwrite the default pipeline properties for this send port only, so if you want, you can configure different pipeline properties for each send port in the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a5f31-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="a5f31-105">Prerequisites</span></span>  
 <span data-ttu-id="a5f31-106">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a5f31-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a5f31-107">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a5f31-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5f31-108">使用每个实例的管道属性设置的值时**DocumentSpecNames** XML 拆装器组件的管道、 指定的文档架构和管道中的属性必须在同一项目中定义。</span><span class="sxs-lookup"><span data-stu-id="a5f31-108">When using per-instance pipeline properties to set the value for the **DocumentSpecNames** property in the XML disassembler component of a pipeline, the specified document schema and the pipeline must be defined in the same project.</span></span>  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a><span data-ttu-id="a5f31-109">若要配置每个实例为发送端口的管道属性</span><span class="sxs-lookup"><span data-stu-id="a5f31-109">To configure per-instance pipeline properties for a send port</span></span>  
  
1. <span data-ttu-id="a5f31-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a5f31-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a5f31-111">在控制台树中，展开**BizTalk Server 管理**，展开包含您要为其配置管道属性中，展开的发送端口的 BizTalk 组**应用程序**，，然后展开包含发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a5f31-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the send port for which you want to configure pipeline properties, expand **Applications**, and then expand the application containing the send port.</span></span>  
  
3. <span data-ttu-id="a5f31-112">单击**发送端口**文件夹中，右键单击该发送端口，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="a5f31-112">Click the **Send Ports** folder, right-click the send port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="a5f31-113">单击省略号 (**...**) 右侧的按钮**发送管道**框。</span><span class="sxs-lookup"><span data-stu-id="a5f31-113">Click the ellipsis (**…**) button to the right of the **Send Pipeline** box.</span></span>  
  
5. <span data-ttu-id="a5f31-114">配置属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5f31-114">Configure the properties you want, and then click **OK**.</span></span> <span data-ttu-id="a5f31-115">单击**帮助**的详细信息的属性页上。</span><span class="sxs-lookup"><span data-stu-id="a5f31-115">Click **Help** on the properties page for more information.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="a5f31-116">请确保输入正确的管道属性的信息。</span><span class="sxs-lookup"><span data-stu-id="a5f31-116">Make sure that you enter correct information for pipelines properties.</span></span> <span data-ttu-id="a5f31-117">如果输入无效值，例如一个字符串，而不是数字，它将生成一个错误。</span><span class="sxs-lookup"><span data-stu-id="a5f31-117">If you enter an invalid value, for example a string rather than a number, it will generate an error.</span></span>  
  
6. <span data-ttu-id="a5f31-118">如果这是要求响应发送端口，单击省略号 (**...**) 右侧的按钮**接收管道**框。</span><span class="sxs-lookup"><span data-stu-id="a5f31-118">If this is a solicit-response send port, click the ellipsis (**…**) button to the right of the **Receive Pipeline** box.</span></span>  
  
7. <span data-ttu-id="a5f31-119">配置属性，然后单击**确定**两次。</span><span class="sxs-lookup"><span data-stu-id="a5f31-119">Configure the properties you want, and then click **OK** twice.</span></span> <span data-ttu-id="a5f31-120">单击**帮助**的详细信息的属性页上。</span><span class="sxs-lookup"><span data-stu-id="a5f31-120">Click **Help** on the properties page for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f31-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5f31-121">See Also</span></span>  
 <span data-ttu-id="a5f31-122">[管理管道](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="a5f31-122">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 <span data-ttu-id="a5f31-123">[创建和配置发送端口](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a5f31-123">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="a5f31-124">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="a5f31-124">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)